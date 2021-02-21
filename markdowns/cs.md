# C#

## Checking the sample code

Let's start by checking our sample solution in C#:

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
- `class Solution` C# is object-oriented. Like in Java, we need to have a class to hold our code, even if we don't really use OOP.
- `static void Main(string[] args)` Every executable program needs a Main method, which will be called, when the program is started.
- `{` C# has curly braces to construct a code block, similarly to C and many other languages. Whitespaces are usually have no meaning.
- `//...` Here we commented out the reading from input stream, and replaced it with a simple assignment.
- `string m = "CG";` C# has a static and strong type system. `m` is declared as a string and it cannot change its type in this program. Also note that semicolon `;` ends each statement.
- `string[] c = new[2] {"00", "0"};` We have a wide range of data structures. `c` is declared as a vector holding 2 strings, and it is initialized with some string literals.
- `var b = "";` Didn't we forget here declaring the type? No, because of type inference the compiler can deduce from the assignment that b must be a string.
- `foreach (char ch in m)` we can simply iterate through the characters of a string. Also note that the curly braces `{` and `}` can be omitted because we use only a single statement within the loop.
- `b += Convert.ToString((int)ch, 2).PadLeft(7, '0');` Several things are happening in this line, so let's go one by one:
  + We can concatenate strings with the `+` operator. So `+` is overloaded, meaning different things if operands are strings or integerers. There is a shortcut `+=` for the compination of an operator and an assignment.
  + We can explicitly cast between compatible types: `(int)ch` simply gets the ascii code of the character.
  + `Convert` is a class in the standard library (remember the `using System;` line above). Its `ToString` method can be referenced by dot `.`. In OOP even a simple string is an object. `ToString()` returns a string, so we can immediately invoke the string class's `PadLeft()` method on the result.
  + While string literals use double quotes `"`, character literals are arked with single one `'`.
- `string ans = c[b[0] - (int)'0'] + " 0";` the only new thing in this line is referencing a vector's elements using square brackets `[ ]`. Vectors are 0 indexed.
- `for (int i = 1; i < b.Length; i++)` The typical C-style loop syntax. As a string is an object we get its length by accessing its `Length` property and not by a function call.
- `if (b[i] == b[i - 1])` the straight-forward conditional statement, using an comparison operator `==` in the boolean exprfession.
- `Console.WriteLine(ans);` Writing to the console. We will need this a lot on CodinGame! :-)

## Other characteristics

While not directly visible from the above code snippet, there are some other aspects of C# worth noting even in such a short intro:

- C# is compiled to an intermediate representation, which will be run by a special virtual machine (Common Language Runtime). Such managed code provides advantages preventing many type of coding bugs.
- Just-in-time compilation further improves performance. C# code runs still slightly slower than native compiled code such as C++ or Rust, but much faster than interpreted languages such as Python or PHP.
- C# is now cross platform. Although developed by Microsoft, it is available not only for Windows. It also became an ECMA standard.
- C# uses garbage collection
- C# is a multi-paradigm languages. While its design is heavily OOP focused, you can use functional programming style.
- There are many advanced language features we cannot address in this intro, such us generics, attributes, delegates, LINQ, etc.

# For further study

- [Overview on Wikipedia](https://en.wikipedia.org/wiki/C_Sharp_(programming_language))
- [Official documentation](https://docs.microsoft.com/en-us/dotnet/csharp/)
- [w3schools tutorial](https://www.w3schools.com/cs/)
