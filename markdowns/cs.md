# C#

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
        string b = "";
        foreach (char ch in m)
            b += Convert.ToString((int)ch, 2).PadLeft(7, '0');
        string ans = "";
        ans += c[b[0] - (int)'0'] + " 0";
        for (int i = 1; i < b.Length; i++)
            if (b[i] == b[i - 1])
                ans += "0";
            else
                ans += " " + c[b[i] - '0'] + " 0";
        // To debug: Console.Error.WriteLine("Debug messages...");
        Console.WriteLine(ans);
    }
}
```

Let's check this code to see the main characteristics of C#:

- `using System;` C# provides an extensive standard library. Here we will use only the very basics.
- `class Solution` C# is object-oriented. Like in Java, we need to have a class to hold our code, even if we don't really use OOP.
- `static void Main(string[] args)` Every executable program needs a Main method which will be called when the program is started.
- `{` C# has curly braces to construct a code block, similary C and many other languages. Whitespaces are usually have no meaning.
- `//...` Here we commented out the reading from input stream, and replaced it with a simple assignment.
- `string m = "CG";` C# has static and strong typing. Here m is declared as a string and it will always be a string in this program.

# For further study

- [Overview on Wikipedia](https://en.wikipedia.org/wiki/C_Sharp_(programming_language))
- [Official documentation](https://docs.microsoft.com/en-us/dotnet/csharp/)
