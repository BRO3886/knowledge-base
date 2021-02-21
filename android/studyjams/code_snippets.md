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
