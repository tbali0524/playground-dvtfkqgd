# Java

Java is 5 years older then C#. When C# was introduced in early 2000s, it was accused of being just an imitation of Java. The languages diverged much more since, but the similarities are still quite obvious.

## Checking the sample code

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

We can see similar features as in the C# sample solution, like classes, a static method for main, strong and static type system, arrays, type casting, iterators, loops, conditionals, etc. with just a slightly different syntax, so I will not go in detail.

Some differences:
- _Java_'s `String` is _immutable_, so `StringBuilder` class is used to append characters to the solution.
- In C# even the primitive types are objects. Java features wrapper classes for the same role. (e.g. `Integer` for `int`).
- And of course there are [many other differences](https://en.wikipedia.org/wiki/Comparison_of_C_Sharp_and_Java) which are not visible from such short sample code, and are beyond the scope of this introductory article.

## Other characteristics

- Both _Java_ and _C#_ are 'managed' languages. Java compiles to Java bytecode which is then run on a JVM (_Java Virtual Machine_). Through JIT, their speed falls in the same range.
- _Java_ is very popular in the enterprise application development, due to its 'write once, run anywhere' philosophy.

## Resources to check

- [Overview on Wikipedia](https://en.wikipedia.org/wiki/Java_(programming_language))
- [w3schools tutorial](https://www.w3schools.com/java/)

## Coming next...

After checking two compiled, managed languages with strong type systems, let's check some languages with a very different approach: weakly typed and interpreted! We start by looking at **PHP**!
