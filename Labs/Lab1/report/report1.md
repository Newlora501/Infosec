---
## Front matter
title: "Отчёт по лабораторной работе 1"
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

Целью данной работы является приобретение практических навыков установки операционной системы на виртуальную машину, настройки минимально необходимых для дальнейшей работы сервисов.

Создать локальный каталог для выполнения заданий по предмету
Научиться оформлять отчёты с помощью легковесного языка разметки Markdown.

# Выполнение лабораторной работы
- Создаем новую виртуальную машину
 
![Рис. 1.2. Окно Имя машины и тип ОС](image/labinfo1.png){#fig:001 width=70%}


![Рис. 1.2.  Окно «Размер основной памяти»](image/labinfo2.png){#fig:001 width=70%}


![Рис. 1.4. Окно подключения или создания жёсткого диска на виртуальной машине](image/labinfo3.png){#fig:001 width=70%}



![Рис. 1.8. Окно «Носители» виртуальной машины: подключение образа оптического диска](image/labinfo4-4.png){#fig:001 width=70%}


![Рис. 1.9. Запуск виртуальной машины](image/labinfo5-5.png){#fig:001 width=70%}


![Рис. 1.10. Установка английского языка интерфейса ОС](image/labinfo4.png){#fig:001 width=70%}


![Рис. 1.11. Окно настройки установки образа ОС](image/labinfo5.png){#fig:001 width=70%}

![Рис. 1.11. Окно настройки установки образа ОС](image/labinfo6.png){#fig:001 width=70%}


### Установка имени пользователя и названия хоста

![Рис. 1.12. Окно настройки установки: выбор программ](image/labinfo7.png){#fig:001 width=70%}


![Рис. 1.13. Окно настройки установки: отключение KDUMP](image/labinfo8.png){#fig:001 width=70%}


![Рис. 1.14. Окно настройки установки: место установки](image/labinfo10.png){#fig:001 width=70%}



3. Создайте пользователя (вместо username укажите ваш логин в дисплейном классе):
adduser -G wheel username
4. Задайте пароль для пользователя (вместо username укажите ваш логин
в дисплейном классе):
passwd username

![Рис. 1.15. Окно настройки установки: сеть и имя узла](image/labinfo9.png){#fig:001 width=70%}


![Рис. 1.17. Установка пароля для пользователя с правами администратора](image/labinfo10.png){#fig:001 width=70%}


![Рис. 1.18. Завершение установки ОС](image/labinfo11.png){#fig:001 width=70%}


![Рис. 1.19. Первоначальная настройка ОС: переход к лицензии](image/labinfo12.png){#fig:001 width=70%}



![Рис. 1.21. Подключение образа диска дополнений гостевой ОС](image/labinfo6-6.png){#fig:001 width=70%}


![Рис. 1.22. Запуск образа диска дополнений гостевой ОС](image/labinfo15.png){#fig:001 width=70%}


![Название рисунка](image/labinfo16.png){#fig:001 width=70%}
![Название рисунка](image/labinfo17.png){#fig:001 width=70%}
![Название рисунка](image/labinfo18.png){#fig:001 width=70%}

### Домашнее задание


Можно использовать поиск с помощью grep:
dmesg | grep -i "то, что ищем"

1. Версия ядра Linux (Linux version).

![Название рисунка](image/labinfo19.png){#fig:001 width=70%}


2. Частота процессора (Detected Mhz processor).

![Название рисунка](image/labinfo20.png){#fig:001 width=70%}


3. Модель процессора (CPU0).

![Название рисунка](image/labinfo21.png){#fig:001 width=70%}


5. Тип обнаруженного гипервизора (Hypervisor detected).

![Название рисунка](image/labinfo22.png){#fig:001 width=70%}


# Выводы

  В ходе выполнения лабораторной работы я научилась установки операционной системы на виртуальную машину.

