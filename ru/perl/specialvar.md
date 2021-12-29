---
lang: ru
layout: home
lang-ref: perl/specialvar
---

## Особые переменные в Перл

### Общие переменные

* $LIST\_SEPARATOR, $"
* $a, $b
* %ENV
* $SYSTEM\_FD\_MAX, $^F
* @F
* $INPLACE\_EDIT, $^I
* $^M
* $BASETIME, $^T

##### "Функции" и ключевые вызовы

* $ARG, $\_
* @ARG, @\_

##### Модули

* @INC
* %INC
* @ISA

##### "Сигналы"

* %SIG

##### О запущенном приложении

* $PROCESS\_ID, $PID, $$
* $PROGRAM\_NAME, $0

##### Сведения

* $EXECUTABLE\_NAME, $^X
* $OSNAME, $^O
* $PERL\_VERSION, $^V
* $OLD\_PERL\_VERSION, $]

##### Пользователи и "группы"

* $REAL\_GROUP\_ID, $GID, $(
* $EFFECTIVE\_GROUP\_ID, $EGID, $)
* $REAL\_USER\_ID, $UID, $<
* $EFFECTIVE\_USER\_ID, $EUID, $>
* $SUBSCRIPT\_SEPARATOR, $SUBSEP, $;


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

### Разметки ("Форматы")

* **$ACCUMULATOR, $^A** -- переменная для внутреннего использования внутри format вызова,
  содержащего formline вызовы, которые работают с ней напрямую.
* **$FORMAT_FORMFEED, $^L** -- с чего начинается вывод одной страницы разметки,
  по умолчанию '\f'.
* **$FORMAT_PAGE_NUMBER, $%** -- порядковое число для текущей страницы разметки.
* **$FORMAT_LINES_LEFT, $-** -- количество неиспользуемых доступных строк на
  странице.
* **$FORMAT_LINE_BREAK_CHARACTERS, $:** -- знаки разделители, используемые для
  случая с правилами отображения ^.
* **$FORMAT_LINES_PER_PAGE, $=** -- количество строк для отображения на странице
  разметки.
* **$FORMAT_TOP_NAME, $^** -- имя разметки в качестве шапки для вывода.
* **$FORMAT_NAME, $~** -- имя разметки для вывода с помощью **write**. По
  умолчанию STDOUT.

### Предупреждения

* **$WARNING, $^W** -- устанавливается при запуске с ключом `-w`, влияет на
  выполнение также, как и "прагма" `use warnings`.
* **${^WARNING_BITS}** -- "битовая" переменная для хранения всех выбранных
  предупреждения для отслеживания.

### Ошибки

##### Ошибки при выполнении сторонних приложений

* **$CHILD_ERROR, $?** -- число ошибки при выполнении внешнего приложения.
* **${^CHILD_ERROR_NATIVE}** -- число ошибки при выполнении внешнего приложения,
  схожее с $?, но которое выдаётся как есть в зависимости от ОС.

##### Ошибки при выполнении eval (уровень Перл)

* **$EVAL_ERROR, $@** -- содержит либо строку с описанием ошибки, либо ссылку на
  переменную, с которой был вызван die.
* **$EXCEPTIONS_BEING_CAUGHT, $^S** -- указывает на вид участка "кода", где
  произошло исключение.

##### "Системные" вызовы

* **$EXTENDED_OS_ERROR, $^E** -- тоже, что и $! (с некоторыми оговорками для VMS,
  OS/2, Win32, MacPerl).
* **$OS_ERROR, $ERRNO, $!** -- содержит "номер" ошибки, после вызова "системного"
  вызова. При использование в строках подменяется на описание ошибки, вместо
  самого числа.
* **%OS_ERROR, %ERRNO, %!** -- словарь всевозможных ошибок при использовании
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
* $\*
* $[
* ${^WIN32_SLOPPY_STAT}
