# Python

Sample solution in Python

```python runnable
# https://www.codingame.com/training/easy/count-as-i-count
import sys
import math

def getMollky(n, roundnum):
    if ((roundnum > 4) or (n < 2) or (n > 50)):
        return 0
    if ((n == 49) and (roundnum == 4)):
        return 0
    if ((n == 49) or (n == 50)):
        return 1
    res = 0
    i = 1
    while ((i <= 12) and (n + i <= 50)):
        if (i > 1):
            res += 2 * getMollky(n + i, roundnum + 1)
        else:
            res += getMollky(n + i, roundnum + 1)
        i = i + 1
    return res

n = int(input())
ans = getMollky(n, 0)
# Write an action using print
# To debug: print("Debug messages...", file=sys.stderr)
print(ans)
```

# Resources to check

- [Overview on Wikipedia](https://en.wikipedia.org/wiki/Python_(programming_language))
- [Official tutorial](https://docs.python.org/3/tutorial/index.html)
