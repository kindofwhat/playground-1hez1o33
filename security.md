
## Security

Kotlin is more secure than Java, mainly due to two language features

### Null safety


The following code is not possible:

```kotlin runnable
// { autofold
fun main(args: Array<String>) {
// }
    var a: String = "abc"
    a = null // compilation error
// { autofold
    }
// }
```

Variables in Kotlin are not nullable unless explicitely stated. How do we prevent a compilation error in the above piece of code?
:::Solution


Add a "?" to the value type to allow this:
```kotlin runnable
// { autofold
fun main(args: Array<String>) {
// }
    var a: String? = "abc"
    println(a)
    a = null //this is ok
    println(a)
// { autofold
}
// }
```

:::




But if you want to do something with those nullable values, you have to check for null:
(Using the `?.` operator. This is the "null safe dot operator", or "safe call operator").

==> Before running the snippet further down: what do you think is displayed?


```kotlin runnable
// { autofold
fun main(args: Array<String>) {
// }
    var a: String? = null
    println(a?.length)
// { autofold
}
// }
```
See https://kotlinlang.org/docs/reference/null-safety.html for more examples.
If you are familier with freemarker you might recognise similarites: https://freemarker.apache.org/docs/dgui_template_exp.html#dgui_template_exp_missing

### Emphasis on Immutabilty

[Shared mutable state is the root of all evil](https://henrikeichenhardt.blogspot.com/2013/06/why-shared-mutable-state-is-root-of-all.html)

Kotlin has one main constructs to prevent shared mutable state:

## val vs var keyword

```kotlin runnable
// { autofold
fun main(args: Array<String>) {
// }
    val a: String? = "abc"
    println(a)
    a = "bcd"
    println(a)
// { autofold
}
// }
```
This code fails, because it reassigns to a *val*, you would have to change above code to a var.

This also works with java, using the "final" keyword

```java runnable
//{ autofold

public class Main {

public static void main(String[] args) {
//}

    final int a = 1;
    System.out.println(a);
    a = 2;
    System.out.println(a);
    

//{ autofold
}

}
//}
```
But there are some issues with the *final* keyword, mainly that it is ambigous: it is both used to declare variables immutable and to put constraints on inheritance. Furthermore you always have to ask yourself if you really want to use a `var` in Kotlin, while in Java you have to not forget the `final` keyword



