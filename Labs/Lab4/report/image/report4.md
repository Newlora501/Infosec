---
## Front matter
title: "Отчёт по лабораторной работе 4"
subtitle: "Простейший вариант "
author: "Еленга Невлора Люглеш"

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

 Получение практических навыков работы в консоли с расширенными атрибутами файлов1.

# Выполнение лабораторной работы

 1.От имени пользователя guest определим расширенные атрибуты файла

 ![Рис. 1.](image/infoseclab4-1.png){#fig:001 width=70%}

 2.Установки команды

3.Попробуем установить на файл/home/guest/dir1/file1 расширенный атрибутa от имени пользователя guest:

![Рис. 2.](image/infoseclab4-2-5.png){#fig:001 width=70%}

В ответ получили отказ от выполнения операции.

4.Зайдем на третью консоль с правами администратора либо повысьте свои права с помощью команды su.Попробуем установить расширенный атрибутa на файл/home/guest/dir1/file1 от имени супер пользователя:

![Рис. 3.](image/infoseclab4-4.png){#fig:001 width=70%}


5.От пользователя guest проверяем правильность установления атрибута:

![Рис. 4.](image/infoseclab4-5.png){#fig:001 width=70%}

6.Выполнение дозапись в файл file1 слова «test» командой
 После этого выполним чтение файла file1 командой

 test было успешно записано в file1.

7.Попробуйем удалить файл file1 либо с тереть имеющуюся в нём информацию командой
Попробуйем переименовать файл. 

![Рис. 5.](image/infoseclab4-6-7.png){#fig:001 width=70%}

8.Попробуйум с помощью команды
установить на файл file1 права,например,запрещающие чтение и запись для владельца файла.
Удалось ли вам успешно выполнить указанные команды?

![Рис. 6. ](image/infoseclab4-8.png){#fig:001 width=70%}


9.Сними расширенный атрибутa с файла /home/guest/dirl/file1 от имени супер пользователя командой

![Рис. 7. ](image/infoseclab4-9.png){#fig:001 width=70%}

10.Повторим ваши действия пошагам,заменив атрибут «a» атрибутом «i». Удалось ли вам дозаписать информацию в файл ? Ваши наблюдения занесите в отчёт.

![Рис. 8. ](image/infoseclab4-10.png){#fig:001 width=70%}

![Рис. 9.](image/infoseclab4-10-1.png){#fig:001 width=70%}


# Выводы

  В ходе выполнения лабораторной работы мы научились работать в консоли с расширенными атрибутами файлов.

