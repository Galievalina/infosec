
---
## Front matter
title: "Лабораторная работа №2"
subtitle: "Дискреционное разграничение прав в Linux. Основные атрибуты"
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


Получение практических навыков работы в консоли с атрибутами файлов, закрепление теоретических основ дискреционного разграничения доступа в современных системах с открытым кодом на базе OC Linux. 


# Выполнение лабораторной работы

1.  В установленной при выполнении предыдущей лабораторной работы операционной системе создаю учётную запись пользователя guest.

![Создание учетной записи для пользователя guest](image/1.png){#fig:001 width=95%}

2. Задаю пароль для пользователя guest.

![Создание пароля для пользователя guest](image/2.png){#fig:002 width=95%}

3. Входим в систему от имени пользователя guest.

![Входим в систему от пользователя guest](image/3.png){#fig:003 width=95%}

4. Определяем директорию, в которой мы находимся, командой pwd. Также определили, что она является домашней директорией.

![Домашняя директория](image/4.png){#fig:004 width=95%}

5. Уточняем имя пользователя командой whoami.

![Командой whoami уточнили имя пользователя](image/5.png){#fig:005 width=95%}

6. Уточняем имя пользователя, его группу, а также группы, куда входит пользователь, командой id. Сравниваем вывод id с выводом команды groups.

![Сравнили две команды](image/6.png){#fig:006 width=95%}

7. Сравниваем полученную информацию об имени пользователя с данными, выводимыми в приглашении командной строки.

8. Просматриваем файл /etc/passwd командой cat /etc/passwd. Найдем в нём свою учётную запись. Определим uid пользователя. Определим gid пользователя. Сравним найденные значения с полученными в предыдущих пунктах. Guest имеет те же идентификаторы 1001, наш пользователь под идентификатором 1002. 

![Файл /etc/passwd](image/7.png){#fig:007 width=95%}

![Программа grep](image/8.png){#fig:008 width=95%}

9. Определяем существующие в системе директории командой ls -l /home/.

![Существующие директории](image/9.png){#fig:009 width=95%}

10. Проверяем, какие расширенные атрибуты установлены на поддиректориях, находящихся в директории /home, командой:
lsattr /home. Нам не удалось увидеть расширенные атрибуты директорий других пользователей, только своей домашней директории. 

![Расширенные атрибуты](image/10.png){#fig:010 width=95%}

11. Создаём в домашней директории поддиректорию dir1 командой mkdir dir1. Определяем командами ls -l и lsattr, какие права доступа и расширенные атрибуты были выставлены на директорию dir1.

![Создаём поддиректорию](image/11.png){#fig:011 width=95%}

12. Снимаем с директории dir1 все атрибуты командой сhmod 000 dir1 и проверяем с её помощью правильность выполнения команды ls -l. 

![Снимаем все атрибуты](image/12.png){#fig:012 width=95%}

13. Создаем в директории dir1 файл file1 командой echo "test" > /home/guest/dir1/file1. Поскольку ранее мы сняли все атрибуты, то тем самым лишили всех прав на взаимодействие с dir1. 

![Создаем файл](image/13.png){#fig:013 width=95%}

14. Заполняем таблицу "Установленные права и разрешённые действия", выполняя действия от имени владельца директории (файлов), определив опытным путём, какие операции разрешены, а какие нет. Если операция разрешена, занесите в таблицу знак «+», если не разрешена, знак «-».

Создание файла - 1
Удаление файла - 2
Запись в  файл - 3
Чтение файла - 4
Смена директории - 5
Просмотр файлов в директории - 6
Переименование файла - 7
Смена атрибутов файла - 8 

![Заполняем таблицу](image/14.png){#fig:014 width=95%}

![Установленные права и разрешенные действия](image/15.png){#fig:015 width=95%}

![Установленные права и разрешенные действия](image/16.png){#fig:016 width=95%}

![Установленные права и разрешенные действия](image/17.png){#fig:017 width=95%}

![Минимальные права для совершения операций](image/18.png){#fig:018 width=95%}


# Выводы

В ходе выполнения лабораторной работы я получила практические навыки работы в консоли с атрибутами файлов, закрепила теоретические основы дискреционного разграничения доступа в современных системах с открытым кодом на базе OC Linux.


