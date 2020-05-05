# Get Text from File

## Get Text from Resources

```kotlin
fun getTextFromResources(context: Context, resourceId: Int): String {
    return context.resources.openRawResource(resourceId).use {
        it.bufferedReader().use {
            it.readText()
        }
    }
}
```

## Get Text from Assets

```kotlin
fun getTextFromAssets(context: Context, fileName: String): String {
    return context.assets.open(fileName).use {
        it.bufferedReader().use {
            it.readText()
        }
    }
}
```
