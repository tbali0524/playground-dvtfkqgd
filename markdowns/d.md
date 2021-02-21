# D

## Checking the sample code

```d runnable
import std;
void main()
{
    string m = readln.chomp;
    string[] c = new string[2];
    c[0] = "00";
    c[1] = "0";
    char[] b;
    for (int i = 0; i < m.length; i++) {
        b ~= format("%07b", m[i]);
    }
    char[] a;
    a ~= c[b[0] - 48] ~ " 0";
    for (int i = 1; i < b.length; i++) {
        if (b[i] == b[i - 1]) {
            a ~= "0";
        } else {
            a ~= " " ~ c[b[i] - 48] ~ " 0";
        }
    }
    // stderr.writeln("Debug messages...");
    writeln(a);
}
```

## Looking at the syntax

- TODO

## Other characteristics

- TODO

# Resources to check

- [Overview on Wikipedia](https://en.wikipedia.org/wiki/D_(programming_language))
- [Official tutorial](https://tour.dlang.org/)
