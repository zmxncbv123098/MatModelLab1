---
# Front matter
lang: ru-RU
title: "Лабораторная работа 6"
subtitle: "Задача об эпидемии"
author: "Бешкуров Михаил Борисович"

# Formatting
toc-title: "Содержание"
toc: true # Table of contents
toc_depth: 2
fontsize: 12pt
linestretch: 1.5
papersize: a4paper
documentclass: scrreprt
polyglossia-lang: russian
polyglossia-otherlangs: english
mainfont: PT Serif
romanfont: PT Serif
sansfont: PT Sans
monofont: PT Mono
mainfontoptions: Ligatures=TeX
romanfontoptions: Ligatures=TeX
sansfontoptions: Ligatures=TeX,Scale=MatchLowercase
monofontoptions: Scale=MatchLowercase
indent: true
pdf-engine: lualatex
header-includes:
  - \linepenalty=10 # the penalty added to the badness of each line within a paragraph (no associated penalty node) Increasing the value makes tex try to have fewer lines in the paragraph.
  - \interlinepenalty=0 # value of the penalty (node) added after each line of a paragraph.
  - \hyphenpenalty=50 # the penalty for line breaking at an automatically inserted hyphen
  - \exhyphenpenalty=50 # the penalty for line breaking at an explicit hyphen
  - \binoppenalty=700 # the penalty for breaking a line at a binary operator
  - \relpenalty=500 # the penalty for breaking a line at a relation
  - \clubpenalty=150 # extra penalty for breaking after first line of a paragraph
  - \widowpenalty=150 # extra penalty for breaking before last line of a paragraph
  - \displaywidowpenalty=50 # extra penalty for breaking before last line before a display math
  - \brokenpenalty=100 # extra penalty for page breaking after a hyphenated line
  - \predisplaypenalty=10000 # penalty for breaking before a display
  - \postdisplaypenalty=0 # penalty for breaking after a display
  - \floatingpenalty = 20000 # penalty for splitting an insertion (can only be split footnote in standard LaTeX)
  - \raggedbottom # or \flushbottom
  - \usepackage{float} # keep figures where there are in the text
  - \floatplacement{figure}{H} # keep figures where there are in the text
---
# Цель работы

Ознакомление с простейшей моделью Эпидемии  и ее построение с помощью языка программирования Python. 

# Задание

1. Построить графики изменения числа особей в каждой из трех групп (восприимчивые к болезни (S), заболевшие люди (I), здоровые люди с иммунитетом (R)), если I(0) \leq I* (число инфицированных не превышает критического значения).
2. Построить графики изменения числа особей в каждой из трех групп (восприимчивые к болезни (S), заболевшие люди (I), здоровые люди с иммунитетом (R)), если I(0) > I* (число инфицированных выше критического значения).

# Выполнение лабораторной работы
  

Предположим, что некая популяция, состоящая из N особей, (считаем, что популяция изолирована) подразделяется на три группы. Первая группа - это восприимчивые к болезни, но пока здоровые особи, обозначим их через S(t). Вторая группа – это число
инфицированных особей, которые также при этом являются распространителями инфекции, обозначим их I(t). А третья группа, обозначающаяся через R(t) – это здоровые особи с иммунитетом к болезни.

До того, как число заболевших не превышает критического значения I* , считаем, что все больные изолированы и не заражают здоровых. Когда I(t) > I*, тогда инфицирование способны заражать восприимчивых к болезни особей.

Cкорость изменения числа особей, восприимчивых к болезни S(t) меняется по следующему закону:
$$ \frac{dS}{dt} = \begin{cases} -\alpha S, если I(t) > I^* \\ 0, если I(t) \leq I^* \end{cases} $$

Скорость изменения числа инфекционных особей I(t) меняется по следующему закону:
$$ \frac{dI}{dt} = \begin{cases} \alpha S - \beta I, если I(t) > I^* \\ - \beta I, если I(t) \leq I^* \end{cases} $$

Скорость изменения числа выздоравливающих особей R(t) меняется по следующему закону:
$$ \frac{dI}{dt} = \beta I $$

В нашем случае $\alpha=0.35$ - коэффициент заболеваемости, а $\beta=0.13$ - коэффициент выздоравливаемости.

1. Построим графики изменения числа инфекционных особей I(t) и числа выздоравливающих особей R(t), если число инфицированных не превышает критического значения (рис 1. -@fig:001) 

![График изменения I(t) и R(t), если I(0) \leq I*](images/1.png){ #fig:001 width=70% }

А теперь добавим график изменения числа особей, восприимчивых к болезни S(t), если число инфицированных не превышает критического значения (рис 2. -@fig:001) 

![График изменения S(t), I(t) и R(t), если I(0) \leq I*](images/2.png){ #fig:001 width=70% }

2. Теперь же построим графики изменения числа особей, восприимчивых к болезни S(t), числа инфекционных особей I(t) и числа выздоравливающих особей R(t), если число инфицированных выше критического значения (рис 3. -@fig:001) 

![График изменения S(t), I(t) и R(t), если I(0) > I*](images/3.png){ #fig:001 width=70% }


# Выводы

Ознакомился с простейшей моделью Эпидемии, построив для нее графики изменения числа особей в трех группах для двух случаев: I(0) \leq I* и I(0) > I*.

