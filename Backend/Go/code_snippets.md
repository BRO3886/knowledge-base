# Code Snippets

## Contents
- [Code Snippets](#code-snippets)
	- [Contents](#contents)
		- [Type Switch](#type-switch)
		- [Runnning Sentry as middleware with custom logging on context](#runnning-sentry-as-middleware-with-custom-logging-on-context)

### Type Switch
Type switches
A type switch is a construct that permits several type assertions in series.

A type switch is like a regular switch statement, but the cases in a type switch specify types (not values), and those values are compared against the type of the value held by the given interface value.
```go
switch v := i.(type) {
case T:
    // here v has type T
case S:
    // here v has type S
default:
    // no match; here v has the same type as i
}
```
The declaration in a type switch has the same syntax as a type assertion i.(T), but the specific type T is replaced with the keyword type.

This switch statement tests whether the interface value i holds a value of type T or S. In each of the T and S cases, the variable v will be of type T or S respectively and hold the value held by i. In the default case (where there is no match), the variable v is of the same interface type and value as i.
### Runnning Sentry as middleware with custom logging on context
```go
package logger

import (
	"bytes"

	"github.com/gin-gonic/gin"
)

//CustomLogger to get the resp body
type CustomLogger struct {
	gin.ResponseWriter
	body *bytes.Buffer
}

func (w CustomLogger) Write(b []byte) (int, error) {
	w.body.Write(b)
	return w.ResponseWriter.Write(b)
}
```
```go
package logger

import (
	"bytes"
	"fmt"
	"io/ioutil"
	utils "rootpackage/util"

	"github.com/getsentry/sentry-go"
	sentrygin "github.com/getsentry/sentry-go/gin"
	"github.com/gin-gonic/gin"
	log "github.com/sirupsen/logrus"
)

//CustomSentryMiddleware logs the error and sends the error to sentry
func CustomSentryMiddleware(c *gin.Context) {
	csm := &CustomLogger{body: bytes.NewBufferString(""), ResponseWriter: c.Writer}
	c.Writer = csm

	hub := sentrygin.GetHubFromContext(c)
	if hub == nil {
		log.Error("Unable to find sentry middleware on gin context")
	}

	// Process request
	c.Next()

	uExists := true
	u, _, err := utils.GetCurrOrgAndUser(c)
	if err != nil {
		uExists = false
	}

	path := c.Request.URL.Path
	raw := c.Request.URL.RawQuery

	if raw != "" {
		path = path + "?" + raw
	}

	status := c.Writer.Status()

	if status >= 500 {

		body, err := ioutil.ReadAll(c.Request.Body)
		if err != nil {
			log.Error("reading body: ", err)
		}

		log.Error(csm.body)

		err = fmt.Errorf("%v", csm.body)

		go hub.WithScope(func(scope *sentry.Scope) {
			scope.SetRequest(c.Request)
			if uExists {
				scope.SetUser(sentry.User{
					ID:        u.ID.Hex(),
					IPAddress: c.ClientIP(),
					Email:     u.Phone,
				})
			}
			scope.SetRequestBody(body)
			scope.SetExtras(map[string]interface{}{
				"path":     path,
				"ClientIP": c.ClientIP(),
			})
		})

		go hub.CaptureException(err)
		// log.Info("sent event to sentry: ID=", id)

	}
}

```