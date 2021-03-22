## Code Snippets

- [Code Snippets](#code-snippets)
  - [Show or Hide Keyboard](#show-or-hide-keyboard)
  - [Enabling Data Binding](#enabling-data-binding)
  - [Add Navigation components to project](#add-navigation-components-to-project)
  - [Adding a Menu item](#adding-a-menu-item)
### Show or Hide Keyboard
* show keyboard
```kotlin
val imm = getSystemService(Context.INPUT_METHOD_SERVICE) as InputMethodManager
imm.showSoftInput(editText, 0)
```
* hide keyboard
```kotlin
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

### Add Navigation components to project
* At the top of the project-level build.gradle file, along with the other ext variables, add a variable for the navigationVersion. To find the latest navigation version number, see Declaring dependencies in the Android developer documentation.
```gradle
ext {
        ...
        navigationVersion = "2.3.0"
        ...
    }
```
* In the Gradle Scripts folder, open the module-level build.gradle file. Add the dependencies for navigation-fragment-ktx and navigation-ui-ktx, as shown below:
```gradle
dependencies {
  ...
  implementation "androidx.navigation:navigation-fragment-ktx:$navigationVersion"
  implementation "androidx.navigation:navigation-ui-ktx:$navigationVersion"
  ...
}
```
* Finally create a Navigation resource in `res` directory

### Adding a Menu item
* After the UI is done, follow the following steps:
* Open the TitleFragment.kt Kotlin file. Inside the `onCreateView()` method, before the return, call the `setHasOptionsMenu()` method and pass in true.
```kotlin
override fun onCreateView(inflater: LayoutInflater, container: ViewGroup?,
                         savedInstanceState: Bundle?): View? {
   ...
   setHasOptionsMenu(true)
   return binding.root
}
```

* After the `onCreateView()` method, override the `onCreateOptionsMenu()` method. In the method, add the options menu and inflate the menu resource file.
```kotlin
override fun onCreateOptionsMenu(menu: Menu, inflater: MenuInflater) {
        super.onCreateOptionsMenu(menu, inflater)
        inflater.inflate(R.menu.options_menu, menu)
}
```
* Override the `onOptionsItemSelected()` method to take the appropriate action when the menu item is tapped. In this case, the action is to navigate to the Fragment that has the same id as the selected menu item.
```kotlin
override fun onOptionsItemSelected(item: MenuItem): Boolean {
     return NavigationUI.
            onNavDestinationSelected(item,requireView().findNavController())
            || super.onOptionsItemSelected(item)
}
```
* If the app doesn't build, check to see whether you need to import packages to fix unresolved references in the code. For example, you can add `import android.view.*` to resolve several references (and replace more specific imports such as `import android.view.ViewGroup`).
