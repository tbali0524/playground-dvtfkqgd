# C

## Checking the sample code

```C runnable
#include <stdio.h>
#include <stdbool.h>
int main()
{
    char m[101];
    // fgets(m, 101, stdin);
    strcpy(m, "CG");
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
    // fprintf(stderr, "Debug messages...\n");
    printf("%s\n", a);
    return 0;
}
```

## Looking at the syntax

- TODO

## Other characteristics

- TODO

## Resources to check

- [Overview on Wikipedia](https://en.wikipedia.org/wiki/C_(programming_language))
