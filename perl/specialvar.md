## Особые переменные в Перл

### Общие переменные

* $LIST_SEPARATOR, $"
* $a, $b
* %ENV
* $SYSTEM_FD_MAX, $^F
* @F
* $INPLACE_EDIT, $^I
* $^M
* $BASETIME, $^T

##### "Функции" и ключевые вызовы

* $ARG, $_
* @ARG, @_

##### Модули

* @INC
* %INC
* @ISA

##### "Сигналы"

* %SIG

##### О запущенном приложении

* $PROCESS_ID, $PID, $$
* $PROGRAM_NAME, $0

##### Сведения

* $EXECUTABLE_NAME, $^X
* $OSNAME, $^O
* $PERL_VERSION, $^V
* $OLD_PERL_VERSION, $]

##### Пользователи и "группы"

* $REAL_GROUP_ID, $GID, $(
* $EFFECTIVE_GROUP_ID, $EGID, $)
* $REAL_USER_ID, $UID, $<
* $EFFECTIVE_USER_ID, $EUID, $>
* $SUBSCRIPT_SEPARATOR, $SUBSEP, $;


### Отыскивающие выражения

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

### Файлы

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

### "Форматы"

* $ACCUMULATOR, $^A
* $FORMAT_FORMFEED, $^L
* $FORMAT_PAGE_NUMBER, $%
* $FORMAT_LINES_LEFT, $-
* $FORMAT_LINE_BREAK_CHARACTERS, $:
* $FORMAT_LINES_PER_PAGE, $=
* $FORMAT_TOP_NAME, $^
* $FORMAT_NAME, $~

### Ошибки

* ${^CHILD_ERROR_NATIVE}
* $EXCEPTIONS_BEING_CAUGHT, $^S
* $WARNING, $^W
* ${^WARNING_BITS}
* $CHILD_ERROR, $?
* $EVAL_ERROR, $@

##### "Системные" вызовы

* $EXTENDED_OS_ERROR, $^E -- тоже, что и $! (с некоторыми оговорками для VMS,
  OS/2, Win32, MacPerl).
* $OS_ERROR, $ERRNO, $! -- содержит "номер" ошибки, после вызова "системного"
  вызова. При использование в строках подменяется на описание ошибки, вместо
  самого числа.
* %OS_ERROR, %ERRNO, %! -- словар всевозможных ошибок при использовании
  "системных" вызовов, где ключами выступают их краткие наименования, а
  значением число ошибки, в случае, если была задана переменная $!.

### "Интерпретатор"

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

### Неиспользуемые

* $#
* $*
* $[
* ${^WIN32_SLOPPY_STAT}
