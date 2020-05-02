# Set Dimensions in Code

* Each view has a **layoutParams** object.
* Set height/width etc. as properties of layoutParams

```kotlin
myButton.layoutParams.height = 100
```

* Sets dimensions as absolute pixels

---

* Convert pixels to dp in Kotlin

```kotlin
val pixels = TypedValue.applyDimension(
    TypedValue.COMPLEX_UNIT_DIP, 100f, resources.displayMetrics
)
output.layoutParams.height = pixels.toInt()
```
