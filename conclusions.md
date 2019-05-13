
# Conclusion

Kotlin has been developed with a pragmatic approach and incorporates many 
"lession learned" of older languages. There is almost no downside compared
 to java, while being a modern and approachable language.

## Wait, you said "no downside to java", this sounds like a sales pitch

Ok, let me elaborate: using kotlin is overhead, plain and simple: there is another compiler
(arguably slower than java's), there is the overhead to learn a new language, and kotlin itself
will never be the "first" language on the jvm.


More about the hidden costs of Kotlin on this wonderfull [post](https://medium.com/@BladeCoder/exploring-kotlins-hidden-costs-part-1-fbb9935d9b62) on Medium.


And then there is always the possibilty to shoot oneself in the foot, with style, i.e. by using something  idiomatic but having a performance 
overhead. 


from https://craigrussell.io/2019/03/shooting-yourself-in-the-foot-while-adding-an-element-to-a-kotlin-list/


```kotlin runnable
// { autofold
  import kotlin.system.measureNanoTime

fun main(args: Array<String>) {
// }


val itemsToAdd = 5_000
val myList = mutableListOf<Int>()

val res1 = measureNanoTime {
    for (i in 1..itemsToAdd) {
        myList += i
    }
}


var myList2: List<Int> = mutableListOf()
val res2 = measureNanoTime {
    for (i in 1..itemsToAdd) {
        myList2 += i
    }
}

println("$res1 vs $res2")


// { autofold
    }
// }
```

Having said this: I am sure that the benefits outweight the drawbacks big time when usig Kotlin instead of Java. You have to introduce this new language, teach the "right" way to do stuff in Kotlin, coach the developers and reflect the used patterns and techniques.

 Kotlin, in a way, is more comparable to languages like [typescript](http://typescript.org/) 
or maybe even [c#](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/).

Innovation is taking place at a breathtaking pace, while still managing to be simple 
enough to be the "first language" to learn.

If you want to try out kotlin: [Just go ahead](https://try.kotlinlang.org), [or play with it](https://play.kotlinlang.org)