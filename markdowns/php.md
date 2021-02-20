# Python

Sample solution in Python

```php runnable
<?php
// https://www.codingame.com/training/easy/count-as-i-count

function getMollky(int $n, int $round): int
{
    if (($round > 4) or ($n < 2) or ($n > 50))
        return 0;
    if (($n == 49) and ($round == 4))
        return 0;
    if (($n == 49) or ($n == 50))
        return 1;
    $res = 0;
    $i = 1;
    while (($i <= 12) and ($n + $i <= 50))
    {
        if ($i > 1)
            $res += 2 * getMollky($n + $i, $round + 1);
        else
            $res += getMollky($n + $i, $round + 1);
        $i++;
    }
    return $res;
}

fscanf(STDIN, "%d", $n);
$ans = getMollky($n, 0);
// Write an action using echo(). DON'T FORGET THE TRAILING \n
// To debug (equivalent to var_dump): error_log(var_export($var, true));
echo $ans . "\n";
```

# Resources to check

- [Overview on Wikipedia](https://en.wikipedia.org/wiki/PHP)
- [Official documentation](https://www.php.net/manual/en/getting-started.php)
