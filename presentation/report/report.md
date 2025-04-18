---
## Front matter
title: "доклад"
subtitle: "Игры чистой кооперации"
author: "Tуем Гислен"

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


## Введение  

Игры чистой кооперации представляют собой фундаментальный класс моделей в теории игр, где успех каждого игрока напрямую зависит от согласованных действий всех участников. В отличие от конкурентных игр, где выигрыш одного игрока означает проигрыш другого, кооперативные игры фокусируются на ситуациях, в которых взаимовыгодное сотрудничество возможно, но не гарантировано.  

![Кооперация vs. Конкуренция](/home/ghislain/work/study/2024-2025/Математическое моделирование/mathmod/presentation/report/image/5){ width=80% }  

Цель — детально разобрать структуру игр чистой кооперации, проанализировать их равновесия, рассмотреть динамические аспекты и продемонстрировать их применение в различных областях.  

---

## Теоретические основы  

### Определение и формальная модель  

Игра чистой кооперации — это некооперативная игра с несколькими равновесиями Нэша, в которых игроки выбирают **соответствующие** стратегии.  

**Формальная постановка**:  
- Два игрока: Игрок 1 и Игрок 2.  
- У каждого две стратегии: **C (Сотрудничать)** и **F (Отказаться от сотрудничества)**.  
- Выигрыши задаются матрицей:  

|           | Игрок 2: C | Игрок 2: F |  
|-----------|------------|------------|  
| **Игрок 1: C** | (a, a)     | (0, 0)     |  
| **Игрок 1: F** | (0, 0)     | (1, 1)     |  

### Интерпретация параметров  
- **a = 1**: Классическая игра чистой кооперации.  
- **a > 1**: Усиленная кооперация (например, дополнительная выгода от совместных действий).  

![Матрица выигрышей](/home/ghislain/work/study/2024-2025/Математическое моделирование/mathmod/presentation/report/image/1){ width=80% }  

### Условия кооперации  
Для устойчивой кооперации необходимо:  
1. **Взаимность**: Оба игрока должны выбрать **C**.  
2. **Доверие**: Отсутствие стимулов для отклонения.  
3. **Координация**: Механизм выбора между **(C, C)** и **(F, F)**.  

---

## Анализ равновесий  

### Равновесие Нэша  
В игре существуют два равновесия:  
1. **(C, C)**: Оба сотрудничают → выигрыш (a, a).  
2. **(F, F)**: Оба отказываются → выигрыш (1, 1).  

**Почему это равновесия?**  
- Если один игрок выбирает **C**, второму выгодно тоже выбрать **C** (иначе 0).  
- Если один выбирает **F**, второму выгодно выбрать **F** (иначе 0).  

### Парето-оптимальность  
- **(C, C)** Парето-доминирует **(F, F)** при a > 1.  
- Но **(F, F)** может быть более устойчивым из-за риска.  

### Риск-доминирование  
**(F, F)** является риск-доминирующим, если:  
- При неопределённости выбора оппонента, **F** даёт гарантированный выигрыш 1.  

![График равновесий](/home/ghislain/work/study/2024-2025/Математическое моделирование/mathmod/presentation/report/image/9){ width=70% }  

![График равновесий](/home/ghislain/work/study/2024-2025/Математическое моделирование/mathmod/presentation/report/image/3){ width=90% }  

---

## Динамические аспекты  

### Повторяющиеся взаимодействия  
В повторяющейся игре кооперация может поддерживаться стратегиями:  
- **"Око за око" (Tit-for-Tat)**: Начинай с **C**, затем повторяй действие оппонента.  
- **"Щедрый Tit-for-Tat"**: Иногда прощай отклонения.  

### Эволюционные модели  
В популяциях кооперация развивается, если:  
- Группы кооператоров получают больше выгод.  
- Существует механизм наказания "безбилетников".  

![Эволюция кооперации](/home/ghislain/work/study/2024-2025/Математическое моделирование/mathmod/presentation/report/image/8){ width=80% }  

---

## Приложения  

### Экономика  
- Создание картелей (если все соблюдают договорённости — прибыль высокая).  
- Совместные инвестиции в инфраструктуру.  

### Социальные науки  
- Коллективные действия (например, протесты).  
- Нормы поведения в обществе.  

### Биология и экология  
- Взаимовыгодные симбиозы (например, пчёлы и цветы).  
- Климатические соглашения между странами.  

---

## Заключение  

Игры чистой кооперации:  
- Показывают, как взаимовыгодные исходы зависят от согласованности.  
- Имеют два равновесия: **(C, C)** (оптимальное) и **(F, F)** (устойчивое).  
- Применяются в экономике, социологии, биологии.  

Более подробно в [@osborne_game_theory_2004], [@axelrod_evolution_1984], [@myerson_game_1991], [@sigmund_calculus_2010]

# Список литературы{.unnumbered}

::: {#refs}
:::

