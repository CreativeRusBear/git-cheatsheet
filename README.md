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
# sets atom as default code editor
$ git config --global core.editor atom

# sets visual studio code as default code editor
$ git config --global core.editor "code --wait"

# sets vim as default code editor
$ git config --global core.editor "vim"
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

7. Инициализция репозитория
```bash
$ git init
```

Эта команда создает в текущей директории новую поддиректорию с именем **.git**, содержащую все необходимые файлы репозитория - структуру Git-репозитория.

8. Клонирование существующего репозитория:
```bash
$ git clone <url>
```

9. Для того, чтобы клонировать репозиторий в директорию, отличающимся от имени клона, необходимо указать желаемое имя, как парметр командной строки. За пример возьмем клонирование **libgit2**:
```bash
$ git clone https://github.com/libgit2/libgit2 mylibgit
```

10. Сокращенный вывод статуса:
```bash
$ git status -s
<или>
$ git status --short 
```

11. Вывод подробной информации об изменениях (просмотр добавленных и удаленных строк):

    * Просмотр непроидексированных имзенений:

    ```bash
    $ git diff
    ```

    * Просмотр проиндексированных изменений:
    
    ```bash
    $ git diff --staged
    <или>
    $ git diff --cached
    ```
    
12. Коммит изменений:
    * Открытие редактора, прописанного в конфиге, с возможностью ввода текста для коммита:
    ```bash
    $ git config
    ```
    
    P.S. В редакторе будет отображен следующий текст (или похожий на него):
    
    ```markdown
     # Please enter the commit message for your changes. Lines starting
     # with '#' will be ignored, and an empty message aborts the commit.
     # On branch master
     # Your branch is up-to-date with 'origin/master'.
     #
     # Changes to be committed:
     #
     new file:
     README
     #
     modified:
     CONTRIBUTING.md
     #
     ~
     ~
     ~
     ".git/COMMIT_EDITMSG" 9L, 283C`
    ```
     
     >**ПРИМЕЧАНИЕ!** Для ещё более подробного напоминания, что же именно вы поменяли, можете передать аргумент `-v` в команду `git commit`. Это приведёт к тому, что в комментарий будет также помещена дельта/`diff` изменений.
     
     Когда вы выходите из редактора, Git создаёт для вас коммит с этим сообщением, удаляя комментарии и вывод команды `diff`.
     
13. `$ git add <файл>` + `$ git commit <файл> -m "<сообщение>"` = `$ git commit -a -m "<сообщение>"`
    
    * `-a` - включает все файлы
    
14. Удаление файлов из директории и из списка отслеживаемых файлов:
```bash
$ git rm <файл>
```
    
15. Удалить файл из индекса, оставив его в рабочем каталоге:
```bash
$ git rm --cached <файл>
```

16. Отобраение всех коммитов в истории текущей ветки:
```bash
$ git log
```

17. Вывод логов с показом изменений:
```bash
$ git log -p
<или>
$ git log --patch
```

18. Вывод логов с краткой записью об изменениях:
```bash
$ git log --stat
```

19. Граф в формате ASCII, который показывает текущую ветку и историю слияний:
```bash
$ git log --graph
```

20. Изменение сообщения в последнем коммите:
```bash
$ git commit --amend -m "Новое сообщение"
```
21. Синхронизация fork-a на github с основным репозиторием:
```bash
// Добавляем адрес для отслеживаемой веткой (upstream branch) основного репозитория
$ git remote add upstream https://github.com/test/test-example.git

// Просматриваем все удаленные ветки
$ git remote -v

// Получаем себе веточки
$ git fetch upstream

// Делаем merge нужной нам ветки с master основного репозитория
$ git merge upstream/master
```

21. Удаление файла из stage
```bash
$ git reset [file]
```

# Возможные проблемы при работе с git и их решения

1. Как выйти из `git diff`?

**Ответ**: Нажать на клаишу `q`
