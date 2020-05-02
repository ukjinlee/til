# Set Dimensions in Code

* Each view has a **layoutParams** object.
* Set height/width etc. as properties of layoutParams
* Sets dimensions as absolute pixels

```kotlin
myButton.layoutParams.height = 100
```

* Convert dp to pixel in Kotlin

```kotlin
val pixels = TypedValue.applyDimension(
    TypedValue.COMPLEX_UNIT_DIP, 100f, resources.displayMetrics
)
output.layoutParams.height = pixels.toInt()
```

[source](https://stackoverflow.com/a/6327095)
