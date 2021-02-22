# Java

Java is 5 years older, than C#. Actually, when C# was introduced in early 2000s, it was accused of being just an imitation of Java. The languages diverged more since that, but the similarities are still quite obvious. Therefore, this page shall be shorterm than the previous one.

## Checking the sample code

**TODO** check why does it not find Main here?

```java runnable
import java.util.*;

class Solution {

    public static void main(String args[]) {
        // Scanner in = new Scanner(System.in);
        // String m = in.nextLine();
        String m = "CG";
        String[] c = {"00", "0"};
        StringBuilder b = new StringBuilder();
        for (char w : m.toCharArray())
            b.append(String.format("%1$" + 7 + "s", Integer.toBinaryString((int)w)).replace(' ', '0'));
        StringBuilder a = new StringBuilder();
        a.append(c[b.charAt(0) - '0'] + " 0");
        for (int i = 1; i < b.length(); i++)
            if (b.charAt(i) == b.charAt(i - 1))
                a.append("0");
            else
                a.append(" " + c[b.charAt(i) - '0'] + " 0");
        // System.err.println("Debug messages...");
        System.out.println(a.toString());
    }
}
```

## Looking at the syntax

We can see similar features as in the C# sample solution, like:
* _classes_, a static method as _main_, a strong and _static type system_, _arrays_, _type casting_, _iterators_, _loops_, _conditionals_, etc. The syntax is slightly different, but I will not go into detail for these features.

Some differences:
- _Java_'s `String` is _immutable_, so `StringBuilder` class is used to append characters to the solution character by character.
- In _C#_, even the primitive types are objects. Java features wrapper classes for the same role. (e.g. `Integer` for `int`).
- And, of course, there are [many more differences](https://en.wikipedia.org/wiki/Comparison_of_C_Sharp_and_Java), which are not visible from such a short sample code, and are beyond the scope of this short introductory article.

## Other characteristics

- Both _Java_ and _C#_ are '_managed_' languages. _Java_ compiles to _Java bytecode_, which is then run on a JVM (_Java Virtual Machine_).
- By using _JIT_, their speeds fall in the same range.
- _Java_ is very popular in the enterprise application development, due to its "_write once, run anywhere_" philosophy.

## Resources to check

- [Overview on Wikipedia](https://en.wikipedia.org/wiki/Java_(programming_language))
- [w3schools tutorial](https://www.w3schools.com/java/)

## Coming next...

After checking 2 compiled, managed languages with a strong type system, let's explore some languages with a very different approach: weakly typed and interpreted! We start by looking at **PHP**!
