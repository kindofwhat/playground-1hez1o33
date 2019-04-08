# Speed of Innovation

Java has gone through a major ramp up regarding speed of innovation. Currently Java is releasing a new major version of the JVM every 6 months.

This is good news for all java developers, but there is one Problem: most businesses are not able to keep up with that speed, and therefore most businesses are still on JVM 8 (or even older versions). 

Kotlin has its own release cycle, and is happily running on older JVM versions. This allows for innovations like [coroutines](https://github.com/Kotlin/kotlinx.coroutines/blob/master/coroutines-guide.md)

Note: the following snippet does not run on tech.io. It looks like coroutines are not supported yet...

```kotlin runnable
// { autofold
import kotlinx.coroutines.*

fun main(args: Array<String>) {
// }
    runBlocking {
//sampleStart
    GlobalScope.launch {
        repeat(1000) { i ->
            println("I'm sleeping $i ...")
            delay(500L)
        }
    }
    delay(1300L) 
// { autofold
    }
// }
```

Kotlin has some other advanced features. One of the most interessting ones are [smart casts](https://kotlinlang.org/docs/reference/typecasts.html). 

```kotlin runnable
// { autofold

fun main(args: Array<String>) {
// }
   var x: Any //no special type
   
   //TODO: intialize string hiere
   
   
   if (x is String) {
        print(x.length) // x is automatically cast to String
    }
    
   //TODO: intialize hiere

   if (x is Int) {
        print(x*2) // x is automatically cast to String
    }
    
// { autofold
    }
// }
```
