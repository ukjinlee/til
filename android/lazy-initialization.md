# Lazy Initialization

lazy() is a function that takes a lambda and returns an instance of Lazy<T> which can serve as a delegate for implementing a lazy property: the first call to get() executes the lambda passed to lazy() and remembers the result, subsequent calls to get() simply return the remembered result.

```kotlin
val lazyValue: String by lazy {
    println("computed!")
    "Hello"
}

fun main() {
    println(lazyValue)
    println(lazyValue)
}
```

[source](https://kotlinlang.org/docs/reference/delegated-properties.html#lazy)
