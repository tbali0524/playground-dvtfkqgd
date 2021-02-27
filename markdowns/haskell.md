# Haskell

![Haskell](../pic/Haskell.png)

Unfortunately, this section is not ready yet as I lack the necessary skills in Haskell...

![Meme](../pic/meme_c3po.png)

## Checking the sample code

In the meantime, enjoy some Hello World!

```haskell runnable
import System.IO
import Control.Monad

main :: IO ()
main = do
    hSetBuffering stdout NoBuffering -- DO NOT REMOVE
    let m = "Hello World"
    -- hPutStrLn stderr "Debug messages..."
    print m
    return ()
```

## Looking at the syntax

- TODO

## Other characteristics

- TODO

## Resources to check

- [Overview on Wikipedia](https://en.wikipedia.org/wiki/Haskell_(programming_language))
- [Official site](https://www.haskell.org/)
- [Learn You a Haskell - tutorial](http://learnyouahaskell.com/introduction)

![Meme](../pic/meme_haskell.png)

## Coming next...

Before we move on to some more serious matters, let's focus on a language, which saw an enormous growth in popularity in the past 5+ years: **Python**!
