# Groovy

![Groovy](../pic/Groovy.png)

## Checking the sample code

*Note: my solution is almost Java. A more idiomatic Groovy-like solution is needed here to show...*

```groovy runnable
inp = new Scanner(System.in)
m = inp.nextLine()
c = ["00", "0"]
b = ""
for (char w : m)
    b = b.concat(Integer.toBinaryString((int)w).padLeft(7,'0'))
a = c[(int)b.charAt(0) - (int)'0'] + " 0"
for (i = 1; i < b.length(); i++)
    if (b.charAt(i) == b.charAt(i - 1))
        a = a.concat("0")
    else
        a = a.concat(" " + c[(int)b.charAt(i) - (int)'0'] + " 0")
println(a.toString())
```

## Looking at the syntax

- TODO

## Other characteristics

- TODO

## Resources to check

- [Overview on Wikipedia](https://en.wikipedia.org/wiki/Apache_Groovy)
- [Official documentation](https://groovy-lang.org/documentation.html)

## Coming next...
