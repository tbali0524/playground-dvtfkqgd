# F#

## Checking the sample code

**TODO**: below F# sample code is not functional, so not proper tho showcase the language

```F# runnable
open System
(* let m = Console.In.ReadLine() *)
let m = "CG"
let c = [| "00"; "0" |]
let mutable b = ""
for ch in m do
    b <- b + Convert.ToString(ch |> int, 2).PadLeft(7, '0')
let mutable a = ""
a <- a + c.[(b.[0] |> int) - ('0' |> int)] + " 0"
for i = 1 to (String.length b) - 1 do
    if b.[i] = b.[i - 1] then
        a <- a + "0"
    else
        a <- a + " " + c.[(b.[i] |> int) - ('0' |> int)] + " 0"
(* eprintfn "Debug message" *)
printfn "%s" a
```

## Looking at the syntax

- TODO

## Other characteristics

- TODO

## Resources to check

- [Overview on Wikipedia](https://en.wikipedia.org/wiki/F_Sharp_(programming_language))
- [Official tutorial](https://fsharp.org/learn/index.html)

## Coming next...
