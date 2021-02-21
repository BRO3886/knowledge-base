## Trivia

Some random facts and info, which can be useful for people just starting out with Android, or might be useful for interviews etc. Found while learning Android during Study Jams.

- [Trivia](#trivia)
  - [No main.kt?](#no-mainkt)
  - [Layout Inflation](#layout-inflation)
  - [AppCompatActivity](#appcompatactivity)
  - [lateinit](#lateinit)
  - [Right-Left vs Start-End](#right-left-vs-start-end)
  - [ScrollView](#scrollview)
  - [LinearLayout](#linearlayout)
  - [ViewGroup](#viewgroup)

### No main.kt?

Many programming languages define a main method that starts the program. **Android apps don't have a main method**. Instead, the AndroidManifest.xml file indicates that MainActivity should be launched when the user taps the app's launcher icon. To launch an activity, the Android OS uses the information in the manifest to set up the environment for the app and construct the MainActivity. Then the MainActivity does some setup in turn.

### Layout Inflation

Each activity has an associated layout file. The activity and the layout are connected by a process known as layout inflation. When the activity starts, the views that are defined in the XML layout files are turned into (or "inflated" into) Kotlin view objects in memory. Once this happens, the activity can draw these objects to the screen and also dynamically modify them.

### AppCompatActivity

AppCompatActivity is a subclass of Activity that supports all modern Android features while providing backward compatibility with older versions of Android. To make your app available to the largest number of devices and users possible, always use AppCompatActivity.

### lateinit

The `lateinit` keyword promises the Kotlin compiler that the variable will be initialized before the code calls any operations on it. Therefore we don't need to initialize the variable to null here, and we can treat it as a non-nullable variable when we use it. It is a best practice to use lateinit with fields that hold views in just this way.

### Right-Left vs Start-End
Right/left versus start/end

"Right" and "left" always refer to the right and left sides of the screen, whether your app uses a left-to-right (LTR) flow or a right-to-left (RTL) flow. "Start" and "end" always refer to the start and end of the flow:

For a LTR flow, start = left and end=right.
For a RTL flow, start=right and end=left.
If your app targets API level 17 (Android 4.2) or higher:

Use "start" and "end" instead of "left" and "right".
For example, android:layout_marginLeft should become android:layout_marginStart to support RTL languages.
If you want your app to work with versions lower than Android 4.2; that is, if the app's targetSdkVersion or minSdkVersion is 16 or lower:

Add "start" and end" in addition to "left" and "right".
For example, use both android:paddingLeft and android:paddingStart.

### ScrollView
A ScrollView is a view group that allows the view hierarchy placed within it to be scrolled. A scroll view can contain only one other view, or view group, as a child. The child view is commonly a LinearLayout. Inside a LinearLayout, you can add other views.

Use a ScrollView when you need to display content on the screen, such as long text or a collection of images. A scroll view can contain only one child view. If you want to scroll more than one view, then add a ViewGroup such as a LinearLayout to the ScrollView, and put the views to be scrolled inside that ViewGroup

### LinearLayout
LinearLayout is a view group that arranges its child views horizontally or vertically.

### ViewGroup
ViewGroup is a view that can contain other views. LinearLayout and ScrollView are view groups.

### Constraint Layout
A `ConstraintLayout` is a `ViewGroup` that allows you to position and size child views in a flexible way. A ConstraintLayout allows you to create large, complex layouts with flat view hierarchies (no nested view groups). To build a ConstraintLayout, you can use the Layout Editor to add constraints, and to drag-and-drop views. You don't need to edit the XML
#### Constraints
A constraint is a connection or alignment between two UI elements. Each constraint connects or aligns one view to another view, to the parent layout, or to an invisible guideline. In a ConstraintLayout, you position a view by defining at least one horizontal and one vertical constraint.