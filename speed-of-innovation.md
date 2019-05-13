# Speed of Innovation

Java has gone through a major ramp up regarding speed of innovation. Currently Java is releasing a new major version of the Java language every 6 months.

This is good news for all java developers, but there is one Problem: most businesses are not able to keep up with that speed, and therefore most businesses are still on JVM 8 (or even older versions). 

Kotlin has its own release cycle, and is happily running on older JVM versions. This allows for innovations like [coroutines](https://github.com/Kotlin/kotlinx.coroutines/blob/master/coroutines-guide.md)

Note: the following snippet does not run on tech.io, because the used docker image is rather old...

```kotlin
import kotlinx.coroutines.*
import java.text.SimpleDateFormat
import java.util.*

fun main() = runBlocking {
    val deferred1 = async { computation1() }
    val deferred2 = async { computation2() }
    printCurrentTime("Awaiting computations...")
    val result = deferred1.await() + deferred2.await()
    printCurrentTime("The result is $result")
}

suspend fun computation1(): Int {
    delay(1000L) // simulated computation
    printCurrentTime("Computation1 finished")
    return 131
}

suspend fun computation2(): Int {
    delay(2000L)
    printCurrentTime("Computation2 finished")
    return 9
}

fun printCurrentTime(message: String) {
    val time = (SimpleDateFormat("hh:mm:ss")).format(Date())
    println("[$time] $message")
}```

Go to https://pl.kotl.in/1RO1ygMUT to see it in action

Kotlin has some other advanced features. One of the most interessting ones are [smart casts](https://kotlinlang.org/docs/reference/typecasts.html). 

Try to initialize the var x once as String and once as Int. The Kotlin compiler is intelligent enough to cast to the respective type

```kotlin runnable
// { autofold

fun main(args: Array<String>) {
// }
    var x: Any //no special type
   
    //TODO: intialize string here
    print(x.length) // smart casting here

    //TODO: intialize int here

    print(x*2) // smart casting here
    
// { autofold
    }
// }
```


Other examples and the generall differences to Java can be found [on the kotlin website](https://kotlinlang.org/docs/reference/comparison-to-java.html)
