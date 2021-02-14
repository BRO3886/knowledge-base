## Trivia

Some random facts and info, which can be useful for people just starting out with Android, or might be useful for interviews etc. Found while learning Android during Study Jams.

### No main.kt?

Many programming languages define a main method that starts the program. **Android apps don't have a main method**. Instead, the AndroidManifest.xml file indicates that MainActivity should be launched when the user taps the app's launcher icon. To launch an activity, the Android OS uses the information in the manifest to set up the environment for the app and construct the MainActivity. Then the MainActivity does some setup in turn.

### Layout Inflation

Each activity has an associated layout file. The activity and the layout are connected by a process known as layout inflation. When the activity starts, the views that are defined in the XML layout files are turned into (or "inflated" into) Kotlin view objects in memory. Once this happens, the activity can draw these objects to the screen and also dynamically modify them.

### AppCompatActivity

AppCompatActivity is a subclass of Activity that supports all modern Android features while providing backward compatibility with older versions of Android. To make your app available to the largest number of devices and users possible, always use AppCompatActivity.

### lateinit

The `lateinit` keyword promises the Kotlin compiler that the variable will be initialized before the code calls any operations on it. Therefore we don't need to initialize the variable to null here, and we can treat it as a non-nullable variable when we use it. It is a best practice to use lateinit with fields that hold views in just this way.
