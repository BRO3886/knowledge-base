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
To work with data binding, you need to wrap your XML layout with a `<layout>` tag. This is so that **the root class is no longer a view group, but is instead a layout that contains view groups and views**. The binding object can then know about the layout and the views in it.
```xml
<layout>
   <LinearLayout ... >
   ...
   </LinearLayout>
</layout>
```