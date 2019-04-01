# Speed of Innovation

Java has gone through a major ramp up regarding speed of innovation. Currently Java is releasing a new major version of the JVM every 6 months.

This is good news for all java developers, but there is one Problem: most businesses are not able to keep up with that speed, and therefore most businesses are still on JVM 8 (or even older versions). 

Kotlin has its own release cycle, and is happily running on older JVM versions. This allows for innovations like [coroutines](https://github.com/Kotlin/kotlinx.coroutines/blob/master/coroutines-guide.md)

```kotlin runnable
// { autofold
fun main(args: Array<String>) {
// }
    repeat(100_000) { // launch a lot of coroutines
        launch {
            delay(1000L)
            print(".")
        }
    }
// { autofold
    }
// }
```
