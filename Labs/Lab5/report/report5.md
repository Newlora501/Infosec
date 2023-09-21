---
## Front matter
title: "Отчёт по лабораторной работе 5"
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

 Изучение механизмов изменения идентификаторов,применения SetUID-иSticky-битов.Получение практических навыков работы в консоли с дополнительными атрибутами.Рассмотрение работы механизма смены идентификатора процессо впользователей,а также влияние бита Sticky назапись и удаление файлов.

# Выполнение лабораторной работы

## Создание программы

1.Войдите в систему от имени пользователя guest.

![Рис. 1.9.](image/labinfo5-5.png){#fig:001 width=70%}

 2.Создайте программу simpleid.c:

![Рис. 1.10. ](image/labinfo4.png){#fig:001 width=70%}

3.Скомплилируйте программуи убедитесь,что файл программы создан: gccsimpleid.c-osimpleid 
4.Выполните программу  simpleid: ./simpleid 
5.Выполните системную программу id: id исравните полученный вами результат с данными предыдущего пункта задания.

![Рис. 1.11. ](image/labinfo5.png){#fig:001 width=70%}

6.Усложните программу,добавив вывод действительных идентификаторов:

![Рис. 1.11. ](image/labinfo6.png){#fig:001 width=70%}

Получившуюся программу назовите simpleid2.c. 
7.Скомпилируйте и запустите simpleid2.c:

![Рис. 1.12. ](image/labinfo7.png){#fig:001 width=70%}

8.Отимени супер пользователя выполните команды:

![Рис. 1.13.](image/labinfo8.png){#fig:001 width=70%}

9.Используйте sudo или повысьте временно свои права с помощью su. Поясните,что делают эти команды. 
10.Выполните проверку правильности установки новых атрибутов и смены владельца файла simpleid2:
![Рис. 1.14. ](image/labinfo10.png){#fig:001 width=70%}

11.Запустите simpleid2 и id:
![Рис. 1.15. ](image/labinfo9.png){#fig:001 width=70%}

Сравните результаты. 
12.Проделайте тоже самое относительно SetGID-бита.

![Рис. 1.2.](image/labinfo2.png){#fig:001 width=70%}

13.Создайтепрограммуreadfile.c:

![Рис. 1.4.](image/labinfo3.png){#fig:001 width=70%}


14.Откомпилируйте её. gcc read file.c-oreadfile 
15.Смените владельца у файла read file.c(или любого другого текстового файла в системе)иизмените права так,чтобы только супер пользователь (root) мог прочитать его,aguest не мог.

![Рис. 1.8.](image/labinfo4-4.png){#fig:001 width=70%}

16.Проверьте,что пользователь guest не может прочитать файл read file.c. 

![Рис. 1.8.](image/labinfo4-4.png){#fig:001 width=70%}

17.Сменитеу программы readfile владельца и установите SetU’D-бит. 
18.Проверьте,может ли программа readfile прочитать файл readfile.c? 
19.Проверьте,может ли программа readfile прочитать файл/etc/shadow? Отразите полученный результат и ваши объяснения в отчёте.

![Рис. 1.8.](image/labinfo4-4.png){#fig:001 width=70%}

## Исследование Sticky-бита

1.Выясните,установленлиатрибутStickyнадиректории/tmp,длячего выполнитекоманду

![Рис. 1.8.](image/labinfo4-4.png){#fig:001 width=70%}

2.Отимени пользователя guest создайте файлfile01.txt в директории /tmp сословом test:  
3.Просмотрите атрибуты у только то созданного файла и разрешите чтение и запись для категории пользователей «все остальные»:

![Рис. 1.8.](image/labinfo4-4.png){#fig:001 width=70%}

4.Отпользователя guest2 (не являющегося владельцем)попробуйте прочитать файл

![Рис. 1.8.](image/labinfo4-4.png){#fig:001 width=70%}

5.Отпользователя guest2 попробуйте дозаписать в файл

![Рис. 1.8.](image/labinfo4-4.png){#fig:001 width=70%}

Удалось ли вам выполнить операцию? 
6.Проверьте содержимое файла командой

7.От пользователя guest2 попробуйте  /tmp/file01.txt слово test3,стерев при этом всю имеющуюсяв файле информацию командой

![Рис. 1.8.](image/labinfo4-4.png){#fig:001 width=70%}

Удалось ли вам выполнить операцию? 
8.Проверьте содержимое файла командой

![Рис. 1.8.](image/labinfo4-4.png){#fig:001 width=70%}

9.От пользователя guest2 попробуйте удалить файл/tmp/file01.txt командой rm/tmp/file Ol.txt 

![Рис. 1.8.](image/labinfo4-4.png){#fig:001 width=70%}

Удалось ли вам удалить файл?

10.Повысьте свои права до супер пользователя следующей командой su и выполните после этого команду,снимающую атрибут t(Sticky-бит)с директории /tmp:

![Рис. 1.8.](image/labinfo4-4.png){#fig:001 width=70%}

11.Покиньте режим супер пользователя командой exit 
12.Отпользователя guest2 проверьте,что атрибут аt у директории /tmp нет:

![Рис. 1.8.](image/labinfo4-4.png){#fig:001 width=70%}

13.Повторите предыдущие шаги.Какие наблюдают сяиз менения? 
14.Удалось ли вам удалить файл от имени пользователя,не являющегося его владельцем?Ваши наблюдения занесите в отчёт.

![Рис. 1.8.](image/labinfo4-4.png){#fig:001 width=70%}

15.Повысьте свои права до супер пользователя и верните атрибут t на директорию/tmp:

![Рис. 1.8.](image/labinfo4-4.png){#fig:001 width=70%}

# Выводы

  В ходе выполнения лабораторной работы я научилась работать в консоли с расширенными атрибутами файлов.

