# Kotlin

![Kotlin](../pic/Kotlin.png)

## Checking the sample code

_My solution is basicly Java. A more  idiomatic Kotlin-like solution is needed here to show..._

```kotlin runnable
import java.util.*
fun main(args : Array<String>) {
    val input = Scanner(System.`in`)
    val m: String = input.nextLine()
    val c = arrayOf("00", "0")
    val b = StringBuilder()
    for (w in m)
        b.append(String.format("%1$" + 7 + "s", Integer.toBinaryString(w.toByte().toInt())).replace(' ', '0'))
    val a = StringBuilder()
    a.append(c[b.get(0) - '0'] + " 0")
    for (i in 1 until b.length)
        if (b.get(i) == b.get(i - 1))
            a.append("0")
        else
            a.append(" " + c[b.get(i) - '0'] + " 0")
    println(a.toString())
    // To debug: System.err.println("Debug messages...");
}
```

## Looking at the syntax

- TODO

## Other characteristics

- TODO

## Resources to check

- [Overview on Wikipedia](https://en.wikipedia.org/wiki/Kotlin_(programming_language))
- [Official tutorial](https://kotlinlang.org/docs/getting-started.html)

## Coming next...
