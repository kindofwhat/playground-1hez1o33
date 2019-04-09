
# Conclusion

Kotlin has been developed with a pragmatic approach and incorporates many 
"lession learned" of older languages. There is almost no downside compared
 to java, while being a modern and approachable language.

## Wait, you said "no downside to java", this sounds like a sales pitch

Ok, let me elaborate: using kotlin is overhead, plain and simple: there is another compiler
(arguably slower than java's), there is the overhead to learn a new language, and kotlin itself
will never be the "first" language on the jvm. And then there is always the possibilty to
shoot oneself in the foot, with style, i.e. by using something  idiomatic but having a performance 
overhead. 

from https://craigrussell.io/2019/03/shooting-yourself-in-the-foot-while-adding-an-element-to-a-kotlin-list/
//val itemsToAdd = 500_000

// val list = mutableListOf<Int>()
val tMutableList = measureNanoTime {
    val list = mutableListOf<Int>()
    for (i in 1..itemsToAdd) {
        list += i
    }
}
Timber.i("Using += on `MutableList<Int>` took ${TimeUnit.NANOSECONDS.toMillis(tMutableList)}ms")


// var list: List<Int> = mutableListOf()
val t = measureNanoTime {
    var list: List<Int> = mutableListOf()
    for (i in 1..itemsToAdd) {
       list += i
    }
}

More about this on this wonderfull [post](https://medium.com/@BladeCoder/exploring-kotlins-hidden-costs-part-1-fbb9935d9b62) on Medium.

Having said this.

 
 
 
 Kotlin, in a way, is more comparable to languages like [typescript](http://typescript.org/) 
or maybe even [c#](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/).

Innovation is taking place at a breathtaking pace, while still managing to be simple 
enough to be the "first language" to learn.

If you want to try out kotlin: [Just go ahead](https://try.kotlinlang.org)