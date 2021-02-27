# C++

![C++](../pic/Cpp.png)

_The remaining sections are not ready yet, only some code snippets and tutorial links are provided._

## Checking the sample code

```C++ runnable
#include <iostream>
#include <bitset>
using namespace std;
int main()
{
    string m;
    // getline(cin, m);
    m = "CG";
    string c[2] = {"00", "0"};
    string b;
    for (auto & ch: m)
        b += bitset<7>(ch).to_string();
    string a;
    a += c[b[0] - '0'] + " 0";
    for (int i = 1; i < b.length(); i++) {
        if (b[i] == b[i - 1])
            a += "0";
        else
            a += " " + c[b[i] - '0'] + " 0";
    }
    // cerr << "Debug messages..." << endl;
    cout << a << endl;
}
```

## Looking at the syntax

- TODO

## Other characteristics

- TODO

## Resources to check

- [Overview on Wikipedia](https://en.wikipedia.org/wiki/C%2B%2B)
- [C++ Resources Network](https://www.cplusplus.com/)
- [w3schools tutorial](https://www.w3schools.com/cpp/)

## Coming next...

After the C++ section, we can go forward to _D_ :-), or we can go backwards to **C**. _U'll c which 1 I chose..._
