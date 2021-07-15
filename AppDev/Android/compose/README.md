# Jetpack Compose
Notes and trivia about jetpack compose, stolen from it's amazing documentation.

* `mutableStateOf(value)` creates a MutableState, which is an observable type in Compose. Any changes to its value will schedule recomposition of any composable functions that read that value.

* `remember` stores objects in the composition, and forgets the object when the composable that called remember is removed from the composition.

* `rememberSaveable` retains the state across configuration changes by saving it in a Bundle.
