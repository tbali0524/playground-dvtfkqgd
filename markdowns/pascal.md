# Pascal

![Pascal](../pic/Pascal.png)

Believe it or not, Pascal was in the top 3 languages when I was a teenager. Let's dive in!

## Checking the sample code

_...except, we cannot: it seems to be unsupported on_ `Tech.io`_..._

Which is understandable, given the fact, that it fell out of the top 100 languages by popularity long time ago.

So, instead of running a `Chuck Norris` sample solution in Pascal, let me show you a screenshot from `Borland Pascal 7.0`, an _IDE_ that was well ahead of its time 25+ years ago:

![Borland Pascal](../pic/borlandpascal.jpg)

While we cannot run it on `Tech.io` we can still check the  source code of the sample puzzle solution. It is rather long for such a short puzzle...

```pascal
program Answer;
{$H+}
uses sysutils, classes, math, StrUtils;

// Helper to read a line and split tokens
procedure ParseIn(Inputs: TStrings);
var Line : string;
begin
    readln(Line);
    Inputs.Clear;
    Inputs.Delimiter := ' ';
    Inputs.DelimitedText := Line;
end;

function decimalToBinary(a: Integer): String;
var
    d: Integer;
    str: String;
Begin
    str:='';
    while a>0 do
    begin
        d := a mod 2;
        str := concat(IntToStr(d), str);
        a := a div 2;
    end;
    decimalToBinary := str;
End;

var
    m, b, a : String;
    Inputs: TStringList;
    c : Array[0..1] of String;
    i, j: Integer;
begin
    Inputs := TStringList.Create;
    readln(m);
    c[0] := '00';
    c[1] := '0';
    b := '';
    for j := 1 to Length(m) do
    begin
        b := b + AddChar('0', decimalToBinary(Ord(m[j])), 7);
    end;
    a := '';
    a := a + c[Ord(b[1]) - Ord('0')] + ' 0';
    for i := 2 to Length(b) do
    begin
        if (b[i] = b[i - 1]) then
            a := a + '0'
        else
            a := a + ' ' + c[Ord(b[i]) - Ord('0')] + ' 0';
    end;
    writeln(a);
    flush(StdErr); flush(output); // DO NOT REMOVE
end.
// To debug: writeln(StdErr, 'Debug messages...');
```

## Looking at the syntax

While I used to know _Pascal_ "inside-out", I admit that I have largely forgotten it, so I will skip going into more details here.

## Resources to check

- [Overview on Wikipedia](https://en.wikipedia.org/wiki/Pascal_(programming_language))
- Official tutorial: _NO, trust me, no-one is learning to code in Pascal nowadays..._
- But if you insist, you can check out [Free Pascal Compiler](https://www.freepascal.org/docs.html)

## Coming next...

After this short detour, let's continue with a language, that really stood the test of time: **C++**!
