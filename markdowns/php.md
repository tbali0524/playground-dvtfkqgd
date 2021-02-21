# PHP

## Checking the sample code

Let's start by checking our sample puzzle solution in PHP:

```php runnable
<?php
declare(strict_types=1);
// $m = stream_get_line(STDIN, 100, "\n");
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

## Looking at the syntax

Let's check this code to see the main characteristics of PHP:

- `<?php` _PHP_ was originally designed as a server side script language for web pages. _HTML_ markup and PHP code can me mixed in a file, so `<?php` denotes the start of a php section.
- `declare(strict_types=1);` PHP is infamous for its type-jugling and all the weird bugs it can bring to your code. Luckily, in the past years _PHP_ moved heavily to a stronger type system, including type hints for function arguments, return types and class properties, etc. I recommend starting all your code with this `declare` line to enforce the stronger type checking.
- `$m = "CG";`
  + The `$` here does not denote how high a PHP coder's income can be, but all variable names start with it. Well, it needs some getting used to (unless you came from _Perl_...).
  + _PHP_ has a dynamic type system. Here, `$m` is assigned a string literal, so it becomes a string, but later we could simple reassign it to an integer. (It is not the best practice to do so.)
- `const c = ['0' => '00', '1' => '0'];`
  + PHP is also infamous for its inconsistency. Here c is declared to be immutable by adding `const`, but that results, that you must not use the `$` prefix anymore.
  + The assigned literal data structure is _PHP_'s very flexible `array`. It is so flexible, that this is almost all that _PHP_ has! Internally, it is implemented as an ordered hashmap, and you can use it as a `vector`, `stack`, `queue`, `dictionary`, `map`, etc. Having to use a complex data type, even if you need just a fixed-size vector of integers, is many times an overkill, and it largely adds to the slowness of _PHP_.
- TODO...

## Other characteristics

- While not visible from the sample code above, _PHP_ supports multiple programming paradigms. Besides procedural style, it can be used in an object-oriented way. Although not really a functional language, some aspects of functional programming are well supported.
- PHP is interpreted. You can run your script without a compilation phase. This also means PHP is **SLOW**. All solo puzzles can be solved on CodinGame by choosing the right algorithm, but it does not stand a chance in a CG contests against compiled codes (_C++_, _Rust_, etc.). PHP v8.0 provides Just-In-Time compilation resulting 3-4x speedup for a typical CG puzzle code (but not for a typical web application!), unfortunately CG does not support this version yet.
- ...**TODO**

## Resources to check

- [Overview on Wikipedia](https://en.wikipedia.org/wiki/PHP)
- [Official documentation](https://www.php.net/manual/en/getting-started.php)
- [w3schools tutorial](https://www.w3schools.com/php/)

## Coming next...

Okay, I have to admit I was a bit biased towards _PHP_, because that is the language I know the most. That is why we started the exploration of interpreted languages with it, despite of the undeniable fact, that it is less fancy, than it was 10+ years ago. But now, it is time to move our focus to another language which is even older than _PHP_, but saw an enormous growth in popularity in the past 5+ years: **Python**!
