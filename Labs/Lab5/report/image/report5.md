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

Setuid, Setgid и Sticky Bit. Это специальные типы разрешений позволяют задавать расширенные права доступа на файлы или каталоги.
Статья будет полезна пользователям и администраторам, которые уже знакомы с настройкой базовых прав в операционных системах Linux.

## Создание программы

1.Вошли в систему от имени пользователя guest.

![Рис. 1.1.](image/infoseclab5-1.png){#fig:001 width=70%}

 2.Создали программу simpleid.c:

 ![Рис. 1.2. ](image/infoseclab5-2.png){#fig:001 width=70%}

3.Скомплилирули программу

 создан: gcc simpleid.c-osimpleid 

4.Выполнили программу  simpleid: ./simpleid 

5.Выполнили системную программу id: id исравните полученный вами результат с данными предыдущего пункта задания.

![Рис. 1.3. ](image/infoseclab5-3.png){#fig:001 width=70%}


6.Усложнили программу,добавив вывод действительных идентификаторов:

![Рис. 1.4. ](image/infoseclab5-4.png){#fig:001 width=70%}

Получившуюся программу назвали simpleid2.c. 

7.Скомпилирули и запустили simpleid2.c:

![Рис. 1.5. ](image/infoseclab5-5.png){#fig:001 width=70%}

8.Отимени супер пользователя выполнили команды:

![Рис. 1.6. ](image/nfoseclab5-6.png){#fig:001 width=70%}

9.Использовали sudo или повысили временно свои права с помощью su. Поясните,что делают эти команды. 

10.Выполнили проверку правильности установки новых атрибутов и смены владельца файла simpleid2:

![Рис. 1.7. ](image/infoseclab5-6.png){#fig:001 width=70%}

11.Запустите simpleid2 и id:

![Рис. 1.8. ](image/infoseclab5-6-6.png){#fig:001 width=70%}

12.Проделали тоже самое относительно SetGID-бита.

![Рис. 1.9. ](image/infoseclab5-6-6.png){#fig:001 width=70%}

13.Создали программу readfile.c:

![Рис. 1.10. ](image/infoseclab5-6-1.png){#fig:001 width=70%}


14.Откомпилирули её. gcc read file.c-oreadfile 

![Рис. 1.11. ](image/infoseclab5-8.png){#fig:001 width=70%}

15.Сменили владельца у файла read file.c(или любого другого текстового файла в системе)иизмените права так,чтобы только супер пользователь (root) мог прочитать его,aguest не мог.

![Рис. 1.12. ](image/infoseclab5-9.png){#fig:001 width=70%}

16.Проверели,что пользователь guest не может прочитать файл read file.c. 

![Рис. 1.13. ](image/infoseclab5-10.png){#fig:001 width=70%}

17.Сменили у программы readfile владельца и установили SetU’D-бит. 

18.Проверьли,может ли программа readfile прочитали файл readfile.c? 

19.Проверьли,может ли программа readfile прочитать файл/etc/shadow? Отразите полученный результат и ваши объяснения в отчёте.

![Рис. 1.14. ](image/infoseclab5-11.png){#fig:001 width=70%}

## Исследование Sticky-бита

1.Выяснили,установленли атрибут Sticky надиректории/tmp

2.Отимени пользователя guest создали файлfile01.txt в директории /tmp сословом test:  

3.Просмотрели атрибуты у только то созданного файла и разрешили чтение и запись для категории пользователей «все остальные»:

![Рис. 2.1. ](image/infoseclab5-12.png){#fig:001 width=70%}


4.От пользователя guest2 (не являющегося владельцем) получилось  прочитать файл

5.От пользователя guest2 получилось дозаписать в файл

6.Проверили содержимое файла командой

7.От пользователя guest2 попробовали  /tmp/file01.txt слово test3,стерев при этом всю имеющуюсяв файле информацию командой

Удалось  выполнить операцию 

8.Проверили содержимое файла командой

9.От пользователя guest2 попробовали удалить файл/tmp/file01.txt командой rm/tmp/file Ol.txt 

![Рис. 2.2. ](image/infoseclab5-13.png){#fig:001 width=70%}

Не Удалось удалить файл

10.Повысьли свои права до супер пользователя следующей командой su и выполнили после этого команду,снимающую атрибут t(Sticky-бит)с директории /tmp:

11.Покинили режим супер пользователя командой exit 

12.Отпользователя guest2 проверули,что атрибут аt у директории /tmp нет:

13.Повторили предыдущие шаги.Какие наблюдают сяиз мененияю 

14.Удалось  удалить файл от имени пользователя,не являющегося его владельцем .

15.Повысьли свои права до супер пользователя и верните атрибут t на директорию/tmp:

![Рис. 2.3. ](image/infoseclab5-14.png){#fig:001 width=70%}


# Вывод

  В ходе выполнения лабораторной работы мы рассмотрели работы механизма смены идентификатора процессов пользователей,а также влияние бита Sticky назапись и удаление файлов.

