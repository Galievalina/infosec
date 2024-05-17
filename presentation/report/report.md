---
## Front matter
title: "Внешний курс"
subtitle: "Основы кибербезопасности"
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

Изучить основы кибербезопасности. 

# Прохождение курса

1. Введение в курс

# Безопасность в сети

2. 1. Как работает интернет: базовые сетевые протоколы.

![Протокол прикладного уровня](image/2.1.1.png){#fig:001 width=95%}

![Протокол ТСР](image/2.1.2.png){#fig:002 width=95%}

![Адреса IPv-4](image/2.1.3.png){#fig:003 width=95%}

![DNS сервер](image/2.1.4.png){#fig:004 width=95%}

![Протокол в модели ТСР/IP](image/2.1.5.png){#fig:005 width=95%}

![Протокол htpp](image/2.1.6.png){#fig:006 width=95%}

![Протокол https](image/2.1.7.png){#fig:007 width=95%}

![Протокол TLS](image/2.1.8.png){#fig:008 width=95%}

![Протокол TLS](image/2.1.9.png){#fig:009 width=95%}

2. 2. Персонализация сети.

![Куки хранят](image/2.2.1.png){#fig:010 width=95%}

![Куки не используются](image/2.2.2.png){#fig:011 width=95%}

![Куки генерируются](image/2.2.3.png){#fig:012 width=95%}

![Сессионные куки](image/2.2.4.png){#fig:013 width=95%}

2. 3.  Браузер TOR. Анимация.

![Промежуточные узлы TOR ](image/2.3.1.png){#fig:014 width=95%}

![Браузер TOR](image/2.3.2.png){#fig:015 width=95%}

![Секретный ключ](image/2.3.3.png){#fig:016 width=95%}

![Браузер TOR](image/2.3.4.png){#fig:017 width=95%}

2. 4. Беспроводные сети Wi-Fi.

![Wi-Fi](image/2.4.1.png){#fig:018 width=95%}

![Протокол Wi-Fi](image/2.4.2.png){#fig:019 width=95%}

![Шифрование Wi-Fi](image/2.4.3.png){#fig:020 width=95%}

![Данные между хостом и роутером](image/2.4.4.png){#fig:021 width=95%}

![Метод](image/2.4.5.png){#fig:022 width=95%}

# Защита ПК/телефона

3. 1. Шифрование диска. 

![Загрузочный сектор диска](image/3.1.1.png){#fig:023 width=95%}

![Шифрование диска](image/3.1.2.png){#fig:024 width=95%}

![Жесткий диск](image/3.1.3.png){#fig:025 width=95%}

3. 2. Пароли. 

![Пароли](image/3.2.1.png){#fig:026 width=95%}

![Хранение паролей](image/3.2.2.png){#fig:027 width=95%}

![Капча](image/3.2.3.png){#fig:028 width=95%}

![Хэширование паролей](image/3.2.4.png){#fig:029 width=95%}

![Стойкость паролей](image/3.2.5.png){#fig:030 width=95%}

![Меры защиты паролей](image/3.2.6.png){#fig:031 width=95%}

3. 3. Фишинг. 

![Фишинговые ссылки](image/3.3.1.png){#fig:032 width=95%}

![Фишинговый имейл](image/3.3.2.png){#fig:033 width=95%}

3. 4. Вирусы. Примеры. 

![Спуфинг](image/3.4.1.png){#fig:034 width=95%}

![Вирус-троян](image/3.4.2.png){#fig:035 width=95%}

3. 5. Безопасность мессенджеров.

![Мессенджер Signal](image/3.5.1.png){#fig:036 width=95%}

![Сквозное шифрование](image/3.5.2.png){#fig:037 width=95%}

# Криптография на практике

4. 1. Введение в криптографию. 

![Криптографические примитивы](image/4.1.1.png){#fig:038 width=95%}

![Криптографическая хэш-функция](image/4.1.2.png){#fig:039 width=95%}

![Цифровые подписи](image/4.1.3.png){#fig:040 width=95%}

![Аутентификация сообщения](image/4.1.4.png){#fig:041 width=95%}

![Обмен ключам](image/4.1.5.png){#fig:042 width=95%}

4. 2. Цифровая подпись. 

![Протокол электронной подписи](image/4.2.1.png){#fig:043 width=95%}

![Алгоритм верификации](image/4.2.2.png){#fig:044 width=95%}

![Электронная подпись](image/4.2.3.png){#fig:045 width=95%}

![ФНС](image/4.2.4.png){#fig:046 width=95%}

![Сертификат ключа](image/4.2.5.png){#fig:047 width=95%}

4. 3. Электронные платежи.

![Платежные системы](image/4.3.1.png){#fig:048 width=95%}

![Многофакторная аутентификация](image/4.3.2.png){#fig:049 width=95%}

![Онлайн платежи](image/4.3.3.png){#fig:050 width=95%}

4. 4. Блокчейн. 

![Криптографическая хэш-функция](image/4.4.1.png){#fig:051 width=95%}

![Консенсус в некоторых системах](image/4.4.2.png){#fig:052 width=95%}

![Секретные ключи](image/4.4.3.png){#fig:053 width=95%}

# Выводы 

Сертификат не выдается.

![Окончание курса](image/5.png){#fig:054 width=95%}




