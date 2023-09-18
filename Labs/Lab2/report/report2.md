---
## Front matter
title: "Отчёт по лабораторной работе 2"
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

 Получение практических навыковработыв консоли с атрибутами файлов,закрепление теоретических основ дискреционного разграничения доступа в современных системах с открытым кодом на базе ОС Linux1.

# Выполнение лабораторной работы

1.Вустановленной при выполнении предыдущей лабораторной работы операционной системе создайте учётную запись пользователя guest(использую учётную запись администратора): useraddguest 

![Рис. 1.2. Окно Имя машины и тип ОС](image/labinfo1.png){#fig:001 width=70%}


![Рис. 1.2.  Окно «Размер основной памяти»](image/labinfo2.png){#fig:001 width=70%}

2.Задайте пароль для пользователя guest(использую учётную запись администратора):

![Рис. 1.4. Окно подключения или создания жёсткого диска на виртуальной машине](image/labinfo3.png){#fig:001 width=70%}

3.Войдите в систему отимени пользователя guest.  

![Рис. 1.8. Окно «Носители» виртуальной машины: подключение образа оптического диска](image/labinfo4-4.png){#fig:001 width=70%}

4.Определите директорию,вкоторой вы находитесь,командой pwd.Сравните её с приглашением командной строки.Определите,является лиона вашей домашней директорией?Если нет,зайдите в домашнюю директорию.

![Рис. 1.9. Запуск виртуальной машины](image/labinfo5-5.png){#fig:001 width=70%}


![Рис. 1.10. Установка английского языка интерфейса ОС](image/labinfo4.png){#fig:001 width=70%}

5.Уточните имя вашего пользователя командой whoami.
![Рис. 1.11. Окно настройки установки образа ОС](image/labinfo5.png){#fig:001 width=70%}

![Рис. 1.11. Окно настройки установки образа ОС](image/labinfo6.png){#fig:001 width=70%}

6.Уточните имя вашего пользователя,его группу,а также группы,куда входит пользователь,командой id.Выведенные значения uid,gid и др.запомните.Сравните вывод id с выводом команды groups.

![Рис. 1.12. Окно настройки установки: выбор программ](image/labinfo7.png){#fig:001 width=70%}


![Рис. 1.13. Окно настройки установки: отключение KDUMP](image/labinfo8.png){#fig:001 width=70%}

7.Сравните полученную информацию об именипользователя сданными, выводимыми в приглашении командной строки.
![Рис. 1.14. Окно настройки установки: место установки](image/labinfo10.png){#fig:001 width=70%}

8.Просмотрите файл/etc/passwd командой

![Рис. 1.15. Окно настройки установки: сеть и имя узла](image/labinfo9.png){#fig:001 width=70%}

9.Определите существующие в системе директории командой
![Рис. 1.17. Установка пароля для пользователя с правами администратора](image/labinfo10.png){#fig:001 width=70%}

10.Проверьте,какие расширенные атрибуты установленына под директориях,находящихся в директории/home,командой:
![Рис. 1.18. Завершение установки ОС](image/labinfo11.png){#fig:001 width=70%}


![Рис. 1.19. Первоначальная настройка ОС: переход к лицензии](image/labinfo12.png){#fig:001 width=70%}

11.Создайте в домашней директории под директорию dir1 командой mkdir dir1 Определите командами ls-l и lsattr,какие правадоступа и расширенные атрибуты были выставленына директорию dir1.

![Рис. 1.21. Подключение образа диска дополнений гостевой ОС](image/labinfo6-6.png){#fig:001 width=70%}

12.Снимите с директории dir1 все атрибуты командой chmod000 dir1 и проверьте с её помощью правильность выполнения команды ls-l
![Рис. 1.22. Запуск образа диска дополнений гостевой ОС](image/labinfo15.png){#fig:001 width=70%}

13.Попытайтесь создать в директории dir1 файл file1 командой echo"test">/home/guest/dir1/file1 Объясните,почему выполучили отказввы полнении операции по созданию файла? Оцените,как сообщение обошибке отразилось на создании файла?Проверьтекомандой ls-l/home/guest/dir1

![Название рисунка](image/labinfo16.png){#fig:001 width=70%}

14.Заполните таблицу «Установленные права и разрешённые действия» (см.табл.2.1),
![Название рисунка](image/labinfo17.png){#fig:001 width=70%}
![Название рисунка](image/labinfo18.png){#fig:001 width=70%}




# Выводы

  В ходе выполнения лабораторной работы я научилась установки операционной системы на виртуальную машину.

