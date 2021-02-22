# C#

Let's start our journey by visiting **C#**. It is not the most-used language as of today, but provides modern features, and is used widely in enterprise application development projects.

## Checking the sample code

Let's see our sample puzzle solution in C#. It is a traditional, imperative programming style approach.

```C# runnable
using System;
using System.IO;
class Solution
{
    static void Main(string[] args)
    {
        // string m = Console.ReadLine();
        string m = "CG";
        string[] c = new string[2] {"00", "0"};
        var b = "";
        foreach (char ch in m)
            b += Convert.ToString((int)ch, 2).PadLeft(7, '0');
        string ans = c[b[0] - (int)'0'] + " 0";
        for (int i = 1; i < b.Length; i++) {
            if (b[i] == b[i - 1])
                ans += "0";
            else
                ans += " " + c[b[i] - '0'] + " 0";
        }
        // Console.Error.WriteLine("Debug messages...");
        Console.WriteLine(ans);
    }
}
```

## Looking at the syntax

Let's check the above code for some characteristics of C# syntax:

- `using System;` C# provides an extensive standard library, that is split to several namespaces. Here we will use only the very basics, but we still need to reference them.
- `class Solution` C# is object-oriented. Like in _Java_, we need to have a class to hold our code, even if we don't really use OOP.
- `static void Main(string[] args)` Every executable program needs a Main method, which will be called, when the program is started.
- `{` C# has curly braces to construct a code block, similarly to _C_ and many other languages. Whitespaces are usually have no meaning.
- `//...` Here we commented out the reading from input stream, and replaced it with a simple assignment.
- `string m = "CG";`
  + C# has a static and strong type system. `m` is declared as a string and it cannot change its type in this program.
  + Also note, that semicolon `;` ends each statement.
- `string[] c = new string[2] {"00", "0"};` We have a wide range of available data structures. `c` is declared as a array (vector) holding 2 strings, and it is initialized with some string literals.
- `var b = "";` Didn't we forget here declaring the type? No, because of type inference the compiler can deduce from the assignment that b must be a string.
- `foreach (char ch in m)`
  + we can simply iterate through the characters of a string. `foreach` is available for all iterable data structures.
  + Also note, that the curly braces `{` and `}` can be omitted because we use only a single statement within the loop.
- `b += Convert.ToString((int)ch, 2).PadLeft(7, '0');` Several things are happening in this line, so let's go one by one:
  + We can concatenate strings with the `+` operator. So `+` is overloaded, meaning different things if operands are strings or integers.
  + There is a shortcut for the combination of an operator and an assignment (here: `+=`).
  + We can explicitly cast between compatible types: `(int)ch` simply gets the ascii code of the character.
  + `Convert` is a class in the standard library (remember the `using System;` line above?). Its `ToString` method can be referenced by dot `.`. In true OOP even a simple string is an object. `ToString()` returns a string, so we can immediately invoke the string class' `PadLeft()` method on the result.
  + While string literals use double quotes `"`, character literals are marked with single one `'`.
- `string ans = c[b[0] - (int)'0'] + " 0";` the only new thing in this line is referencing a vector's elements using square brackets `[ ]`. Vectors are 0 indexed.
- `for (int i = 1; i < b.Length; i++)` The typical C-style loop syntax. As a string is an object, we get its length by accessing its `Length` property, and not by a function call as for example `strlen()` in C.
- `if (b[i] == b[i - 1])`
  + The conditional statement is quite straight-forward, using a comparison operator `==` in the boolean expression.
  + The ternary operator `? :` could have been also used here.
- `Console.WriteLine(ans);` Writing to the console. We will need this a lot on CodinGame! :smiley:

## Other characteristics

While not directly visible from the above code snippet, there are some other important aspects of C# worth noting:

- C# is compiled to an intermediate representation, which will be run by a special virtual machine (_Common Language Runtime_). Such managed code provides lot of advantages, like preventing many type of coding bugs.
- _Just-In-Time_ compilation further improves performance. C# code runs still slightly slower than a native compiled code (such as _C++_ or _Rust_), but still much faster than an interpreted language (such as _Python_ or _PHP_).
- C# is now cross platform. Although developed by _Microsoft_, it is available not only for _Windows_. It also became an _ECMA standard_.
- C# uses _garbage collection_, so you don't have to bother too much about memory management.
- There are many advanced language features we cannot address in this intro, such us _generics_, _attributes_, _delegates_, _LINQ_, etc.

## Checking a different approach

C# is a multi-paradigm language. While its design is heavily OOP focused, you can use it in procedural or functional style. As an illustration, let's revisit the `Chuck Norris` puzzle in a different way!\
(Contributed by [Djoums](https://www.codingame.com/profile/f0b5a892e52b5ec167931b7bdf52eb982136521)):

```C# runnable
using System;
using System.Linq;
using System.Text.RegularExpressions;
public static class Solution
{
    // Once again, Console.ReadLine() is replaced weith "CG" contant string for the tech.io playground only.
    public static void Main() =>
        Console.WriteLine(string.Join(" ", new Regex(@"(.)\1*")
            .Matches(string.Join("", "CG".Select(c => Convert.ToString(c, 2).PadLeft(7, '0'))))
            .Select(match => (match.Value[0] == '0' ? "00 " : "0 ") + new string('0', match.Value.Length))));
}
```

- We can see the `fluent interface` in action here: Methods can be chained to build a more complex query.
- A `Regex` (regular expression) is a very concise and efficient way for string manipulation. Its main disadvantage is that the resulting code is hard to read/understand without checking the regex pattern.
- `new string(...)` Constructors are overloaded. Here, we create a string by repeating a character by a specified amount.
- `=>` A _lambda expression_ is used to create an anonymous function, that can be passed directly to a method as an argument.

## For further study

- [Overview on Wikipedia](https://en.wikipedia.org/wiki/C_Sharp_(programming_language))
- [Official documentation](https://docs.microsoft.com/en-us/dotnet/csharp/)
- [w3schools tutorial](https://www.w3schools.com/cs/)

## Coming next...

After C#, let's quickly check another, quite similar language: **Java**!
