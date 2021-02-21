## Code Snippets

### Show or Hide Keyboard
* show keyboard
```kt
val imm = getSystemService(Context.INPUT_METHOD_SERVICE) as InputMethodManager
imm.showSoftInput(editText, 0)
```
* hide keyboard
```kt
val imm = getSystemService(Context.INPUT_METHOD_SERVICE) as InputMethodManager
imm.hideSoftInputFromWindow(view.windowToken, 0)
```
### Enabling Data Binding
To use data binding, you need to enable data binding in your Gradle file, as it's not enabled by default. This is because data binding increases compile time and may affect app startup time.
Open the `build.gradle (Module: app)` file.
Inside the `android` section, before the closing brace, add a `buildFeatures` section and set `dataBinding` to true
```gradle
buildFeatures {
    dataBinding true
}
```