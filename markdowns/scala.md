# Scala

![Scala](../pic/Scala.png)

## Checking the sample code

```scala runnable
import scala.io.StdIn._

object Main extends App {
    // val m = readLine
    val m = "CG"
    val c = List("00", "0")
    var b = ""
    for (i <- 0 until m.length) {
        b += m.charAt(i).toBinaryString.reverse.padTo(7, '0').reverse
    }
    var a = ""
    a += c(b.charAt(0) - '0'.toInt) + " 0"
    for (i <- 1 until b.length) {
        if (b.charAt(i) == b.charAt(i - 1)) {
            a += "0"
        } else {
            a += " " + c(b.charAt(i) - '0'.toInt) + " 0"
        }
    }
    // Console.err.println("Debug messages...")
    println(a)
}
```

## Looking at the syntax

- TODO

## Other characteristics

- TODO

## Resources to check

- [Overview on Wikipedia](https://en.wikipedia.org/wiki/Scala_(programming_language))

## Coming next...
