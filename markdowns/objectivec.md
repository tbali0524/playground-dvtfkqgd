# Objective-C

![Objective-C](../pic/Objective-C.png)

## Checking the sample code

```c
#include <Foundation/Foundation.h>
int main(int argc, const char * argv[]) {
    char m[101];
    scanf("%[^\n]", m);
    bool b[800];
    int blen = 0;
    for (int i = 0; i < strlen(m); i++)
    {
        int digit =  m[i];
        if (digit != 10)
            for (int j = 6; j >= 0; j--) {
                if ((digit >> j) & 1) {
                    b[blen++] = true;
                }
                else {
                    b[blen++] = false;
                }
            }
    }
    char a[2000];
    if (b[0])
        strcat(a, "0");
    else
        strcat(a, "00");
    strcat(a, " 0");
    for (int i = 1; i < blen; i++)
        if (b[i] == b[i - 1])
            strcat(a, "0");
        else
        {
            strcat(a, " ");
            if (b[i])
                strcat(a, "0");
            else
                strcat(a, "00");
            strcat(a, " 0");
        }
    printf([@"%s\n" UTF8String], a);
}
// To debug: fprintf(stderr, [@"Debug messages\n" UTF8String]);
```

## Looking at the syntax

- TODO

## Other characteristics

- TODO

## Resources to check

- [Overview on Wikipedia](https://en.wikipedia.org/wiki/Objective-C)

## Coming next...
