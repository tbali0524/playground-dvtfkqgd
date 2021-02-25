# JavaScript

![JavaScript](../pic/JavaScript.png)

## Checking the sample code

``` javascript runnable
//const m = readline();
const m = 'CG', c = ['00', '0'];
let b = '';
for (const w of m)
    b += parseInt(w.charCodeAt(0)).toString(2).padStart(7, '0');

let a = c[b.charCodeAt(0) - '0'.charCodeAt(0)] + ' 0';
for (let i = 1; i < b.length; i++) {
    if (b[i] === b[i - 1])
        a += '0';
    else
        a += ' ' + c[b[i].charCodeAt(0) - '0'.charCodeAt(0)] + ' 0';
}
// console.error('Debug messages...');
console.log(a);
```

## Looking at the syntax

Let's check the above code for some characteristics of javascript (JS) syntax:

- `//...` Here we commented out the reading from input stream, and replaced it with a simple assignment.
- `const m = 'CG'`
  + JS is an interpreted language with dynamically typed variables, which means we never give a type to any of our variables. Variables can even change their underlying type during the course of the program, although it is something you should always avoid unless you have a very good reason to do so.
  + `const` means readonly and prevents `m` from being reassigned after its initialisation. It is generally a good practice to declare any variable with `const` whenever possible, as it can prevent bugs preemptively and help developpers understand the flow of the code.
  + `'CG'` is a string but can also be declared as `"CG"`, as long as your choice of quote is consistent, JS will oblige.
- `c = ["00", "0"];`
  + Since `c` is declared on the same line as `m`, it also receives the `const` modifier.
  + `[ ]` indicates an array of elements, which in this case is an array containing two strings : `00` and `0`.
  + `;` at the end of a line is optional in JS and comes down to personal preference.
- `let b = '';`
  + Opposite to `const` is `let`, which is an indication that this variable is going to see some change in your program.
  + Note that `var` is also usable instead of `let`, but it is an older version of it that is supported as a legacy.
- `for (const w of m)`
  + A for-of loop allows you to iterate through a given iterable, in this case a string, which is an iterable of chars. You can of course do the same for an array.
  + Curly braces `{ }` are optional for single statement instructions.
- `b += Number(w.charCodeAt(0)).toString(2).padStart(7, '0');` Several things are happening in this line, so let's go one by one:
  + We can concatenate strings with the `+` operator. So `+` is overloaded, meaning different things if operands are strings or integers.
  + `+=` is a shortcut for saying that b = b + somethingElse.
  + `parseInt(..)` is a function that parses a given string into a number.
  + `w.charCodeAt(0)` is a function call that returns the ASCII code of the 0th character in a string, this code is a number.
  + `.toString(2)` is another function call, that can be used on numbers to display them as a string. The `2` is an optional parameter that indicates which base we want to display the number in, in this case 2 means as binary.
  + `.padStart(7, '0')` is yet another (final) function call, that can be used on a string. It means that we want our string to be at least 7 characters long, and if it is not, then fill it with `'0'` from the left until it is. For example `101100` would become `0101100`.
- `let a = c[b.charCodeAt(0) - '0'.charCodeAt(0)] + ' 0';` the only new thing in this line is referencing a vector's elements using square brackets `[ ]`. Vectors are 0 indexed.
- `for (let i = 1; i < b.length; i++)` The typical C-style loop syntax. Since `b` is a string, we can access its length by calling its property `length`.
- `if (b[i] === b[i - 1])`
  + A straightforward equality comparison, except it is actually not. For historical reasons, the traditional `==` (equality operator) should pretty much never be used in JS, and be replaced with `===` (identity operator). If you want to learn more about it, you can read the detailed explanation here : https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators
  + The ternary operator `? :` could have been also used here.
- `console.log(a);` Writing to the console. We will need this a lot on CodinGame! :smiley:

## Other characteristics

While not directly visible from the above code snippet, there are some other important aspects of JS worth noting :

- As an interpreted language, JS needs an engine to be executed. When navigating on the web, this is done by your browser, and since this is a major part of web pages now, all those engines have been very optimized. V8 is the most used engine, as all the chromium based browsers depend on it, as well as Node.js and the applications built with Electron.
- JS uses _garbage collection_, so you don't have to manually manage memory. In fact you can't, even if you wanted to, there's no syntax or keyword that would allow you to.
- JS has a single `Number` type, no int/float/double to be seen here, all the same !
- JS can be very strong when it comes to functional programming. Functions are treated as any other objects, a principle often called _functions as first class citizens_.
- There are many advanced language features we cannot address in this intro, such as _interfaces_, _inheritance_, _delegates_, _currying_ etc.
- One of the infamous characteristics of JS is the complete freedom it gives to the developper. It is so flexible and accepting that you can write pretty much anything, from the awesome to the horrendous. To mitigate this issue and add consistency, TypeScript (TS) was created, as a superset of JS. It means your TS code is _transpiled_ into regular JS before running.
- _Generics_ are not supoorted in JS, however TS adds that feature.

## Embracing the freedom
  + TODO

## The functional way
  + TODO

## Resources to check

- [Overview on Wikipedia](https://en.wikipedia.org/wiki/JavaScript)
- [w3schools tutorial](https://www.w3schools.com/js/)

## Coming next...

So far, we have seen 2 _managed_ languages and 3 _interpreted_ languages. Now let's change gears and see what speed a _native compiler_ can bring. Entering the stage: ~~C++~~... Nah, what did you think of, it will be **Pascal**, of course! :-)
