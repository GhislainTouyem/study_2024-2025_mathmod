---
## Front matter
lang: ru-RU
title: Лабораторная работа N1
subtitle: Работа с git
author:
  - Туем Г.
institute:
  - Российский университет дружбы народов, Москва, Россия
  

## i18n babel
babel-lang: russian
babel-otherlangs: english

## Formatting pdf
toc: false
toc-title: Содержание
slide_level: 2
aspectratio: 169
section-titles: true
theme: metropolis
header-includes:
 - \metroset{progressbar=frametitle,sectionpage=progressbar,numbering=fraction}
---

# Информация

## Докладчик

:::::::::::::: {.columns align=center}
::: {.column width="70%"}

  * Туем Гислен.
  * Студент
  * НКНбд-01-22
  * Российский университет дружбы народов
  * [1032225069@pfur.ru](mailto:1032225069@pfur.ru)
 

:::
::: {.column width="30%"}

![](/home/ghislain/work/study/2024-2025/Математическое моделирование/mathmod/labs/lab1/presentation/image/moi.jpeg)

:::
::::::::::::::



## Цель работы

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

## Cоздание проекта

![Cоздайте страницу «Hello, World»](/home/ghislain/work/study/2024-2025/Математическое моделирование/mathmod/labs/lab1/report/image/003.png)

## Cоздание репозитория, добавление файла в репозиторий и Проверка состояние репозитория

![fig4](/home/ghislain/work/study/2024-2025/Математическое моделирование/mathmod/labs/lab1/report/image/004.png)


## Измените страницу «Hello, World» и Проверьте состояние рабочего каталога.

![fig1](/home/ghislain/work/study/2024-2025/Математическое моделирование/mathmod/labs/lab1/report/image/001.png)

## Индексация изменений


![проиндексировать изменения](/home/ghislain/work/study/2024-2025/Математическое моделирование/mathmod/labs/lab1/report/image/005.png)


## Коммит изменений

![проверьте состояние](/home/ghislain/work/study/2024-2025/Математическое моделирование/mathmod/labs/lab1/report/image/007.png)

## Добавьте стандартные теги страницы

![Измените страницу](/home/ghislain/work/study/2024-2025/Математическое моделирование/mathmod/labs/lab1/report/image/008.png)

![fig9](/home/ghislain/work/study/2024-2025/Математическое моделирование/mathmod/labs/lab1/report/image/009.png)

![fig10](/home/ghislain/work/study/2024-2025/Математическое моделирование/mathmod/labs/lab1/report/image/010.png)

![fig11](/home/ghislain/work/study/2024-2025/Математическое моделирование/mathmod/labs/lab1/report/image/011.png)


## Создание тегов версий

![fig24](/home/ghislain/work/study/2024-2025/Математическое моделирование/mathmod/labs/lab1/report/image/024.png)


## Просмотр тегов с помощью команды tag

![fig27](/home/ghislain/work/study/2024-2025/Математическое моделирование/mathmod/labs/lab1/report/image/027.png)


## Отмена локальных изменений (до индексации) и Измените hello.html


![fig28](/home/ghislain/work/study/2024-2025/Математическое моделирование/mathmod/labs/lab1/report/image/028.png)

![fig29](/home/ghislain/work/study/2024-2025/Математическое моделирование/mathmod/labs/lab1/report/image/029.png)


## Измените файл и проиндексируйте изменения

![fig32](/home/ghislain/work/study/2024-2025/Математическое моделирование/mathmod/labs/lab1/report/image/032.png)


## Переключитесь на версию коммита

![fig35](/home/ghislain/work/study/2024-2025/Математическое моделирование/mathmod/labs/lab1/report/image/035.png)

Наш рабочий каталог опять чист


## Отмена коммитов


![Изменить файл и сделать коммит](/home/ghislain/work/study/2024-2025/Математическое моделирование/mathmod/labs/lab1/report/image/036.png)


## Удаление коммиттов из ветки

Для начала отметьте эту ветку
Сброс коммитов к предшествующим коммиту Oops
Удаление тега oops

![fig42](/home/ghislain/work/study/2024-2025/Математическое моделирование/mathmod/labs/lab1/report/image/042.png)

![fig43](/home/ghislain/work/study/2024-2025/Математическое моделирование/mathmod/labs/lab1/report/image/043.png)

[fig45](/home/ghislain/work/study/2024-2025/Математическое моделирование/mathmod/labs/lab1/report/image/045.png)


## Внесение изменений в коммиты

[fig46](/home/ghislain/work/study/2024-2025/Математическое моделирование/mathmod/labs/lab1/report/image/046.png)

![fig47](/home/ghislain/work/study/2024-2025/Математическое моделирование/mathmod/labs/lab1/report/image/047.png)


## Измените предыдущий коммит и переместите файл hello.html в каталог lib


![fig50](/home/ghislain/work/study/2024-2025/Математическое моделирование/mathmod/labs/lab1/report/image/050.png)

![fig52](/home/ghislain/work/study/2024-2025/Математическое моделирование/mathmod/labs/lab1/report/image/052.png)


## Коммит в новый каталог

![fig53](/home/ghislain/work/study/2024-2025/Математическое моделирование/mathmod/labs/lab1/report/image/053.png)


## Добавление index.html

![fig54](/home/ghislain/work/study/2024-2025/Математическое моделирование/mathmod/labs/lab1/report/image/054.png)


## Работа непосредственно с объектами git

- Поиск последнего коммита 
- Вывод последнего коммита с помощью SHA1 хэша

![fig62](/home/ghislain/work/study/2024-2025/Математическое моделирование/mathmod/labs/lab1/report/image/062.png)

![fig63](/home/ghislain/work/study/2024-2025/Математическое моделирование/mathmod/labs/lab1/report/image/063.png)


## Создание ветки, Добавьте файл стилей style.css, Измените основную страницу и Измените index.html


![fig68](/home/ghislain/work/study/2024-2025/Математическое моделирование/mathmod/labs/lab1/report/image/068.png)

![fig69](/home/ghislain/work/study/2024-2025/Математическое моделирование/mathmod/labs/lab1/report/image/069.png)

![fig70](/home/ghislain/work/study/2024-2025/Математическое моделирование/mathmod/labs/lab1/report/image/070.png)

![fig72](/home/ghislain/work/study/2024-2025/Математическое моделирование/mathmod/labs/lab1/report/image/072.png)

![fig73](/home/ghislain/work/study/2024-2025/Математическое моделирование/mathmod/labs/lab1/report/image/073.png)

![fig74](/home/ghislain/work/study/2024-2025/Математическое моделирование/mathmod/labs/lab1/report/image/074.png)

![fig75](/home/ghislain/work/study/2024-2025/Математическое моделирование/mathmod/labs/lab1/report/image/075.png)



## Изменения в ветке master

- Создайте файл README в ветке master

![fig79](/home/ghislain/work/study/2024-2025/Математическое моделирование/mathmod/labs/lab1/report/image/079.png)

- Сделайте коммит изменений README.md в ветку master

![fig80](/home/ghislain/work/study/2024-2025/Математическое моделирование/mathmod/labs/lab1/report/image/080.png)


## Создание конфликта

- Вернитесь в master и создайте конфликт

![fig84](/home/ghislain/work/study/2024-2025/Математическое моделирование/mathmod/labs/lab1/report/image/084.png)

## Разрешение конфликтов

Вернемся к ветке style и попытаемся объединить ее с новой веткой
master.

![fig86](/home/ghislain/work/study/2024-2025/Математическое моделирование/mathmod/labs/lab1/report/image/086.png)


## Клонирование репозиториев

![fig96](/home/ghislain/work/study/2024-2025/Математическое моделирование/mathmod/labs/lab1/report/image/096.png)

![fig97](/home/ghislain/work/study/2024-2025/Математическое моделирование/mathmod/labs/lab1/report/image/097.png)

![fig98](/home/ghislain/work/study/2024-2025/Математическое моделирование/mathmod/labs/lab1/report/image/098.png)

![fig99](/home/ghislain/work/study/2024-2025/Математическое моделирование/mathmod/labs/lab1/report/image/099.png)


# Выводы

В процессе выполнения данной лабораторной работы я приобрела практические навыки работы с Git.

