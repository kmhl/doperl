---
lang: en
layout: home
lang-ref: core/docker
---

## Installing Perl from sources into Docker-container

Get sources:

```
git clone https://github.com/Perl/perl5
```

Go to it:

```
cd perl5/
```

Create Dockerfile with the following content:

```bash
FROM debian
RUN apt-get update && apt-get -y upgrade
RUN apt-get -y install make gcc
RUN apt-get -y install vim
RUN apt-get -y install dialog apt-utils
RUN apt-get -y install locales
RUN apt-get -y install cpanminus

WORKDIR /perl_source
ENTRYPOINT ["/bin/bash"]
```

Make image from Dockerfile:

```
docker build -t perl_dev .
```

Check it:

```
docker image ls | grep perl_dev
perl_dev            latest              82f7da758c59        55 seconds ago 268MB
```

Run a container:

```
docker run -it -v "$(pwd)":/perl_source \
               -v localperl:/usr/localperl \
               perl_dev
```

Run pre-install configuration:

```
./Configure -des \
            -Dusedevel \
            -Dprefix=/usr/localperl
```

Make it by make:

```
make
```

Run tests:

```
make test
```

Install perl:

```
make install
```

Check perl version:

```
./perl -v

This is perl 5, version 33, subversion 9 (v5.33.9) built for x86_64-linux
```

Exit from the container:

```
exit
```

Run the container one more time:

```
docker run -it -v "$(pwd)":/perl_source -v localperl:/usr/localperl perl_dev
```

Check that it works as before:

```
/perl_source/perl -v

This is perl 5, version 33, subversion 9 (v5.33.9) built for x86_64-linux
```
