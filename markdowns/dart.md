# Dart

![Dart](../pic/Dart.png)

## Checking the sample code

```dart runnable
import 'dart:io';
import 'dart:math';
void main() {
    // String m = stdin.readLineSync();
    String m = "CG";
    var c = {0 : "00", 1: "0"};
    String b = "";
    for(int i = 0; i < m.length; i++) {
        b = b + m.codeUnitAt(i).toRadixString(2).padLeft(7, "0");
    }
    String a = "";
    a += c[b[0].codeUnits.first - "0".codeUnits.first] + " 0";
    for (int i = 1; i < b.length; i++)
        if (b[i] == b[i - 1])
            a += "0";
        else
            a += " " + c[b.codeUnitAt(i) - "0".codeUnits.first] + " 0";
    print(a);
}
```

## Looking at the syntax

- TODO

## Other characteristics

- TODO

## Resources to check

- [Overview on Wikipedia](https://en.wikipedia.org/wiki/Dart_(programming_language))
- [Official tutorial](https://dart.dev/overview)

## Coming next...
