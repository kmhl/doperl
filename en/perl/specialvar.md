---
lang: en
layout: home
lang-ref: perl/specialvar
---

## Special variables in Perl

### General variables

* $LIST\_SEPARATOR, $"
* $a, $b
* %ENV
* $SYSTEM\_FD\_MAX, $^F
* @F
* $INPLACE\_EDIT, $^I
* $^M
* $BASETIME, $\^T

##### Subroutines and key calls

* $ARG, $\_
* @ARG, @\_

##### Modules

* @INC
* %INC
* @ISA

##### Signals

* %SIG

##### Running process

* $PROCESS\_ID, $PID, $$
* $PROGRAM\_NAME, $0

##### Information

* $EXECUTABLE\_NAME, $^X
* $OSNAME, $^O
* $PERL\_VERSION, $^V
* $OLD\_PERL\_VERSION, $]

##### Users and groups

* $REAL\_GROUP\_ID, $GID, $(
* $EFFECTIVE\_GROUP\_ID, $EGID, $)
* $REAL\_USER\_ID, $UID, $<
* $EFFECTIVE\_USER\_ID, $EUID, $>
* $SUBSCRIPT\_SEPARATOR, $SUBSEP, $;


### Regular expressions

* $1, $2, $3 …
* @{^CAPTURE}
* $MATCH, $&
* ${^MATCH}
* $PREMATCH, $`
* ${^PREMATCH}
* $POSTMATCH, $'
* ${^POSTMATCH}
* $LAST_PAREN_MATCH, $+
* $LAST_SUBMATCH_RESULT, $^N
* @LAST_MATCH_END, @+
* %{^CAPTURE}, %LAST_PAREN_MATCH, %+
* @LAST_MATCH_START, @-
* %{^CAPTURE_ALL}, %-
* $LAST_REGEXP_CODE_RESULT, $^R
* ${^RE_COMPILE_RECURSION_LIMIT}
* ${^RE_DEBUG_FLAGS}
* ${^RE_TRIE_MAXBUF}

### Files

* $ARGV
* @ARGV
* ARGV
* ARGVOUT
* $OUTPUT_FIELD_SEPARATOR, $OFS, $,
* $INPUT_LINE_NUMBER, $NR, $.
* $INPUT_RECORD_SEPARATOR, $RS, $/
* $OUTPUT_RECORD_SEPARATOR, $ORS, $\
* $OUTPUT_AUTOFLUSH, $\|
* ${^LAST_FH}

### Formats

* **$ACCUMULATOR, $^A** -- internal variable inside format call which contains
  formline calls.
* **$FORMAT_FORMFEED, $^L** -- a start output of a page, by default '\f'.
* **$FORMAT_PAGE_NUMBER, $%** -- a serial number for current page.
* **$FORMAT_LINES_LEFT, $-** -- a count of unused available line of a page
* **$FORMAT_LINE_BREAK_CHARACTERS, $:** -- delimiter signs for representation
  rules ^.
* **$FORMAT_LINES_PER_PAGE, $=** -- a count of lines for representation per
  page.
* **$FORMAT_TOP_NAME, $^** -- a format name for a header output.
* **$FORMAT_NAME, $~** -- a format name for output by **write**. By default
  STDOUT.

### Warnings

* **$WARNING, $^W** -- it is set when running perl with `-w` key. It works the
  same as pragma `use warnings`.
* **${^WARNING_BITS}** -- bit variable for all selected warnings to keep track.

### Errors

##### External errors

* **$CHILD_ERROR, $?** -- error id after running external process.
* **${^CHILD_ERROR_NATIVE}** -- error id after running external process. It is
  set as is from OS.

##### Eval errors (Perl level)

* **$EVAL_ERROR, $@** -- it can be a string with error description or a variable
  reference which was used by die call.
* **$EXCEPTIONS_BEING_CAUGHT, $^S** -- a type of code part where an exception happened.

##### System calls errors

* **$EXTENDED_OS_ERROR, $^E** -- the same as $! (with some reservation for VMS,
  OS/2, Win32, MacPerl).
* **$OS_ERROR, $ERRNO, $!** -- error id after syscall. In string context it is
  replaced by error description instead of id.
* **%OS_ERROR, %ERRNO, %!** -- all possible errors for syscalls, where keys are
  their short names and values are their id in case of setting $! variable.

### Interpretator

* $COMPILING, $^C
* $DEBUGGING, $^D
* ${^ENCODING}
* ${^GLOBAL_PHASE}
* $^H
* %^H
* ${^OPEN}
* $PERLDB, $^P
* ${^TAINT}
* ${^SAFE_LOCALES}
* ${^UNICODE}
* ${^UTF8CACHE}
* ${^UTF8LOCALE}

### Unused

* $#
* $\*
* $[
* ${^WIN32_SLOPPY_STAT}
