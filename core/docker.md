## Установливаем перл из исходников в ящик (Docker)

Забираем исходники к себе:

```
git clone https://github.com/Perl/perl5
```

Переходим в них:

```
cd perl5/
```

Создаём Dockerfile со следующим содержимым:

```
FROM debian
RUN apt-get update
RUN apt-get -y upgrade
RUN apt-get -y install make gcc
ENTRYPOINT ["/bin/bash"]
```

Создаём образ из Dockerfile:

```
docker build -t perl_dev .
```

Проверяем его наличие:

```
docker image ls | grep perl_dev
perl_dev            latest              82f7da758c59        55 seconds ago 268MB
```

Запускаем ящик:

```
docker run -it -v "$(pwd)":/perl_source \
               -v localperl:/usr/localperl \
               perl_dev
```

Заходим с "папку" с исходниками:

```
cd /perl_source
```

Запускаем предустановочный настройщик:

```
./Configure -des \
            -Dusedevel \
            -Dprefix=/usr/localperl
```

Выполняем сборку:

```
make
```

Запускаем испытания:

```
make test
```

Устанавливаем перл:

```
make install
```

Проверяем "версию" перла:

```
./perl -v

This is perl 5, version 33, subversion 9 (v5.33.9) built for x86_64-linux
```

Выходим из ящика:

```
exit
```

Заново запускаем ящик:

```
docker run -it -v "$(pwd)":/perl_source -v localperl:/usr/localperl perl_dev
```

Проверяем, что всё на месте:

```
/perl_source/perl -v

This is perl 5, version 33, subversion 9 (v5.33.9) built for x86_64-linux
```
