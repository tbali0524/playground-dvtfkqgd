# PHP

Let's start by checking our sample solution in PHP:

```php runnable
<?php
declare(strict_types=1);
$c = ['0' => '00', '1' => '0'];
// $m = stream_get_line(STDIN, 100 + 1, "\n");
$m = "CG";
$b = '';
for ($i = 0; $i < strlen($m); $i++) {
    $b .= str_pad(decbin(ord($m[$i])), 7, '0', STR_PAD_LEFT);
}
$ans = $c[$b[0]] . ' 0';
for ($i = 1; $i < strlen($b); $i++) {
    if ($b[$i] == $b[$i - 1])
        $ans .= '0';
    else
        $ans .= ' ' . $c[$b[$i]] . ' 0';
}
// To debug (equivalent to var_dump): error_log(var_export($var, true));
echo $ans, PHP_EOL;
```

Let's check this code to see the main characteristics of C#:

- `<?` PHP was originally designed as a server side scrpit language for web pages. HTML markup and PHP code can me mixed in a file, sp `<?` denotes the start of a php section
- `declare(strict_types=1);` PHP is infamous for its type-jungling.

# Resources to check

- [Overview on Wikipedia](https://en.wikipedia.org/wiki/PHP)
- [Official documentation](https://www.php.net/manual/en/getting-started.php)
