# PHP

Let's start by checking our sample solution in PHP:

```php runnable
<?php
declare(strict_types=1);
// $m = stream_get_line(STDIN, 100 + 1, "\n");
$m = "CG";
const c = ['0' => '00', '1' => '0'];
$b = '';
for ($i = 0; $i < strlen($m); $i++) {
    $b .= str_pad(decbin(ord($m[$i])), 7, '0', STR_PAD_LEFT);
}
$ans = c[$b[0]] . ' 0';
for ($i = 1; $i < strlen($b); $i++) {
    if ($b[$i] == $b[$i - 1])
        $ans .= '0';
    else
        $ans .= ' ' . c[$b[$i]] . ' 0';
}
// error_log(var_export($var, true));
echo $ans, PHP_EOL;
```

Let's check this code to see the main characteristics of C#:

- `<?` PHP was originally designed as a server side script language for web pages. HTML markup and PHP code can me mixed in a file, sp `<?` denotes the start of a php section
- `declare(strict_types=1);` PHP is infamous for its type-jugling and all the weird bugs it can bring to your code. Luckily in the past years PHP moved heavily to a stronger type system including function arguments and class property type hinting, etc. I recommend starting all your code with this line to enforce stronger type checking.
- `$m = "CG";`
  + The `$` here does not denote how high PHP coder's income can be, but all varaible names start with it. It needs some getting used to (unless you came from Perl...).
  + PHP has a dynamic system. Here `$m` is assigned a string literal, so it becomes a string, but later we could simple reassign it to an integer. (Not a best practice though.)
- `const c = ['0' => '00', '1' => '0'];`
  + PHP is also infamous for its inconsistency. Here c is declared immutable by adding `const`, but that results you cannot use `$c` anymore.
  + The assigned literal data structure is PHP's very flexible `array`. It is so flexible, that this is almost all PHP has at all. Internally, it is an ordered hashmap, and you can use it as a vector, stack, queue, dictionary, map, etc. Having to use a complex data type even if you need a fixed size vector of integers is largely adds to the slowness of PHP code.
- TODO...

## Other characteristics

- TODO...

# Resources to check

- [Overview on Wikipedia](https://en.wikipedia.org/wiki/PHP)
- [Official documentation](https://www.php.net/manual/en/getting-started.php)
- [w3schools tutorial](https://www.w3schools.com/php/)
