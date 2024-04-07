---
lang: ru
layout: home
lang-ref: mojo-index
---

# Заговор (Mojo)

## Запуск приложения

```bash
morbo admin.pl
Web application available at http://127.0.0.1:3000
```

## Получить список доступных путей приложения

```bash
./admin.pl routes

/                              GET
/tasks                         *     tasks
  +/                           GET
  +/                           POST
  +/new                        GET   new
  +/:task_id/note              POST  task_idnote
```

Указание `routes` доступно по умолчанию посредством
`Mojolicious::Command::routes`.
