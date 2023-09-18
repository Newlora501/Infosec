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

Получение практических навыков работы в консоли с атрибутами файлов для групп пользователей1.

# Выполнение лабораторной работы

 1.В установленной операционной системе создайте учётную запись пользователя guest(использую учётную запись администратора):

![Рис. 1.2. Окно Имя машины и тип ОС](image/labinfo1.png){#fig:001 width=70%}

2.Задайте пароль для пользователя guest(использую учётную запись администратора):
![Рис. 1.2.  Окно «Размер основной памяти»](image/labinfo2.png){#fig:001 width=70%}

3.Аналогично создайте второго пользователя guest2. 
4.Добавьте пользователя guest2 в группу guest:

![Рис. 1.4. Окно подключения или создания жёсткого диска на виртуальной машине](image/labinfo3.png){#fig:001 width=70%}


5.Осуществите вход в систему от двух пользователей на двух разных консолях:guest напервой консолии guest2 навторой консоли. 

6.Для обоих пользователей командой pwd определите директорию,в которой вынаходитесь.Сравните её с приглашениями командной строки. 

7.Уточните имя вашего пользователя,его группу,кто входит в неё ик каким группам принадлежитонсам.

![Рис. 1.8. Окно «Носители» виртуальной машины: подключение образа оптического диска](image/labinfo4-4.png){#fig:001 width=70%}


![Рис. 1.9. Запуск виртуальной машины](image/labinfo5-5.png){#fig:001 width=70%}

8.Сравните полученную информацию с содержимым файла /etc/group. Просмотрите файл командой

![Рис. 1.10. Установка английского языка интерфейса ОС](image/labinfo4.png){#fig:001 width=70%}

9.Отимени пользователя guest2 выполните регистрацию пользователя guest2 в группе guest командой

![Рис. 1.11. Окно настройки установки образа ОС](image/labinfo5.png){#fig:001 width=70%}

![Рис. 1.11. Окно настройки установки образа ОС](image/labinfo6.png){#fig:001 width=70%}


10.Отимени пользователя guest измените права директории /home/guest, разрешив все действия для пользователей группы:

![Рис. 1.12. Окно настройки установки: выбор программ](image/labinfo7.png){#fig:001 width=70%}


![Рис. 1.13. Окно настройки установки: отключение KDUMP](image/labinfo8.png){#fig:001 width=70%}

11.Отимени пользователя guest снимите с директории /home/guest/dir1 все атрибуты командой

![Рис. 1.14. Окно настройки установки: место установки](image/labinfo10.png){#fig:001 width=70%}

Сравните табл.2.1(из лабораторнойработы №2) и табл.3.1. На основании заполненной таблицы определите теилииные минимально необходимые права для выполнения пользователем guest2 операций внутри директории dir1 и заполните табл.3.2.

![Рис. 1.15. Окно настройки установки: сеть и имя узла](image/labinfo9.png){#fig:001 width=70%}


# Выводы

  В ходе выполнения лабораторной работы я научилась работать с атрибутами файлов для групп пользователей 1.

