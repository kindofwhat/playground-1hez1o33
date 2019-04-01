# Why Kotlin >> Java

3 Reasons

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

How to prevent compilation error here?
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
(Using the `?.` operator. This is the "null safe dot operator", or "safe call operator")

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
See https://kotlinlang.org/docs/reference/null-safety.html for more examples

### Emphasis on Immutabilty

[Shared mutable state is the root of all evil](https://henrikeichenhardt.blogspot.com/2013/06/why-shared-mutable-state-is-root-of-all.html)

Kotlin has 2 main constructs to prevent shared mutable state:

1. val vs var keyword

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
package com.yourself;

import com.pizzapi.*;

public class Pizza {

public static void orderPizza() throws PizzaException {
//}

    final Integer a = 1;
    System.out.println(a);
    a = 2;
    System.out.println(a);
    

//{ autofold
}

}
//}
```
