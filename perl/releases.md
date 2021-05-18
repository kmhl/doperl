## Выпуски Перла

### 5.34.0

В 5.34.0, который выйдет в ближайшее
[время](https://metacpan.org/pod/release/XSAWYERX/perl-5.34.0-RC2/pod/perldelta.pod)
были добавлены новые улучшения ядра:

- появились try/catch области;
- в qr/{,n}/ нижнюю границу можно не указывать;
- возможность использовать пробелы внути {} для отыскивающих выражений или
  записей вида \b{}, \g{} и т.д;
- новый способ указания восьмиричных чисел 0odddd.

#### try/catch

```perl
use strict;
use warnings;

use feature 'try';
use feature 'say';

sub run {
    try {
        say "Привет";
        warn "Чую неладное!";
        say "Пока всё хорошо";
        die "Поломка!";
        say "Я так и знал!"
    }
    catch ($r) {
        warn "Что-то сломалось: $r";
        return 2;
    }

    return 5;
}

say run();
```

вывод:

```
perl m.pl
try/catch is experimental at m.pl line 8.
try/catch is experimental at m.pl line 15.
Привет
Чую неладное! at m.pl line 10.
Пока всё хорошо
Что-то сломалось: Поломка! at m.pl line 12.
2
```

#### qr/{,n}/

```perl
perl -E '$a="dffs"; $r=qr/f{,2}/; while ($a=~/($r)/g) { say $1 }'

ff


```

#### Пробелы в {}

```perl
perl -E '$a="dffs"; $r=qr/f{ ,  2  }/; while ($a=~/($r)/g) { say $1 }'

ff


```

#### 0odddd

```
perl -E 'say 0o013'
11
```
