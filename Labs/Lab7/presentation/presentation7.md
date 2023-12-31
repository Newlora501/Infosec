---
## Front matter
lang: ru-RU
title: Информационная безопасность компьютерных сетей
subtitle: Презентация к лабораторной работе № 7
author:
  - Еленга Невлора Люглеш
institute:
  - Российский университет дружбы народов, Москва, Россия
  - Факультет физико-математических и естественных наук, Москва, Россия
  - Кафедра прикладной информатики и теории вероятности, Москва, Россия
date: 21 октября 2023

## i18n babel
babel-lang: russian
babel-otherlangs: english

## Formatting pdf
toc: false
toc-title: Содержание
slide_level: 2
aspectratio: 169
section-titles: true
theme: metropolis
header-includes:
 - \metroset{progressbar=frametitle,sectionpage=progressbar,numbering=fraction}
 - '\makeatletter'
 - '\beamer@ignorenonframefalse'
 - '\makeatother'
---

# Информация

## Докладчик

:::::::::::::: {.columns align=center}
::: {.column width="70%"}

  * Еленга Невлора Люглеш
  * Студент 4-го курса
  * Группа НКНбд-01-20
  * Российский университет дружбы народов
  * 1032201673
  * <>

:::
::: {.column width="30%"}

:::
::::::::::::::

## Актуальность

   Гаммирование – это наложение (снятие) на открытые (зашифрованные) данные криптографической гаммы, то есть последовательности элементов данных, вырабатываемых с помощью некоторого криптографического алгоритма, для получения зашифрованных (открытых) данных.

   Шифрование в режиме однократного гаммирования – это один из методов симметричного шифрования, который используется для защиты информации от несанкционированного доступа. 

Шифрование в режиме однократного гаммирования – это метод симметричного шифрования, в котором побитово складывается (по модулю 2) открытый текст с ключом-гаммой. 

Ключ-гамма – это случайный битовый набор, который используется только для зашифрования одного сообщения и должен быть равен или более длинным, чем сам текст. Ключ-гамма порождается с помощью генератора случайных чисел и не должен быть известен злоумышленнику.

Как это работает?

Для шифрования в режиме однократного гаммирования мы используем операцию побитового XOR (исключающее ИЛИ), которая имеет следующую таблицу истинности:

![Рис. 1.3. ](image/дфи7шь1.png){#fig:001 width=70%}
 
## Цели и задачи

- Освоить на практике применение режима одно кратного гаммирования .   
- Описание программы
- Запуск программы

## Материалы и методы

- Python
- Библотека Numpy

## Результаты

1.Определили вид шифро текст а при известном ключе и известном открытом тексте.

![Рис. 1.1.Шифрование Текста в режиме однократного гаммирования ](image/infoseclab7_1.png){#fig:001 width=70%}


![Рис. 1.2.Дешифрование Текста ](image/infoseclab7_2.png){#fig:001 width=70%}

2.Определили ключ,спомощью которого шифро текст может быть преобразован в некоторый фрагмент текста,представляющий собой один из возможных вариантов прочтения открытого текста.

![Рис. 1.3. ](image/infoseclab7_3.png){#fig:001 width=70%}

![Рис. 1.4.Дешифрование Текста ](image/infoseclab7_4.png){#fig:001 width=70%}

## Вывод

   В ходе выполнения лабораторной работы мы освоили на практике применение режима одно кратного гаммирования.






