---
## Front matter
title: "Лабораторная работа №5"
subtitle: "Дискреционное разграничение прав в Linux. Исследование влияния дополнительных атрибутов"
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

Изучение механизмов изменения идентификаторов, применения SetUID- и Sticky-битов. Получение практических навыков работы в консоли с дополнительными атрибутами. Рассмотрение работы механизма смены идентификатора процессов пользователей, а также влияние бита Sticky на запись и удаление файлов.

# Выполнение лабораторной работы

1. Для выполнения части заданий требуются средства разработки приложений. Проверяем наличие установленного компилятора gcc -v: компилятор обнаружен. 

2. Чтобы система защиты SELinux не мешала выполнению заданий работы, отключили систему запретов до очередной перезагрузки системы командой setenforce 0. 

3. Команда getenforce вывела Permissive. 

![Подготовка](image/1.png){#fig:001 width=95%}

4. Входим в систему от имени пользователя guest. 

5. Создаем команду simpleid.c. 

![Программа simpleid.c](image/2.png){#fig:002 width=95%}

6. Компилируем программу и убеждаемся, что файл программы создан. 

7. Выполняем программу simpleid. 

8. Выполняем системную программу id и gid совпадает в обеих программах. 

![Результат программы simpleid](image/3.png){#fig:003 width=95%}

9. Усложняем программу, добавив вывод действительных идентификаторов. 

![Программа simpleid2](image/4.png){#fig:004 width=95%}

10. Компилируем и запускаем simpleid2.c. 

11. От имени суперпользователя выполняем команды: chown root:guest /home/guest/simpleid2, chmod u+s /home/guest/simpleid2

12. Используем su для повышения прав до суперпользователя. 

13. Выполняем проверку правильности установки новых атрибутов и смены владельца файла simpleid2. 

14. Запускаем simpleid2 и id. Результат выполнения программ теперь немного отличается. 

15. Проделаем тоже самое относительно SetGID-бита.

![Результат программы simpleid2](image/5.png){#fig:005 width=95%}

16. Создаем программу readfile.c. 

![Программа readfile](image/6.png){#fig:006 width=95%}

17. Откомпилируем её.  

18. Сменили владельца у файла readfile.c и меняем права так, чтобы только суперпользователь
(root) мог прочитать его, a guest не мог.

19. Проверяем, что пользователь guest не может прочитать файл readfile.c.

20. Меняем у программы readfile владельца и установите SetU’D-бит.

21. Проверяем, может ли программа readfile прочитать файл readfile.c.

22. Проверяем, может ли программа readfile прочитать файл /etc/shadow.

![Результат программы readfile](image/7.png){#fig:007 width=95%}

![Результат программы readfile](image/8.png){#fig:008 width=95%}

23. Выясняем, установлен ли атрибут Sticky на директории /tmp.

24. От имени пользователя guest создаем файл file01.txt в директории /tmp со словом test.

25. Просматриваем атрибуты у только что созданного файла и разрешаем чтение и запись для категории пользователей «все остальные». Первоначально все группы имели право на чтение, а запись могли осуществлять все, кроме "остальных пользователей".

26. От пользователя guest2 (не являющегося владельцем) пробуем прочитать файл /tmp/file01.txt.

27. От пользователя guest2 пробуем дозаписать в файл /tmp/file01.txt слово test2.

28. Проверяем содержимое файла. В файле теперь записано test test2.

29. От пользователя guest2 пробуем записать в файл /tmp/file01.txt слово test3, стерев при этом всю имеющуюся в файле информацию.

30. Проверяем содержимое файла командой cat /tmp/file01.txt.

31. От пользователя guest2 пробуем удалить файл /tmp/file01.txt командой rm /tmp/fileOl.txt. Получаем отказ.

32.  От суперпользователя проверили, что атрибута t у директории /tmp нет.

33. Повторяем предыдущие шаги. Получилось удалить файл. 

34. Удалось удалить файл от имени пользователя, не являющегося его владельцем. 

35. Повышаем свои права до суперпользователя и возвращаем атрибут t на директорию /tmp. 

![Исследование Sticky-бит](image/9.png){#fig:009 width=95%}


# Выводы

В ходе выполнения лабораторной работы я изучила механизмы изменения идентификаторов, применения SetUID- и Sticky-битов. Получила практические навыки работы в консоли с дополнительными атрибутами. Рассмотрела работы механизма смены идентификатора процессов пользователей, а также влияние бита Sticky на запись и удаление файлов.


