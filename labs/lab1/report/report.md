---
## Front matter
title: "Лабораторная работа N1"
subtitle: "Работа с git"
author: "Туем Гислен"

## Generic otions
lang: ru-RU
toc-title: "Содержание"

## Bibliography
bibliography: bib/cite.bib
csl: pandoc/csl/gost-r-7-0-5-2008-numeric.csl

## Pdf output format
toc: true # Table of contents
toc-depth: 2
lof: true # List of figures
lot: true # List of tables
fontsize: 12pt
linestretch: 1.5
papersize: a4
documentclass: scrreprt
## I18n polyglossia
polyglossia-lang:
  name: russian
  options:
	- spelling=modern
	- babelshorthands=true
polyglossia-otherlangs:
  name: english
## I18n babel
babel-lang: russian
babel-otherlangs: english
## Fonts
mainfont: IBM Plex Serif
romanfont: IBM Plex Serif
sansfont: IBM Plex Sans
monofont: IBM Plex Mono
mathfont: STIX Two Math
mainfontoptions: Ligatures=Common,Ligatures=TeX,Scale=0.94
romanfontoptions: Ligatures=Common,Ligatures=TeX,Scale=0.94
sansfontoptions: Ligatures=Common,Ligatures=TeX,Scale=MatchLowercase,Scale=0.94
monofontoptions: Scale=MatchLowercase,Scale=0.94,FakeStretch=0.9
mathfontoptions:
## Biblatex
biblatex: true
biblio-style: "gost-numeric"
biblatexoptions:
  - parentracker=true
  - backend=biber
  - hyperref=auto
  - language=auto
  - autolang=other*
  - citestyle=gost-numeric
## Pandoc-crossref LaTeX customization
figureTitle: "Рис."
tableTitle: "Таблица"
listingTitle: "Листинг"
lofTitle: "Список иллюстраций"
lotTitle: "Список таблиц"
lolTitle: "Листинги"
## Misc options
indent: true
header-includes:
  - \usepackage{indentfirst}
  - \usepackage{float} # keep figures where there are in the text
  - \floatplacement{figure}{H} # keep figures where there are in the text
---

# Цель работы

Приобретить практические навыки работы с Git.


# Теоретическое введение

Git-это мощный инструмент, созданный 7 апреля 2005 года для управления ядром lunix.

# Выполнение лабораторной работы

## Подготовка
 
### Утановка имени и электронной почты
```
 git config --global user.name "Your Name"
 git config --global user.email "your_email@whatever.com"
```
Если git уже установлен, можете переходить к разделу оконча-
ния строк.

### Параметры установки окончаний строк и Установка отображения unicode.(рис. fig2[-@fig:002]).

![fig1](/home/ghislain/work/study/2024-2025/Математическое моделирование/mathmod/labs/lab1/report/image/002.png){#fig:002 width=70%}

```
Настройка core.autocrlf с параметрами true и input делает все переводы
строк текстовых файлов в главном репозитории одинаковы.
core.autocrlf true - git автоматически конвертирует CRLF->LF при комми-
те и обратно LF->CRLF при выгрузке кода из репозитория на файловую систему
(используют в Windows). core.autocrlf input - конвертация CRLF в LF только
при коммитах (используют в Mac/Linux).

 git config --global core.autocrlf input
 git config --global core.safecrlf true
 git config --global core.quotepath off
```

## Cоздание проекта

### Cоздайте страницу «Hello, World» (рис. [-@fig:003]).
```
mkdir hello
cd hello
touch hello.html
echo "Hello, World!" > hello.html
```

![fig3](/home/ghislain/work/study/2024-2025/Математическое моделирование/mathmod/labs/lab1/report/image/003.png){#fig:003 width=70%}



### Cоздание репозитория, добавление файла в репозиторий и Проверка состояние репозитория(рис. [-@fig:004]).
```
 git init
 git add hello.html
 git commit -m "Initial Commit"
 git status
```

![fig4](/home/ghislain/work/study/2024-2025/Математическое моделирование/mathmod/labs/lab1/report/image/004.png){#fig:004 width=70%}



## Внесение изменений

### Измените страницу «Hello, World» и Проверьте состояние рабочего каталога.(рис. [-@fig:001])
Добавим кое-какие HTML-теги к нашему приветствию. Измените содержимое
файла hello.html на:

```
 <h1>Hello, World!</h1>
 git status
```

![fig1](/home/ghislain/work/study/2024-2025/Математическое моделирование/mathmod/labs/lab1/report/image/001.png){#fig:001 width=70%}




## Индексация изменений

Теперь выполните команду git, чтобы проиндексировать изменения. Проверьте
состояние.(рис. [-@fig:005]).
```
 git add hello.html
 git status
```


![fig5](/home/ghislain/work/study/2024-2025/Математическое моделирование/mathmod/labs/lab1/report/image/005.png){#fig:005 width=70%}


### Коммит изменений
Сделайте коммит и проверьте состояние.(рис. [-@fig:007]).
```
 git commit
```

![fig7](/home/ghislain/work/study/2024-2025/Математическое моделирование/mathmod/labs/lab1/report/image/007.png){#fig:007 width=70%}



В первой строке введите комментарий: «Added h1 tag». Сохраните файл и вый-
дите из редактора.(рис. [-@fig:006]).
```
 git status
```

![fig6](/home/ghislain/work/study/2024-2025/Математическое моделирование/mathmod/labs/lab1/report/image/006.png){#fig:006 width=70%}



### Добавьте стандартные теги страницы
Измените страницу «Hello, World», чтобы она содержала стандартные теги.(рис. [-@fig:008])
```
<html>
    <body>
        <h1>Hello, World!</h1>
    </body>
</html>

```
![fig8](/home/ghislain/work/study/2024-2025/Математическое моделирование/mathmod/labs/lab1/report/image/008.png){#fig:008 width=70%}


Теперь добавьте это изменение в индекс git.
```
git add hello.html
```
Теперь добавьте заголовки HTML (секцию <head>) к странице «Hello, World».(рис. [-@fig:009])

![fig9](/home/ghislain/work/study/2024-2025/Математическое моделирование/mathmod/labs/lab1/report/image/009.png){#fig:009 width=70%}


Проверьте текущий статус (рис. [-@fig:009]):
```
git status
```
![fig10](/home/ghislain/work/study/2024-2025/Математическое моделирование/mathmod/labs/lab1/report/image/010.png){#fig:010 width=70%}


Произведите коммит проиндексированного изменения (значение по умолча-
нию), а затем еще раз проверьте состояние.(рис. [-@fig:011])
```
 git commit -m "Added standard HTML page tags"
 git status
```

![fig11](/home/ghislain/work/study/2024-2025/Математическое моделирование/mathmod/labs/lab1/report/image/011.png){#fig:011 width=70%}


Теперь добавьте второе изменение в индекс, а затем проверьте состояние с
помощью команды git status.(рис. [-@fig:012])

```
git add .
git status
```

![fig12](/home/ghislain/work/study/2024-2025/Математическое моделирование/mathmod/labs/lab1/report/image/012.png){#fig:012 width=70%}

Сделайте коммит второго изменения(рис. [-@fig:013])
```
git commit -m "Added HTML header"
```
![fig13](/home/ghislain/work/study/2024-2025/Математическое моделирование/mathmod/labs/lab1/report/image/013.png){#fig:013 width=70%}


### История
Получим список произведенных изменений(рис. [-@fig:015]):
```
git log
```
Есть много вариантов отображения лога.
```
git log --pretty=oneline --max-count=2
git log --pretty=oneline --since='5 minutes ago'
git log --pretty=oneline --until='5 minutes ago'
git log --pretty=oneline --author=<your name>
git log --pretty=oneline --all
```
![fig15](/home/ghislain/work/study/2024-2025/Математическое моделирование/mathmod/labs/lab1/report/image/015.png){#fig:015 width=70%}

Справочная страница(рис. [-@fig:019]):
```
man git-log
```

![fig19](/home/ghislain/work/study/2024-2025/Математическое моделирование/mathmod/labs/lab1/report/image/019.png){#fig:019 width=70%}

### Получение старых версий(рис. [-@fig:021])
```
git log
git checkout <hash>
cat hello.htm
```

![fig21](/home/ghislain/work/study/2024-2025/Математическое моделирование/mathmod/labs/lab1/report/image/021.png){#fig:021 width=70%}

Вернитесь к последней версии в ветке master(рис. [-@fig:022])
```
git checkout master
cat hello.html
```

![fig22](/home/ghislain/work/study/2024-2025/Математическое моделирование/mathmod/labs/lab1/report/image/022.png){#fig:022 width=70%}

### Создание тегов версий
```
git tag v1
```
Теперь текущая версия страницы называется v1.
Теги для предыдущих версий Давайте создадим тег для версии, которая идет
перед текущей версией и назовем его v1-beta и сделаем
ее версией v1-beta.(рис. [-@fig:024])
```
git checkout v1^
cat hello.html
git tag v1-beta
```

![fig24](/home/ghislain/work/study/2024-2025/Математическое моделирование/mathmod/labs/lab1/report/image/024.png){#fig:024 width=70%}

### Переключение по имени тега
Теперь попробуйте попереключаться между двумя отмеченными версиями.(рис. [-@fig:026])
```
git checkout v1
git checkout v1-beta
```

![fig26](/home/ghislain/work/study/2024-2025/Математическое моделирование/mathmod/labs/lab1/report/image/026.png){#fig:026 width=70%}

### Просмотр тегов с помощью команды tag

Вы можете увидеть, какие теги доступны, используя команду git tag и также можете посмотреть теги в логе.(рис. [-@fig:027])
```
git tag
git log master --all
```

![fig27](/home/ghislain/work/study/2024-2025/Математическое моделирование/mathmod/labs/lab1/report/image/027.png){#fig:027 width=70%}

## Отмена локальных изменений (до индексации)

### Переключитесь на ветку master

Убедитесь, что вы находитесь на последнем коммите ветки master, прежде чем
продолжить работу.(рис. [-@fig:028])
```
git checkout master
```

![fig28](/home/ghislain/work/study/2024-2025/Математическое моделирование/mathmod/labs/lab1/report/image/028.png){#fig:028 width=70%}

### Измените hello.html

Внесите изменение в файл hello.html в виде нежелательного комментария.(рис. [-@fig:029]) и проверьте состояние.(рис. [-@fig:030])
```
<html>
    <head>
    </head>
    <body>
        <h1>Hello, World!</h1>
        <!-- This is a bad comment. We want to revert it. -->
    </body>
</html>
```

![fig29](/home/ghislain/work/study/2024-2025/Математическое моделирование/mathmod/labs/lab1/report/image/029.png){#fig:029 width=70%}

![fig30](/home/ghislain/work/study/2024-2025/Математическое моделирование/mathmod/labs/lab1/report/image/030.png){#fig:030 width=70%}

Мы видим, что файл hello.html был изменен, но еще не проиндексирован.

### Отмена изменений в рабочем каталоге

Используйте команду git checkout для переключения версии файла
hello.html в репозитории.(рис. [-@fig:031])
```
git checkout hello.html
git status
cat hello.html
```

![fig31](/home/ghislain/work/study/2024-2025/Математическое моделирование/mathmod/labs/lab1/report/image/031.png){#fig:031 width=70%}

## Отмена проиндексированных изменений (перед коммитом)

### Измените файл и проиндексируйте изменения

Внесите изменение в файл hello.html в виде нежелательного комментария(рис. [-@fig:032]).
```
<html>
    <head>
        <!-- This is an unwanted but staged comment -->
    </head>
    <body>
        <h1>Hello, World!</h1>
    </body>
</html>
```

![fig32](/home/ghislain/work/study/2024-2025/Математическое моделирование/mathmod/labs/lab1/report/image/032.png){#fig:032 width=70%}

Проиндексируйте это изменение и проверьте состояние(рис. [-@fig:033]).
```
git add hello.html
git status
```

![fig33](/home/ghislain/work/study/2024-2025/Математическое моделирование/mathmod/labs/lab1/report/image/033.png){#fig:033 width=70%}

### Выполните сброс буферной зоны

К счастью, вывод состояния показывает нам именно то, что мы должны сделать
для отмены индексации изменения.(рис. [-@fig:034]).
```
git reset HEAD hello.html
```
Команда git reset сбрасывает буферную зону к HEAD. Это очищает буферную
зону от изменений, которые мы только что проиндексировали.
Команда git reset (по умолчанию) не изменяет рабочий каталог. Поэтому
рабочий каталог все еще содержит нежелательный комментарий. Мы можем ис-
пользовать команду git checkout, чтобы удалить нежелательные изменения в
рабочем каталоге.

![fig34](/home/ghislain/work/study/2024-2025/Математическое моделирование/mathmod/labs/lab1/report/image/034.png){#fig:034 width=70%}


### Переключитесь на версию коммита

```
git checkout hello.html
git status
```
Наш рабочий каталог опять чист(рис. [-@fig:035]).

![fig35](/home/ghislain/work/study/2024-2025/Математическое моделирование/mathmod/labs/lab1/report/image/035.png){#fig:035 width=70%}

## Отмена коммитов

### Отмена коммитов
Иногда вы понимаете, что новые коммиты являются неверными, и хотите их
отменить. Есть несколько способов решения этого вопроса, здесь мы будем исполь-
зовать самый безопасный.
Мы отменим коммит путем создания нового коммита, отменяющего нежела-
тельные изменения.

### Измените файл и сделайте коммит

Измените файл hello.html на следующий(рис. [-@fig:036]).
```
<html>
    <head>
    </head>
    <body>
        <h1>Hello, World!</h1>
        <!-- This is an unwanted but committed change -->
    </body>
</html>
```

![fig36](/home/ghislain/work/study/2024-2025/Математическое моделирование/mathmod/labs/lab1/report/image/036.png){#fig:036 width=70%}

Выполните(рис. [-@fig:037]).: 
```
git add hello.html
git commit -m "Oops, we didn't want this commit"
```

![fig37](/home/ghislain/work/study/2024-2025/Математическое моделирование/mathmod/labs/lab1/report/image/037.png){#fig:037 width=70%}

### Сделайте коммит с новыми изменениями, отменяющими предыдущие

Чтобы отменить коммит, нам необходимо сделать коммит, который удаляет изме-
нения, сохраненные нежелательным коммитом(рис. [-@fig:039]).
```
git revert HEAD
```

![fig39](/home/ghislain/work/study/2024-2025/Математическое моделирование/mathmod/labs/lab1/report/image/039.png){#fig:039 width=70%}

### Проверьте лог
```
git log
```
Эта техника будет работать с любым коммитом(рис. [-@fig:040]).

![fig40](/home/ghislain/work/study/2024-2025/Математическое моделирование/mathmod/labs/lab1/report/image/040.png){#fig:040 width=70%}

## Удаление коммиттов из ветки

### Для начала отметьте эту ветку

Но прежде чем удалить коммиты, давайте отметим последний коммит тегом, чтобы
потом можно было его найти(рис. [-@fig:042]).
```
git tag oops
```

![fig42](/home/ghislain/work/study/2024-2025/Математическое моделирование/mathmod/labs/lab1/report/image/042.png){#fig:042 width=70%}

### Сброс коммитов к предшествующим коммиту Oops

```
git reset --hard v1
git log
```
Мы видим, что ошибочные коммиты не исчезли. Они все еще находятся в ре-
позитории. Просто они отсутствуют в ветке master. Если бы мы не отметили их
тегами, они по-прежнему находились бы в репозитории, но не было бы никакой
возможности ссылаться на них, кроме как при помощи их хэш имен. Коммиты, на
которые нет ссылок, остаются в репозитории до тех пор, пока не будет запущен
сборщик мусора(рис. [-@fig:043]).

![fig43](/home/ghislain/work/study/2024-2025/Математическое моделирование/mathmod/labs/lab1/report/image/043.png){#fig:043 width=70%}

## Удаление тега oops

### Удаление тега oops

Тег oops свою функцию выполнил. Давайте удалим его и коммиты, на которые он
ссылался, сборщиком мусора(рис. [-@fig:045]).

![fig45](/home/ghislain/work/study/2024-2025/Математическое моделирование/mathmod/labs/lab1/report/image/045.png){#fig:045 width=70%}

## Внесение изменений в коммиты

### Измените страницу, а затем сделайте коммит

(рис. [-@fig:046]). 

![fig46](/home/ghislain/work/study/2024-2025/Математическое моделирование/mathmod/labs/lab1/report/image/046.png){#fig:046 width=70%}

Выполните:
```
git add hello.html
git commit -m "Add an author comment"
```

(рис. [-@fig:047]). 

![fig47](/home/ghislain/work/study/2024-2025/Математическое моделирование/mathmod/labs/lab1/report/image/047.png){#fig:047 width=70%}

### Необходим email 
(рис. [-@fig:048]). 

![fig48](/home/ghislain/work/study/2024-2025/Математическое моделирование/mathmod/labs/lab1/report/image/048.png){#fig:048 width=70%}

### Измените предыдущий коммит
(рис. [-@fig:050]). 
```
git add hello.html
git commit --amend -m "Add an author/email comment"
```

![fig50](/home/ghislain/work/study/2024-2025/Математическое моделирование/mathmod/labs/lab1/report/image/050.png){#fig:050 width=70%}

## Перемещение файлов

### Переместите файл hello.html в каталог lib
Сейчас мы собираемся создать структуру нашего репозитория. Давайте перенесем
страницу в каталог lib.(рис. [-@fig:052]).
```
mkdir lib
git mv hello.html lib
git status
```

![fig52](/home/ghislain/work/study/2024-2025/Математическое моделирование/mathmod/labs/lab1/report/image/052.png){#fig:052 width=70%}

### Второй способ перемещения файлов
```
mkdir lib
mv hello.html lib
git add lib/hello.html
git rm hello.html
```

### Коммит в новый каталог(рис. [-@fig:053])
```
git commit -m "Moved hello.html to lib"
```

![fig53](/home/ghislain/work/study/2024-2025/Математическое моделирование/mathmod/labs/lab1/report/image/053.png){#fig:053 width=70%}


## Подробнее о структуре

### Добавление index.html

Добавим файл index.html в наш репозиторий и сделайте коммит(рис. [-@fig:054])

![fig54](/home/ghislain/work/study/2024-2025/Математическое моделирование/mathmod/labs/lab1/report/image/054.png){#fig:054 width=70%}


## Git внутри: Каталог .git

### Каталог .git

Выполните: (рис. [-@fig:057]), (рис. [-@fig:058])
```
la -C .git
ls -C .git/objects
ls -C .git/objects/<dir>
```

![fig57](/home/ghislain/work/study/2024-2025/Математическое моделирование/mathmod/labs/lab1/report/image/057.png){#fig:057 width=70%}

![fig58](/home/ghislain/work/study/2024-2025/Математическое моделирование/mathmod/labs/lab1/report/image/058.png){#fig:058 width=70%}


### Config File
Выполните:(рис. [-@fig:059])
```
cat .git/config
```

![fig59](/home/ghislain/work/study/2024-2025/Математическое моделирование/mathmod/labs/lab1/report/image/059.png){#fig:059 width=70%}

### Ветки и теги, Файл HEAD

Выполните:(рис. [-@fig:060]), (рис. [-@fig:061])
```
ls .git/refs
ls .git/refs/heads
ls .git/refs/tags
cat .git/refs/tags/v1

cat .git/HEAD
```

![fig60](/home/ghislain/work/study/2024-2025/Математическое моделирование/mathmod/labs/lab1/report/image/060.png){#fig:060 width=70%}

![fig61](/home/ghislain/work/study/2024-2025/Математическое моделирование/mathmod/labs/lab1/report/image/061.png){#fig:061 width=70%}


## Работа непосредственно с объектами git

### Поиск последнего коммита (рис. [-@fig:062])
```
git log --max-count=1
```
![fig62](/home/ghislain/work/study/2024-2025/Математическое моделирование/mathmod/labs/lab1/report/image/062.png){#fig:062 width=70%}


### Вывод последнего коммита с помощью SHA1 хэша

Выполните:(рис. [-@fig:063])

```
git cat-file -t <hash>
git cat-file -p <hash>
```

![fig63](/home/ghislain/work/study/2024-2025/Математическое моделирование/mathmod/labs/lab1/report/image/063.png){#fig:063 width=70%}

### Поиск дерева

Мы можем вывести дерево каталогов, ссылка на который идет в коммите. Это долж-
но быть описание файлов (верхнего уровня) в нашем проекте (для конкретного
коммита). Используйте SHA1 хэш из строки «дерева», из списка выше.
Выполните:(рис. [-@fig:064])
```
git cat-file -p <treehash>
```

![fig64](/home/ghislain/work/study/2024-2025/Математическое моделирование/mathmod/labs/lab1/report/image/064.png){#fig:064 width=70%}


### Вывод каталога lib, Вывод файла hello.html

Выполните:(рис. [-@fig:066])
```
git cat-file -p <libhash>
git cat-file -p <hellohash>
```

![fig66](/home/ghislain/work/study/2024-2025/Математическое моделирование/mathmod/labs/lab1/report/image/066.png){#fig:066 width=70%}


## Создание ветки, Добавьте файл стилей style.css, Измените основную страницу и Измените index.html

(рис. [-@fig:068]), (рис. [-@fig:069]), (рис. [-@fig:070]), (рис. [-@fig:072]), (рис. [-@fig:073]), (рис. [-@fig:074]), (рис. [-@fig:075])
```
git checkout -b style
git status

touch lib/style.css
```
Файл lib/style.css:
```
h1 {
    color: red;
}
```
```
git add lib/style.css
git commit -m "Added css stylesheet"

git add index.html
git commit -m "Updated index.html"
```

![fig68](/home/ghislain/work/study/2024-2025/Математическое моделирование/mathmod/labs/lab1/report/image/068.png){#fig:068 width=70%}

![fig69](/home/ghislain/work/study/2024-2025/Математическое моделирование/mathmod/labs/lab1/report/image/069.png){#fig:069 width=70%}

![fig70](/home/ghislain/work/study/2024-2025/Математическое моделирование/mathmod/labs/lab1/report/image/070.png){#fig:070 width=70%}

![fig72](/home/ghislain/work/study/2024-2025/Математическое моделирование/mathmod/labs/lab1/report/image/072.png){#fig:072 width=70%}

![fig73](/home/ghislain/work/study/2024-2025/Математическое моделирование/mathmod/labs/lab1/report/image/073.png){#fig:073 width=70%}

![fig74](/home/ghislain/work/study/2024-2025/Математическое моделирование/mathmod/labs/lab1/report/image/074.png){#fig:074 width=70%}

![fig75](/home/ghislain/work/study/2024-2025/Математическое моделирование/mathmod/labs/lab1/report/image/075.png){#fig:075 width=70%}

## Навигация по веткам

Теперь в вашем проекте есть две ветки:
Выполните:(рис. [-@fig:076])
```
git log --all
```

![fig76](/home/ghislain/work/study/2024-2025/Математическое моделирование/mathmod/labs/lab1/report/image/076.png){#fig:076 width=70%}


### Переключение на ветку master

Используйте команду git checkout для переключения между ветками:(рис. [-@fig:077])
```
git checkout master
cat lib/hello.html
```

![fig77](/home/ghislain/work/study/2024-2025/Математическое моделирование/mathmod/labs/lab1/report/image/076.png){#fig:077 width=70%}


### Вернемся к ветке style 

Выполните:(рис. [-@fig:078])
```
git checkout style
cat lib/hello.html
```

![fig78](/home/ghislain/work/study/2024-2025/Математическое моделирование/mathmod/labs/lab1/report/image/078.png){#fig:078 width=70%}

## Изменения в ветке master

### Создайте файл README в ветке master(рис. [-@fig:079])

```
git checkout master

echo "This is the Hello World example from the git tutorial." > READ
```

![fig79](/home/ghislain/work/study/2024-2025/Математическое моделирование/mathmod/labs/lab1/report/image/079.png){#fig:079 width=70%}


### Сделайте коммит изменений README.md в ветку master.(рис. [-@fig:080])

```
git add README.md
git commit -m "Added README"
```

![fig80](/home/ghislain/work/study/2024-2025/Математическое моделирование/mathmod/labs/lab1/report/image/080.png){#fig:080 width=70%}


## Слияние веток

Слияние переносит изменения из двух веток в одну. Давайте вернемся к ветке
style и сольем master с style.
Выполните:(рис. [-@fig:082])
```
git checkout style
git merge master
git log --graph --all
```

![fig82](/home/ghislain/work/study/2024-2025/Математическое моделирование/mathmod/labs/lab1/report/image/082.png){#fig:082 width=70%}


## Создание конфликта

### Вернитесь в master и создайте конфликт

Вернитесь в ветку master и внесите следующие изменения:
```
git checkout master
```
Файл lib/hello.html(рис. [-@fig:084])

![fig84](/home/ghislain/work/study/2024-2025/Математическое моделирование/mathmod/labs/lab1/report/image/084.png){#fig:084 width=70%}


```
git add lib/hello.html
git commit -m 'Life is great'
```

## Разрешение конфликтов

### Слияние master с веткой style

Теперь вернемся к ветке style и попытаемся объединить ее с новой веткой
master.
Выполните:(рис. [-@fig:086])
```
git checkout style
git merge master
```

![fig86](/home/ghislain/work/study/2024-2025/Математическое моделирование/mathmod/labs/lab1/report/image/086.png){#fig:086 width=70%}

Если вы откроете lib/hello.html, вы увидите:
```
<!-- Author: Dmitry S. Kulyabov (dskulyabov@rudn.ru) -->
<html>
    <head>
<<<<<<< HEAD
        <link type="text/css" rel="stylesheet" media="all" href="style.css" />
=======
        <!-- no style -->
>>>>>>> master
    </head>
    <body>
        <h1>Hello,World! Life is great!</h1>
    </body>
</html>
```

### Решение конфликта

Вам необходимо вручную разрешить конфликт. Внесите изменения в lib/hello.html
для достижения следующего результата
```
<!-- Author: Dmitry S. Kulyabov (dskulyabov@rudn.ru) -->
<html>
    <head>
        <link type="text/css" rel="stylesheet"
            media="all" href="style.css" />
    </head>
    <body>
        <h1>Hello, World! Life is great!</h1>
    </body>
</html>
```

### Сделайте коммит решения конфликта (рис. [-@fig:087])
```
git add lib/hello.html
git commit -m "Merged master fixed conflict."
```

![fig86](/home/ghislain/work/study/2024-2025/Математическое моделирование/mathmod/labs/lab1/report/image/087.png){#fig:087 width=70%}

## Клонирование репозиториев

### Перейдите в рабочий каталог, Создайте клон репозитория hello и давайте взглянем на клонированный репозиторий.

```
cd ..
pwd
ls

git clone hello cloned_hello
ls

cd cloned_hello
ls
```
Вы увидите список всех файлов на верхнем уровне оригинального репозитория
README.md, index.html и lib.(рис. [-@fig:096]), (рис. [-@fig:097]),(рис. [-@fig:098]), (рис. [-@fig:099])


![fig96](/home/ghislain/work/study/2024-2025/Математическое моделирование/mathmod/labs/lab1/report/image/096.png){#fig:096 width=70%}

![fig97](/home/ghislain/work/study/2024-2025/Математическое моделирование/mathmod/labs/lab1/report/image/097.png){#fig:097 width=70%}

![fig98](/home/ghislain/work/study/2024-2025/Математическое моделирование/mathmod/labs/lab1/report/image/098.png){#fig:098 width=70%}

![fig99](/home/ghislain/work/study/2024-2025/Математическое моделирование/mathmod/labs/lab1/report/image/099.png){#fig:099 width=70%}

## Что такое origin?

Выполните:
```
git remote

git remote show origin
```
Мы видим, что клонированный репозиторий знает об имени по умолчанию
удаленного репозитория(рис. [-@fig:101])


![fig101](/home/ghislain/work/study/2024-2025/Математическое моделирование/mathmod/labs/lab1/report/image/101.png){#fig:101 width=70%}


## Извлечение общих изменений(рис. [-@fig:119])

```
cd ../cloned_hello

git remote add shared ../hello.git
git branch --track shared master
git pull shared master
cat README.md
```




![fig119](/home/ghislain/work/study/2024-2025/Математическое моделирование/mathmod/labs/lab1/report/image/119.png){#fig:119 width=70%}


# Выводы

В процессе выполнения данной лабораторной работы я приобрела практические навыки работы с Git.
