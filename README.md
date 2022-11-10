# АНАЛИЗ ДАННЫХ И ИСКУССТВЕННЫЙ ИНТЕЛЛЕКТ [in GameDev]
Отчет по лабораторной работе #1 выполнил(а):
- Панюкова Екатерина Алексеевна
- РИ210947
Отметка о выполнении заданий (заполняется студентом):

| Задание | Выполнение | Баллы |
| ------ | ------ | ------ |
| Задание 1 | * | 60 |
| Задание 2 | * | 20 |
| Задание 3 | * | 20 |

знак "*" - задание выполнено; знак "#" - задание не выполнено;

Работу проверили:
- к.т.н., доцент Денисов Д.В.
- к.э.н., доцент Панов М.А.
- ст. преп., Фадеев В.О.

[![N|Solid](https://cldup.com/dTxpPi9lDf.thumb.png)](https://nodesource.com/products/nsolid)

[![Build Status](https://travis-ci.org/joemccann/dillinger.svg?branch=master)](https://travis-ci.org/joemccann/dillinger)

Структура отчета

- Данные о работе: название работы, фио, группа, выполненные задания.
- Цель работы.
- Задание 1.
- Код реализации выполнения задания. Визуализация результатов выполнения (если применимо).
- Задание 2.
- Код реализации выполнения задания. Визуализация результатов выполнения (если применимо).
- Задание 3.
- Код реализации выполнения задания. Визуализация результатов выполнения (если применимо).
- Выводы.
- ✨Magic ✨

## Цель работы
познакомиться с программными средствами для создания системы машинного обучения и ее интеграции в Unity.

## Задание 1 Реализовать систему машинного обучения в связке Python - Google-Sheets – Unity. При выполнении задания можно использовать видео-материалы и исходные данные, предоставленные преподавателями курса.
Ход работы
При этапе подготовки необходимо скачать папку с ML-агентом.Необходимо в новом 3D проекте Unity добавить .json – файлы. 
![image](https://user-images.githubusercontent.com/113353473/198330606-d859e35d-74c8-4b5f-812c-838254cb6d6d.png)

С помощью Anaconda Prompt нужно активировать новый ML-агент и скачать новые библиотеки: mlagents 0.28.0 (в моем случае на версию ниже), torch 1.7.1.
![image](https://user-images.githubusercontent.com/113353473/198361952-5d49e748-1021-45fe-925a-71e4a2985b27.png)
![image](https://user-images.githubusercontent.com/113353473/198361993-889818df-ee3b-440c-846f-29438c9fe6ce.png)
![image](https://user-images.githubusercontent.com/113353473/198362035-c7548694-750a-40a0-a738-06bd0473fee6.png)
![image](https://user-images.githubusercontent.com/113353473/198362085-c96d3572-1988-4f0c-a098-1d5384a147c0.png)
![image](https://user-images.githubusercontent.com/113353473/198361733-cea773bf-d61b-4f9e-8456-1f43873bf5ef.png)
Далее нужно создать TargetArea, в которой находится плоскость, шар и куб. Также нужно создать C# скрипт-файл, добавить в него код, опубликованный в материалах для работы, и привязать его к сфере
![image](https://user-images.githubusercontent.com/113353473/201060846-d15e7255-5184-4bdf-8efc-896f535628a2.png)
код:
![image](https://user-images.githubusercontent.com/113353473/201061421-31a6b597-0569-4f0c-b8ce-7fb8d2d1233b.png)
![image](https://user-images.githubusercontent.com/113353473/201061454-ac312c7b-ac95-437b-8780-bfb4e83f7a1c.png)
Объекту RollerAgent нужно добавить компоненты Decision Requester, Behavior Parameters с настройками:
![image](https://user-images.githubusercontent.com/113353473/201062844-581c603b-6fde-4d0d-bd92-aaa675077dad.png)
Запустить работу ml-агента
![image](https://user-images.githubusercontent.com/113353473/201073357-0e865fad-87ef-4ab7-a08f-2db36c902c5f.png)
<p>При запуске программы в консоли unity выводится код:
![image](https://user-images.githubusercontent.com/113353473/201074147-25a37f6c-2c29-4128-ae5e-5eb97858da14.png)
<p>У шара появилось такое поведение:
![image](https://user-images.githubusercontent.com/113353473/201074514-853b638b-097c-46f9-9d4a-2a7924096b44.gif)
Когда три модели:
![image](https://user-images.githubusercontent.com/113353473/201075230-fde0f864-29ab-498c-833c-3e5dab73f3fd.gif)
Когда девять моделей:
![image](https://user-images.githubusercontent.com/113353473/201075371-e6faf777-3e3f-4dfb-b3b4-205908d57967.gif)
Когда 27 моделей:
![image](https://user-images.githubusercontent.com/113353473/201075482-4cc31944-4114-4ee9-b2f4-7a55eb58854c.gif)
После завершеня обучения:
![image](https://user-images.githubusercontent.com/113353473/201075815-54b3297e-3444-4f17-8ab9-fd775fa89d6d.gif)

## Задание 2 Подробно опишите каждую строку файла конфигурации нейронной сети, доступного в папке с файлами проекта по ссылке. Самостоятельно найдите информацию о компонентах Decision Requester, Behavior Parameters, добавленных на сфере.
![image](https://user-images.githubusercontent.com/113353473/201080995-7f7eaeaf-58d9-4f97-b6c0-bfbcb147aa42.png)
![image](https://user-images.githubusercontent.com/113353473/201081070-348f7979-87b7-472c-8493-2095aa22fb6d.png)

## Задание 3 Доработайте сцену и обучите ML-Agent таким образом, чтобы шар перемещался между двумя кубами разного цвета. Кубы должны, как и в первом задании, случайно изменять координаты на плоскости.
1.Создать модель, в которой находится плоскость, шар и два куба:
![image](https://user-images.githubusercontent.com/113353473/201083128-72c225f8-5f11-480e-9c2c-ab27f5b02325.png)
2. Написать скрипт:
![image](https://user-images.githubusercontent.com/113353473/201083374-7a4f8d34-2738-4ba6-b607-62f7574700f2.png)
![image](https://user-images.githubusercontent.com/113353473/201083389-601ffc3d-298c-400b-8eb7-71621a268bb1.png)
![image](https://user-images.githubusercontent.com/113353473/201083444-18bfa284-fa08-4acd-b388-0d4c58a44cd9.png)
3. Задать шару настройки, аналогичные с первым заданием
4. После обучения модели в несколько этапов (3, 9, 27 моделей), видим такую работу модели:
 ![image](https://user-images.githubusercontent.com/113353473/201085839-a4e6a303-a89a-40ca-85c3-3e993a20b438.gif)

## Выводы

В ходе работы осуществленно ознакомление с программными средствами для создания системы машинного обучения и ее интеграции в Unity, а также выяснено, что при увеличении количества копий модели, она обучается быстрее.
<p>Игровой баланс это равновесие между персонажами, командами, тактиками игры и другими игровыми объектами. Системы машинного обучения могут помогать поддерживать баланс игры. Например, усложнять миссии, если персонаж имеет высокие характеристики. Или подстраивать характеристики NPC и мира, чтобы персонажу было интересно развиваться. Таким образом, МО позволяет более точно распределять игровые механики, которые подлежат балансу.

| Plugin | README |
| ------ | ------ |
| Dropbox | [plugins/dropbox/README.md][PlDb] |
| GitHub | [plugins/github/README.md][PlGh] |
| Google Drive | [plugins/googledrive/README.md][PlGd] |
| OneDrive | [plugins/onedrive/README.md][PlOd] |
| Medium | [plugins/medium/README.md][PlMe] |
| Google Analytics | [plugins/googleanalytics/README.md][PlGa] |

## Powered by

**BigDigital Team: Denisov | Fadeev | Panov**
