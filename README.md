# Шпаргалка по Git

1. Посмотреть все установленные настройки и узнать, где они располгаются:
```bash
$ git config --list --show-origin
```

2. Установка имени пользователя и адреса эл. почты:
```bash
$ git config --global user.name "Artem Gusev"
$ git config --global user.email gusev2014russia@mail.ru
```

3. Установка дефолтного редактора:
```bash
$ git config --global core.editor atom
```

4. Посмотреть текущий конфиг git'а:
```bash
$ git config --list
```

5. Просмотреть значение опредленного ключа в конфиге:
```bash
$ git config user.name
```

6. Помощь в git:

Если вам нужна помощь при использовании Git, есть 3 способа открыть страницу руководства по любой команде Git:
```bash
$ git help <команда>
$ git <команда> --help
$ man git-<команда>
```

Если же вам нужна краткая инструкция по использования:
```bash
$ git <команда> -h
```
