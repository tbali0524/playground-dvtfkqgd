# TypeScript

![TypeScript](../pic/TypeScript.png)

## Checking the sample code

```typescript
const m: string = readline();
var c: string[] = ["00", "0"];
var b: string = "";
for (let w of m)
    b = b.concat(parseInt(w.charCodeAt(0).toString()).toString(2).padStart(7, '0'));
var a: string = c[b.charCodeAt(0) - "0".charCodeAt(0)] + " 0";
for (let i = 1; i < b.length; i++) {
    if (b[i] === b[i - 1])
        a = a.concat("0");
    else
        a = a.concat(" ", c[b[i].charCodeAt(0) - "0".charCodeAt(0)], " 0");
}
console.log(a);
// To debug: console.error('Debug messages...');
```

## Looking at the syntax

- TODO

## Other characteristics

- TODO

## Resources to check

- [Overview on Wikipedia](https://en.wikipedia.org/wiki/TypeScript)
- [Official documentation](https://www.typescriptlang.org/)

## Coming next...
