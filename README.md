# АНАЛИЗ ДАННЫХ И ИСКУССТВЕННЫЙ ИНТЕЛЛЕКТ [in GameDev]
Отчет по лабораторной работе #4 выполнил(а):
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
Познакомиться с работой перцептрона на практике при помощи движка Unity. Реализовать перцептрон который умеет решать логические операции.

## Задание 1 В проекте реализовать перцептрон, который умеет производить вычисления: OR, AND, NAND, XOR, и дать комментарии о кореектности работы.
Ход работы:
Создадим пустой проект на Unity. Создадим пустой объект и прикрепим ему код из методических указаний:
![image](https://user-images.githubusercontent.com/113353473/205294672-c2ae4a62-3736-452b-80b5-9724c4636704.png)
![image](https://user-images.githubusercontent.com/113353473/205294700-b421a96d-acb0-4873-9ad7-a5be7e22d5ec.png)
![image](https://user-images.githubusercontent.com/113353473/205294723-e1fa73d0-eb2a-42a5-bcb5-51ed0a02bea7.png)
![image](https://user-images.githubusercontent.com/113353473/205294762-56f0e0cf-b1fd-4064-bd9b-b1e95370a2b6.png)
1)Реализация операции OR | ИЛИ:
![image](https://user-images.githubusercontent.com/113353473/205295479-f3916c36-f0b7-4733-bd1a-955cffa8659f.png)
![image](https://user-images.githubusercontent.com/113353473/205296205-ca303ba8-de23-4c7e-a828-5ef86b3a5447.png)
![image](https://user-images.githubusercontent.com/113353473/205296866-35c248c8-a031-45ab-9a73-a50540927039.png)
Для начала зададим 1 обучающую эпоху и посмотрим на результаты наших тестов:
![image](https://user-images.githubusercontent.com/113353473/205298919-752e88f1-150b-4c3c-98d7-a3649758cd7a.png)
Значение Total Error отвечает за обучение перцептрона: если оно отлично от нуля, то модель не обучилась, если же нуль - тогда модель успешно обучилась. При первой эпохе обучения значение Total Error = 2, и из результатов тестов видно, что значения отличны от истины: в первом случае, ответ 1, хотя должен быть 0.
Зададим 4 эпохи обучения:
![image](https://user-images.githubusercontent.com/113353473/205299295-2d0b31fe-5776-4821-8878-43dd011274b4.png)
![image](https://user-images.githubusercontent.com/113353473/205299348-945cd755-e07f-4508-8691-52060e35c583.png)
![image](https://user-images.githubusercontent.com/113353473/205299408-3cd5fcd8-a970-4955-b1d1-6a734a798857.png)
![image](https://user-images.githubusercontent.com/113353473/205299452-c050d824-4d55-4819-9dd2-24060149ea21.png)
![image](https://user-images.githubusercontent.com/113353473/205299202-c07d1839-d6c1-4889-a3a7-92c9ea244fcf.png)
В данном случае уже при четвертой эпохе обучения Totl Error равняется нулю, и мы видим из результатов тестов, что модель успешно обучилась. Повторим запуск программы с 4 эпохами обучения:
![image](https://user-images.githubusercontent.com/113353473/205299642-94768bb1-9154-4bfe-8582-563a64d9a029.png)
Можем сделать вывод, что не всегда 4 эпохи обучения достаточно, бывает, что и при 4 итерации Total Error отлично от нуля и программа работает некорректно.
В ходе подбора количества эпох обучения, в моем случае, на пятой эпохе значение Total Error равно нулю. 
2)Реализация операции AND | И:
![image](https://user-images.githubusercontent.com/113353473/205300537-6ac567fd-df91-472d-b3c0-767577230339.png)
![image](https://user-images.githubusercontent.com/113353473/205300723-34b196aa-634d-41b6-8cba-e231a4cb3a43.png)
Для начала зададим 1 обучающую эпоху и посмотрим на результаты наших тестов:
![image](https://user-images.githubusercontent.com/113353473/205300853-51e0d607-4b41-4962-9303-8ed7fb3c8c32.png)![image](https://user-images.githubusercontent.com/113353473/205300952-9f701aec-83b5-4ead-8e3d-ec0d9d4d51ee.png)

Как и требовалось ожидать 1 эпохи обучения недостаточно для корректных ответов.
Зададим 4 эпохи:
![image](https://user-images.githubusercontent.com/113353473/205301114-66455977-507e-4199-92ce-a9bc63b59b60.png)
![image](https://user-images.githubusercontent.com/113353473/205301181-c114003b-43e5-4019-9fd2-0de75376c333.png)
![image](https://user-images.githubusercontent.com/113353473/205301223-4a49269a-e1af-43ab-a9f2-127c446c061c.png)
При данной операции и 4 эпох для обучения недостаточно. Попробуем 5:
![image](https://user-images.githubusercontent.com/113353473/205301462-56c06f2c-c0e0-4f36-883b-3011c0914f28.png)
![image](https://user-images.githubusercontent.com/113353473/205301528-5d06e050-c00b-4a44-aace-3d973e51a0a7.png)
![image](https://user-images.githubusercontent.com/113353473/205301570-85797da2-051b-4b48-98f8-5389740b2fd1.png)
В этот раз 5 эпох обучения было достаточно.

3)Реализация операции NAND | инвертированный элемент И:
![image](https://user-images.githubusercontent.com/113353473/205303619-a0b0dc15-ef27-461f-8128-31bac95d4cf5.png)
![image](https://user-images.githubusercontent.com/113353473/205303059-0764b39c-fc91-4d3a-81dd-fdac98375b86.png)
Для начала зададим 1 обучающую эпоху и посмотрим на результаты наших тестов:
![image](https://user-images.githubusercontent.com/113353473/205303796-35e71a14-347e-4bd8-ba16-50f4aa6e4e5a.png)
Одной эпохи для обучения мало. Установим 4:
![image](https://user-images.githubusercontent.com/113353473/205303981-02ebb0b5-d70a-4628-ab97-8cafce29ca10.png)
![image](https://user-images.githubusercontent.com/113353473/205304019-b363725b-de5b-426d-a086-f113321b743d.png)
![image](https://user-images.githubusercontent.com/113353473/205304049-ea547b9b-3692-4b68-a4e8-9bad918619b0.png)
Этого оказалось достаточно.
4) Реализация операции XOR | исключающее ИЛИ:
![image](https://user-images.githubusercontent.com/113353473/205304349-6eabd4b6-95c3-4655-b308-dca9ef95239c.png)
![image](https://user-images.githubusercontent.com/113353473/205304933-ee7d0e22-49ab-4521-9cf4-b69041d6faf4.png)
Для начала зададим 1 обучающую эпоху и посмотрим на результаты наших тестов:
![image](https://user-images.githubusercontent.com/113353473/205304654-4f1f33a4-fab1-406d-a082-bb9364334f7c.png)
Как и ранее, этого недостаточно.Установим 4 эпохи
![image](https://user-images.githubusercontent.com/113353473/205305393-84e23110-20d1-4b52-9884-345e93a6705e.png)
![image](https://user-images.githubusercontent.com/113353473/205305443-2df754fc-8b8e-4f3c-aa6a-c792067fe17e.png)
![image](https://user-images.githubusercontent.com/113353473/205305469-d5874311-ffd0-40ba-994e-c411a8675522.png)
Снова не достаточно. Установим 8 эпох.
![image](https://user-images.githubusercontent.com/113353473/205306303-ca69f29c-d2c4-4aec-9b35-20eba6b96914.png)
![image](https://user-images.githubusercontent.com/113353473/205306339-2e0e7cda-4adb-450b-9da7-4374dde5d906.png)
![image](https://user-images.githubusercontent.com/113353473/205306374-51a865c7-50d4-4f36-acfd-2ddf94cfc3fd.png)
![image](https://user-images.githubusercontent.com/113353473/205306449-f741e12e-f74e-464d-818c-f536c42d3bdb.png)
![image](https://user-images.githubusercontent.com/113353473/205306479-03218c01-2e54-42a9-bf47-18589dd00f35.png)
При нескольких попытках восьми эпох было мало для обучения. В ходе работы с разными значениями эпох обучения было выяснено, что начиная с третьей-четвертой эпохи значение Total Error всегда было равно 4. Следовательно - однослойный перцептрон не может обучиться этой операции.
Однослойный перцептрон в силах решать линейные задачи, а XOR таковой не является.
Можно сделать вывод, что один слой перцептрона может решать только линейные задачи: AND, OR, NAND. Для решения нелинейной задачи XOR он не подходит.


## Задание 2 Построить графики зависимости количества эпох от ошибки обучения. Указать от чего зависит необходимое количество эпох обучения.
Для каждой операции было запущено 4 попытки с 8-ю эпохами обучения. На графиках указано среднее значение Total Error за 4 попытки.
Операция OR | ИЛИ
![image](https://user-images.githubusercontent.com/113353473/205310783-583b6781-bdcb-4ca7-8070-627f172f7cb8.png)
Операция AND | И
![image](https://user-images.githubusercontent.com/113353473/205311366-d4848ee9-9829-43ab-95ec-8c77e3ec5b22.png)
Операция NAND | инвертированный элемент И
![image](https://user-images.githubusercontent.com/113353473/205312346-7083613a-ada6-426a-a418-de24437d9ee4.png)

Операция XOR | исключающее ИЛИ
![image](https://user-images.githubusercontent.com/113353473/205313923-2085a464-9595-4782-8df7-48a9a260579c.png)
Количество эпох обучения зависит от операции. Статистика не совсем точная, так как взято небольшое количество попыток - 4.


## Задание 3 Построить визуальную модель работы перцептрона на сцене Unity.
Для начала создадим сцену с двумя вариантами: (черный куб - 0, белый куб - 1(0;0), (0;1)/(1;0) и (1;1).
![203351251-3ba686f5-2af7-4c51-87df-d033bca84dc9 gif](https://user-images.githubusercontent.com/113353473/205325316-9311c2a0-005e-45b8-bf2a-fdedefa2fbd9.jpg)

При их столкновении они оба окрасятся в цвет результата того или иного исхода.

Для этого в коде нужно завести две переменных, которые будут отвечать за обозначение куба (0 или 1). И уже эти значения подставлять в функцию CalcOutput для определения результата операции после обучения модели. Также у верхнего куба нужно поставить Rigidbody, а у нижнего - Is trigger. Новый код:
![image](https://user-images.githubusercontent.com/113353473/205321570-9e005bc8-8810-4f3e-9492-1a666f95c5cb.png)
![image](https://user-images.githubusercontent.com/113353473/205321631-c3d654cb-f521-4569-bf7e-c93d4982ac42.png)
![image](https://user-images.githubusercontent.com/113353473/205321684-1b1a8a11-3e4c-493d-9821-160cfc3a8974.png)
![image](https://user-images.githubusercontent.com/113353473/205321715-e8fc262e-260a-40fc-872c-decc10b15979.png)
![image](https://user-images.githubusercontent.com/113353473/205321761-339e9b91-03b2-4d65-b6d4-230f98a44dbb.png)

результат работы для операции ИЛИ:


https://user-images.githubusercontent.com/113353473/205325006-981b152a-477b-4ffc-98cf-74bfae67e3d3.mp4


## Выводы!


В ходе лабороторной работы познакомилась с моделью нейроной сети - перцептроном. С помощью однослойного перцептрона смогла реализовать такие логические операции как OR, AND, NAND. Операцию XOR однослойным прецептроном реализовать не удалось. Таким образом однослойный перцептрон можен решить только линейные задачи.Также построила графики для оценки обучаемости модели той или иной операции.Применив функционал Unity, построила наглядную модель работы перцептрона:

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
