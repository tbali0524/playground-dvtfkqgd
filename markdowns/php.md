# PHP

![PHP](../pic/PHP.png)

## Checking the sample code

Our sample puzzle solution looks like this in PHP:

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

- `<?php` _PHP_ was originally designed as a server side script language for web pages. _HTML_ markup and PHP code can me mixed in a file, so `<?php` denotes the start of a php section (and `?>` would mark the end of it, but we can omit it as our full script is in PHP).
- `declare(strict_types=1);` PHP is infamous for its type-jugling and all the weird bugs it can bring to your code. Luckily, in the past years _PHP_ moved heavily towards a stronger type system, including type hints for function arguments, return types and class properties, etc. Not to break backward compatibility, this is fully _opt-in_.  I recommend starting all your code with this `declare` line to enforce the stronger type checking, and to use all the type declaration facilities.
- After _C#'s_ `using` and _Java's_ `import` you might miss some library references here. PHP _does_ have an extensive library, but exactly what is available for the coder is installation-specific. In the sample code, `strlen`, `str_pad`, `decbin`, etc. are all library functions.
- `$m = "CG";`
  + The `$` here does not denote how much a professional PHP coder earns, but all variable names start with it. Yes, it needs some getting used to (unless you came from _Perl_...).
  + _PHP_ has a dynamic type system. Here, `$m` is assigned a string literal, so it becomes a string, but later we could simple reassign it to an integer. (However, to do so is not the best practice.)
- `const c = ['0' => '00', '1' => '0'];`
  + _PHP_ is also infamous for its inconsistency. Here c is declared to be immutable by adding `const`, but that results that you must not use the `$` prefix anymore.
  + The assigned literal data structure is _PHP_'s very flexible `array`. It is so flexible, that this is almost all that PHP has to offer... Internally, it is implemented as a hashmap with the key order preserved. You can use it as a `vector`, `stack`, `queue`, `dictionary`, `map`, etc. Having to use such a complex data type, even if you would need just a fixed-size array of integers, is in many cases an overkill. This design decision largely adds to the slowness of PHP.
- Why are there no parentheses around the parameters passed to `echo`? Well, it could have been written as `echo($ans)`, but `echo` is not a normal library function, it is a language construct.
  + `PHP_EOL` is just an OS-dependent constant for the endline, so CR + LF in Windows and LF in Linux.

## Other characteristics

- While not visible from the sample code above, _PHP_ supports multiple programming paradigms.
  + Besides the procedural style, it can be used in an object-oriented way. Some standard libraries (such as database access) have even dual interfaces: you can use them either by calling simply functions or by instantiating classes and calling methods.
  + The most popular PHP web frameworks such as _Laravel_ or _Symfony_ are all written in OOP.
  + Although not really a functional language, some aspects of functional programming are also well supported. (Higher order functions, lambda functions, etc.).
- PHP is _interpreted_. You can run your script without a separate compilation phase. This also results that PHP is quite slow. Although all solo puzzles can be solved on `CodinGame` by choosing the right algorithm, but PHP does not stand much chance in a CG contest against compiled codes (e.g. _C++_, _Rust_, etc.). `PHP v8.0` provides _Just-In-Time_ compilation, resulting 3-5x speedup for a typical CG puzzle code (but not for a typical web application!), unfortunately, at the time of writing this, CG does not support this version yet.

## Resources to check

- [Overview on Wikipedia](https://en.wikipedia.org/wiki/PHP)
- [Official documentation](https://www.php.net/manual/en/getting-started.php)
- [w3schools tutorial](https://www.w3schools.com/php/)

![Meme](../pic/meme_php.png)

## Coming next...

Okay, I have to admit I was a bit biased towards _PHP_, because that is the language I know the most. That is why we started the exploration of interpreted languages with it, despite of the undeniable fact that it is perceived as less fancy than it was 10+ years ago. My personal opinion is still that it is much better than its fame.

Now let's check another weakly typed, interpreted language, which became the _de-facto_ ruler of web front-ends: **JavaScript**!
