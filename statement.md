# Why Kotlin >> Java

3 Reasons

## Security

Kotlin is more secure than Java, mainly due to two language features

### Null safety


The following code is not possible:

```kotlin runnable
// { autofold
fun main(args: Array<String>) {
//  }
    var a: String = "abc"
    a = null // compilation error
    // { autofold
    }
//  }
```

Add a "?" to the value type to allow this:
```kotlin runnable
// { autofold
fun main(args: Array<String>) {
    var a: String? = "abc"
    println(a)
    a = null //this is ok
    println(a)
    // { autofold
}
//  }
```

But if you want to do something with those nullable values, you have to check for null:
(Using the `?.` operator. This is the "null safe dot operator", or "safe call operator")

```kotlin runnable
// { autofold
fun main(args: Array<String>) {
    var a: String? = "abc"
    a = null //this is ok
    println(a?.length)
    // { autofold
}
//  }
```
See https://kotlinlang.org/docs/reference/null-safety.html for more examples


