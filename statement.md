# Why Kotlin >> Java

3 Reasons

## Security

Kotlin is more secure than Java, mainly due to two language features

### Null safety

See https://kotlinlang.org/docs/reference/null-safety.html

The following code is not possible:

```kotlin runnable

fun test() {
    var a: String = "abc"
    a = null // compilation error
    }
```

Add a "?" to the value type to allow this:
```kotlin runnable
fun test() {
    var a: String? = "abc"
    a = null //this is ok
    }
```

But if you want to do something with those nullable values, you have to check for null:

```kotlin runnable
fun test() {
    var a: String? = "abc"
    a = null //this is ok
    println(a?.size())
    }
```


