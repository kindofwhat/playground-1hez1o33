# Integration with Java

Kotlin integrates very well with Java:

* Within IntelliJ, you can choose to convert one Java class after the other
 (doesn't work too well, although)
* The only requirement to have Kotlin ready is a 1.8 JVM
* Integration with Maven is seamless


# Integration with JavaScript

Javascript is a first class [runtime](https://kotlinlang.org/docs/tutorials/javascript/kotlin-to-javascript/kotlin-to-javascript.html) for Kotlin.
This allows for interessting scenarios:

* Kotlin could be used to define objects which are created and consumed both in the browser and on the backend.
* Kotlin can make use of the  [ts2kt](https://github.com/Kotlin/ts2kt) TypeScript-> Kotlin converter to create Kotlin artifacts out of Typescript definitions

# Native Integration
[Kotlin Native](https://kotlinlang.org/docs/reference/native-overview.html) is the initiative to create a version of Kotlin runnable on all "important" platforms like iOs, Android, and also WebAssembly.

