# Lua

![Lua](../pic/Lua.png)

## Checking the sample code

Seems to be unsupported on tech.io...

## Looking at the syntax

```lua
function Dec2Bin(dec)
  local result = ""
  repeat
        local divres = dec / 2
        local int, frac = math.modf(divres)
        dec = int
        result = math.ceil(frac) .. result
  until dec == 0
  local StrNumber
  StrNumber = string.rep("0", 7 - #result) .. result
  return StrNumber
end

m = io.read()
c = {"00", "0"}
b = ""
for i = 1, string.len(m) do
    b = b .. Dec2Bin(string.byte(m, i))
end
a = c[string.byte(string.sub(b, 1, 1)) - string.byte("0") + 1] .. " 0"
for i = 2, string.len(b) do
    if (string.sub(b, i, i) == string.sub(b, i - 1, i - 1)) then
        a = a .. "0"
    else
        a = a .. " " .. c[string.byte(b, i) - string.byte("0") + 1] .. " 0"
    end
end
print(a)
-- To debug: io.stderr:write("Debug message\n")
```

## Other characteristics

- TODO

## Resources to check

- [Overview on Wikipedia](https://en.wikipedia.org/wiki/Lua_(programming_language))
- [Official tutorial](https://www.lua.org/start.html)

## Coming next...
