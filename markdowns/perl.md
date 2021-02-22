# Perl

![Perl](../pic/Perl.png)

## Checking the sample code

```perl runnable
use strict;
use warnings;
use 5.20.1;
select(STDOUT); $| = 1; # DO NOT REMOVE

#chomp(my $m = <STDIN>);
my $m = "CG";
my @mc = split("", $m);
my %c = (
    "0", "00",
    "1", "0"
);
my $b = "";
for my $i (0..(length($m) - 1)) {
    $b .= sprintf("%07b", ord($mc[$i]));
}
my @bc = split("", $b);
my $ans = $c{$bc[0]} . " 0";
for my $i (1..(length($b) - 1)) {
    if ($bc[$i] == $bc[$i - 1]) {
        $ans .= "0";
    } else {
        $ans .= " " . $c{$bc[$i]} . " 0";
    }
}
# To debug: print STDERR "Debug messages...\n";
print $ans . "\n";
```

## Looking at the syntax

- TODO

## Other characteristics

- TODO

## Resources to check

- [Overview on Wikipedia](https://en.wikipedia.org/wiki/Perl)
- [Official tutorial](https://www.perl.org/learn.html)

## Coming next...
