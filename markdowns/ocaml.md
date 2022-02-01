# OCaml

![OCaml](../pic/Ocaml.png)

## Checking the sample code

```OCaml
let bin_of_int d =
    if d = 0 then "0"
    else
    let rec aux acc d digit =
        if digit = 0 then acc
        else aux (string_of_int (d land 1) :: acc) (d lsr 1) (digit - 1)
    in
    String.concat "" (aux [] d 7)
in

let m = (input_line stdin) in
let c = [|"00"; "0"|] in
let b : string ref = ref "" in
for i = 0 to (String.length m) - 1 do
    b := !b ^ (bin_of_int (Char.code m.[i]));
done;
let a : string ref = ref "" in
a := c.((Char.code !b.[0]) - (Char.code '0')) ^ " 0";
for i = 1 to (String.length !b) - 1 do
    if !b.[i] = !b.[i - 1] then
        a := !a ^ "0"
    else
        a := !a ^ " " ^ c.((Char.code !b.[i]) - (Char.code '0')) ^ " 0"
done;
print_endline !a;
(* Write an answer using print_endline *)
(* To debug: prerr_endline "Debug message"; *)
```

## Looking at the syntax

- TODO

## Other characteristics

- TODO

## Resources to check

- [Overview on Wikipedia](https://en.wikipedia.org/wiki/OCaml)
- [Official tutorial](https://ocaml.org/learn/)

## Coming next...
