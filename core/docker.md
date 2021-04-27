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

```bash
FROM debian
RUN apt-get update && apt-get -y upgrade
RUN apt-get -y install make gcc
RUN apt-get -y install vim
RUN apt-get -y install dialog apt-utils
RUN apt-get -y install locales
RUN apt-get -y install cpanminus

# Поддержка русского языка
RUN sed -i -e \
  's/# ru_RU.UTF-8 UTF-8/ru_RU.UTF-8 UTF-8/' /etc/locale.gen \
   && locale-gen

ENV LANG ru_RU.UTF-8
ENV LANGUAGE ru_RU:ru
ENV LC_LANG ru_RU.UTF-8
ENV LC_ALL ru_RU.UTF-8

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
