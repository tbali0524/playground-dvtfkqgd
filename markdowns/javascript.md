# JavaScript

![JavaScript](../pic/JavaScript.png)

## Checking the sample code

``` javascript runnable
//const m = readline();
const m = "CG";
var c = ["00", "0"];
var b = "";
for (let w of m)
    b = b.concat(parseInt(w.charCodeAt()).toString(2).padStart(7, '0'));
var a = c[b.charCodeAt() - "0".charCodeAt()] + " 0";
for (let i = 1; i < b.length; i++) {
    if (b[i] === b[i - 1])
        a = a.concat("0");
    else
        a = a.concat(" ", c[b[i].charCodeAt() - "0".charCodeAt(0)], " 0");
}
// console.error('Debug messages...');
console.log(a);
```

## Looking at the syntax

- TODO

## Other characteristics

- TODO

## Resources to check

- [Overview on Wikipedia](https://en.wikipedia.org/wiki/JavaScript)
- [w3schools tutorial](https://www.w3schools.com/js/)

## Coming next...

So far, we have seen 2 _managed_ languages and 3 _interpreted_ languages. Now let's change gears and see what speed a _native compiler_ can bring. Entering the stage: ~~C++~~... Nah, what did you think of, it will be **Pascal**, of course! :-)
