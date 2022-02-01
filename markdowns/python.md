# Python

![Python](../pic/Python.png)

## Checking the sample code

```python runnable
import sys
# m = input()
m = "CG"
c = ("00", "0")
b = ""
for w in m:
    b += bin(ord(w))[2:].zfill(7)
ans = c[int(b[0])] + " 0"
for i in range(1, len(b)):
    ans += '0' if b[i] == b[i - 1] else " " + c[int(b[i])] + " 0"
# print("debug message...", file=sys.stderr, flush=True)
print(ans)
```

## Looking at the syntax

Even if it is almost a line-by-line conversion of the same imperative-style solution that we saw in the C# or PHP chapters, the syntax is quite different:

- Whitespace matters! Blocks for loops and conditional statements are indented. There are no curly braces `{ }` or semicolons `;`.
- The type system is dynamic. There is not a single mention of any type names in the above code, yet we used _string_, _integer_ and a _tuple_ `( )`. There are also _lists_, _sets_, _dictionaries_ and full _OOP_ support.
- `[2:]` Slicing is a powerful and efficient tool to process only some part of a datatype such as string or list.
- Instead of the traditional `if` statement, here I show _Python_'s ternary operator, which has an unusual order of operands.
- Of course, there are much more language features. In the unlikely case you were never exposed to Python, I recommend checking out any of the huge number of tutorials on the web.

## Other characteristics

- Python is now over 30 years old, and it was quite at the sideline in popularity in its first half of existence. However, in the past decade its popularity grew tremendously, partly due to the mainstream emergence of data science.
- Python is relatively easy to learn.
- Using its high level abstractions and expressiveness, it takes less time to create a prototype solution than in most other languages.
- One of its main strengths lies in the huge selection of available libraries, especially for data science, machine learning and natural sciences. If you have finished a basic Python tutorial, you should definitely check out _numpy_, _pandas_, _matplotlib_, _scipy_, _scikit-learn_, _pytorch_, etc., just to name only a few of the most popular ones.
- It is well suited for _REPL (Read–eval–print loop)_ usage: instead of writing the code separately, you can run Python commands line-by-line and immediately see the result using (for example) _Jupyter notebook_.
- It is interpreted, so it is quite slow. Despite this, it is used extensively in machine learning, where speed DOES matter. The contradiction is resolved by the fact that most Python ML libraries are written in a fast compiled language such as _C_, so the time spent at the Python interpreter is only a fraction of the whole running time.

## Resources to check

- [Overview on Wikipedia](https://en.wikipedia.org/wiki/Python_(programming_language))
- [Official tutorial](https://docs.python.org/3/tutorial/index.html)
- [w3schools tutorial](https://www.w3schools.com/python/)

## Coming next...

So far, we have seen some _managed_, some _interpreted_ and some _functional_ languages. Now let's change gears and see what speed a _native compiler_ can bring. Entering the stage: ~~C++~~... Nah, what did you think of, it will be **Pascal**, of course! :-)
