---
lang: en
layout: home
lang-ref: perl/releases
---

## Perl releases

### 5.34.0

In 5.34.0 was added new [core improvements](https://metacpan.org/pod/release/XSAWYERX/perl-5.34.0/pod/perldelta.pod):

- try/catch features;
- in qr/{,n}/ it may not to set a low scope;
- allowed spaces in {} for regex and notes like \b{}, \g{} etc;
- new way for notation of octal numbers 0odddd.

#### try/catch

```perl
use strict;
use warnings;

use feature 'try';
use feature 'say';

sub run {
    try {
        say "Hi";
        warn "I have a bad feeling!";
        say "All right for the time being";
        die "Breakage!";
        say "I did know it!"
    }
    catch ($r) {
        warn "Something was broken: $r";
        return 2;
    }

    return 5;
}

say run();
```

output:

```
perl m.pl
try/catch is experimental at m.pl line 8.
try/catch is experimental at m.pl line 15.
Hi
I have a bad feeling! at m.pl line 10.
All right for the time being
Something was broken: Breakage! at m.pl line 12.
2
```

#### qr/{,n}/

```perl
perl -E '$a="dffs"; $r=qr/f{,2}/; while ($a=~/($r)/g) { say $1 }'

ff


```

#### Spaces inside {}

```perl
perl -E '$a="dffs"; $r=qr/f{ ,  2  }/; while ($a=~/($r)/g) { say $1 }'

ff


```

#### 0odddd

```
perl -E 'say 0o013'
11
```
