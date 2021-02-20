# Python

Let's start by checking our sample solution in Python:

```python runnable
import sys
c = ("00","0")
m = input()
b = ""
for w in m:
    b += bin(ord(w))[2:].zfill(7)
ans = c[int(b[0])] + " 0"
for i in range(1, len(b)):
    if (b[i] == b[i - 1]):
        ans += '0'
    else:
        ans += " " + c[int(b[i])] + " 0"
# print("debug message...", file=sys.stderr, flush=True)
print(ans)
```

Let's check this code to see the main characteristics of Python:

# Resources to check

- [Overview on Wikipedia](https://en.wikipedia.org/wiki/Python_(programming_language))
- [Official tutorial](https://docs.python.org/3/tutorial/index.html)
