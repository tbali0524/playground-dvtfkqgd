# Ruby

![Ruby](../pic/Ruby.png)

## Checking the sample code

```ruby runnable
#m = gets.chomp
m = "CG"
b = ""
m.each_byte { |w|
    b += ('%7.7s' % w.ord.to_s(2)).gsub(' ', '0')
}
c = ["00", "0"]
ans = c[b[0].to_i] + " 0"
for i in 1..b.length-1
    ans += (b[i] == b[i - 1] ? "0" : " " + c[b[i].to_i] + " 0")
end
# STDERR.puts "Debug messages..."
print ans
```

## Looking at the syntax

- TODO

## Other characteristics

- TODO
- Ruby excels at _Code Golf_. You can write really short code in it.

## Resources to check

- [Overview on Wikipedia](https://en.wikipedia.org/wiki/Ruby_(programming_language))
- [Official documentation](https://www.ruby-lang.org/en/documentation/)

![Meme](../pic/meme_ruby.png)

## Coming next...
