---
## Front matter
title: "Индивидуальный проект 2 этап"
subtitle: "Установка DVWA"
author: "Галиева Аделина Руслановна"

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
mainfont: PT Serif
romanfont: PT Serif
sansfont: PT Sans
monofont: PT Mono
mainfontoptions: Ligatures=TeX
romanfontoptions: Ligatures=TeX
sansfontoptions: Ligatures=TeX,Scale=MatchLowercase
monofontoptions: Scale=MatchLowercase,Scale=0.9
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


Установить DVWA в гостевую систему к Kali Linux.


# Выполнение лабораторной работы

1. Устанавливаем DVWA при помощи различных команд и данного нам репозитория. 

![Прописываем команды](image/1.png){#fig:001 width=95%}

![Прописываем команды](image/2.png){#fig:002 width=95%}

![Прописываем команды](image/3.png){#fig:003 width=95%}

![Прописываем команды](image/4.png){#fig:004 width=95%}

![Прописываем команды](image/5.png){#fig:005 width=95%}

![Прописываем команды](image/6.png){#fig:006 width=95%}

![Прописываем команды](image/7.png){#fig:007 width=95%}

![Прописываем команды](image/8.png){#fig:008 width=95%}

![Прописываем команды](image/9.png){#fig:009 width=95%}

![Прописываем команды](image/10.png){#fig:010 width=95%}


# Выводы

В ходе выполнения данного этапа я установила DVWA в гостевую систему к Kali Linux.


