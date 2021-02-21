# Go

## Checking the sample code

```go runnable
package main
// import "os"
import "fmt"
// import "bufio"
import "strconv"
func main() {
    // scanner := bufio.NewScanner(os.Stdin)
    // scanner.Buffer(make([]byte, 1000000), 1000000)
    // scanner.Scan()
    // m := scanner.Text()
    m := "CG"
    var c [2]string
    c[0] = "00"
    c[1] = "0"
    var b = ""
    for i := 0; i < len(m); i++ {
        b += fmt.Sprintf("%07s", strconv.FormatInt(int64(m[i]), 2))
    }
    var a = ""
    a += c[int(b[0]) - int('0')] + " 0"
    for i := 1; i < len(b); i++ {
        if b[i] == b[i - 1] {
            a += "0"
        } else {
            a += " " + c[int(b[i]) - int('0')] + " 0"
        }
    }
    // fmt.Fprintln(os.Stderr, "Debug messages...")
    fmt.Println(a)
}
```

## Looking at the syntax

- TODO

## Other characteristics

- TODO

## Resources to check

- [Overview on Wikipedia](https://en.wikipedia.org/wiki/Go_(programming_language))
- [Official tutorial](https://golang.org/doc/tutorial/getting-started)
