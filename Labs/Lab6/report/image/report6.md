---
## Front matter
title: "Отчёт по лабораторной работе 6"
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

  Развить навыки администрирования ОСLinux.Получить первое практическое знакомствос технологией SELinux1. Проверить работу SELinx  напрактике совместно с веб-сервером Apache.

# Алтуальность

Веб-сервер Apache – это программное обеспечение, которое установлено на сам сервер. Как мы уже поняли, благодаря ему устанавливается соединение между юзером, использующим браузер, и сервером, чтобы осуществить передачу данных при запросе. Пользователь переходит на страницу, далее отправляется сигнал на обработку, Apache находит необходимые данные и возвращает их пользователю, чтобы тот смог ознакомиться с ними.

# Выполнение лабораторной работы

1.Вошли в систему с полученными учётными данными и убедились,что SELinux работает  в режиме enforcing  политики targeted с помощью команд getenforce и sestatus. 

2.Обратились с помощью браузера к веб-серверу,запущенному на вашем компьютере,иубедитесь,что последний работает: service httpd status или /etc/rc.d/init.d/httpdstatus 

 ![Рис. 1.1. ](image/infoseclab6_1-2.png){#fig:001 width=70%}

3.Нашли веб-сервер Apache в списке процессов,определите его контекст безопасности изанесите эту информацию в отчёт.Например,можно использовать команду

![Рис. 1.2. ](image/infoseclab6_3.png){#fig:001 width=70%}

4.Посмотрули текущее состояние переключателей SELinux для Apacheс помощью команды sestatus-bigrep httpd 
Многие из них находятся вположении «off». 

![Рис. 1.3. ](image/infoseclab6_4.png){#fig:001 width=70%}

5.Посмотрули статистику пополитике с помощью команды seinfo,также определите множество пользователей,ролей,типов. 

6.Определили тип файлов и поддиректорий,находящихся в директории /var/www,с помощью команды


7.Определили тип файлов,находящихся в директории/var/www/html: ls-lZ/var/www/html 

![Рис. 1.4. ](image/infoseclab6_6-6-7.png){#fig:001 width=70%}

8.Определили круг пользователей,которымразрешеносозданиефайловв директории/var/www/html. 

9.Создали отимени суперпользователя(так как в дистрибутиве после установки только ему разрешена запись в директорию)html-файл /var/www/html/test.html следующего содержания:

![Рис. 1.5. ](image/infoseclab6_8.png){#fig:001 width=70%}

![Рис. 1.6. ](image/infoseclab6_8-9.png){#fig:001 width=70%}

10.Проверили контекст созданного вами файла.Занесили в отчёт контекст, присваиваемый по умолчанию вновь созданным файлам в директории /var/www/html.

![Рис. 1.7. ](image/infoseclab6_10.png){#fig:001 width=70%}

11.Обратились к файлу через веб-сервер,введя в браузере адрес http://127.0.0.1/test.html.Убедитесь,что файл был успешно отображён.

![Рис. 1.8. ](image/infoseclab6_11.png){#fig:001 width=70%}

12.Изучили справку man httpd_selinuxи выясните,какие контексты файлов определены для httpd.Сопоставили их с типом файла test.html.Проверили контекст файла можно командой ls-Z..

13.Изменили контекст файла /var/www/html/test.html с httpd_sys_content_t на любой другой,к которому процесс httpd не должен иметь доступа,например,наsamba_share_t:

![Рис. 1.9. ](image/infoseclab6_12-13.png){#fig:001 width=70%}


14.Попробовали ещё разполучить доступ к файлу через веб-сервер,введяв браузере адрес http://127.0.0.1/test.html.

 Получили сообщение обошибке:

![Рис. 1.10. ](image/ifnoseclab6_14.png){#fig:001 width=70%}

15.Проанализировали ситуацию.Почему файл не был отображён,если права доступа позволяют читать этот файл  любому пользователю ls-l/var/www/html/test.html Просмотрите log-файлы веб-сервера Apache.Также просмотрели системный лог-файл:

!![Рис. 1.11. ](image/infoseclab6_15.png){#fig:001 width=70%}

16.Запустили веб-сервер Apache на прослушивание ТСР-порта 81(ане80,как рекомендует IANA и прописанов/etc/services).Для этого в файле/etc/httpd/httpd.conf найдите строчку Listen 80и заменили её на Listen 81. 

![Рис. 1.12. ](image/infoseclab6_16.png){#fig:001 width=70%}


17.Выполнили перезапуск веб-сервера Apache.

![Рис. 1.13. ](image/infoseclab6_17.png){#fig:001 width=70%}

18.Проанализирули лог-файлы: tail-nl/var/log/messages

![Рис. 1.14. ](image/infoseclab6_15-2.png){#fig:001 width=70%}

![Рис. 1.15. ](image/infoseclab6_15-1.png){#fig:001 width=70%}

19.Выполнили команду semanage port-a-thttp_port_t -р tcp 81 После этого проверили список портовкомандой semanage port-l|grep http_port_t

![Рис. 1.16. ](image/infoseclab6_17-1.png){#fig:001 width=70%}

20.Попробовали запустить веб-сервер Apache ещё раз.

![Рис. 1.17. ](image/infoseclab6_17.png){#fig:001 width=70%}


21.Вернили контекст httpd_sys_cоntent__t к файлу/var/www/html/test.html: chcon-thttpd_sys_content_t/var/www/html/test.html 

После этого попробовали получить доступ к файлу через веб-сервер,введя в браузере адрес http://127.0.0.1:81/test.html. 
Видели содержимое файла—слово«test».

![Рис. 1.18. ](image/infoseclab6_17-2.png){#fig:001 width=70%}

22.Исправили обратно конфигурационный файлa pache,вернув Listen80.

23.Удалили привязку http_port_t к 81 порту: semanage port-d-thttp_port_t-ptcp81 и проверили,что порт 81 удалён. 

24.Удалили файли/var/www/html/test.html: rm /var/www/html/test.html

![Рис. 1.19. ](image/infoseclab6_23-24.png){#fig:001 width=70%}


# Вывод

  В ходе выполнения лабораторной работы мы получили первое практическое знакомствос технологией SELinux1. Проверили работу SELinx  напрактике совместно с веб-сервером Apache.

