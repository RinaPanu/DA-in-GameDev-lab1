# АНАЛИЗ ДАННЫХ И ИСКУССТВЕННЫЙ ИНТЕЛЛЕКТ [in GameDev]
Отчет по лабораторной работе #2 выполнил(а):
- Панюкова Екатерина Алексеевна
- РИ210947
Отметка о выполнении заданий (заполняется студентом):

| Задание | Выполнение | Баллы |
| ------ | ------ | ------ |
| Задание 1 | * | 60 |
| Задание 2 | * | 20 |
| Задание 3 | # | 20 |

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
Познакомиться с программными средствами для организации передачи данных между инструментами Google, Python и Unity.

## Задание 1 Реализовать совместную работу и передачу данных в связке Python - Google-Sheets - Unity. При выполнении задания использовать видео-материалы и исходные данные, предоставленные преподавателями курса.
Ход работы:
1)В облачном сервисе google console подключить API для работы с google sheets и google drive.
Сначала был создан новый проект в сервисе Google Console - "UnityDataSciece". Потом подключены необходимые API из маркетплейса (Google Sheets API и Google Drive API). Создан сервис аккаунт UnityServiceDataScience и затем указана роль "Editor". После я выгружен API-ключ. При создании сервиса появился Email, который необходимо занести в доступ в новую google-таблицу. Скриншот о проделанной работе:
![image](https://user-images.githubusercontent.com/113353473/195171291-57ae5261-195d-436e-938c-ca17e3a9483c.png)
2)Реализовать запись данных из скрипта на python в google-таблицу. Данные описывают изменение темпа инфляции на протяжении 11 отсчётных периодов, с учётом стоимости игрового объекта в каждый период.
![image](https://user-images.githubusercontent.com/113353473/195152179-0c4db89d-b6a0-4c68-b8fb-175ccf1f5917.png)
![image](https://user-images.githubusercontent.com/113353473/195152299-bec0d22d-d8df-4ce6-a534-b1bfdeb4efed.png)
3)Создать новый проект на Unity, который будет получать данные из google-таблицы, в которую были записаны данные в предыдущем пункте.
![image](https://user-images.githubusercontent.com/113353473/195153692-da79a7b3-9e52-4b76-a7bd-6827609103ef.png)
![image](https://user-images.githubusercontent.com/113353473/195155536-ab4a80c2-b3f7-4b78-b5e3-c4ca870c4462.png)
![image](https://user-images.githubusercontent.com/113353473/195159340-529ac7a3-2ea5-4a05-a3c4-7250fa56beff.png)
Значение из консоли совпадает с первым значением из таблицы, значит связка удалась.
4)Написать функционал на Unity, в котором будет воспроизводиться аудио-файл в зависимости от значения данных из таблицы.
![image](https://user-images.githubusercontent.com/113353473/195163232-e6dc6a50-70be-488e-9461-7b5ccaeb2572.png)

## Задание 2 Реализовать запись в Google-таблицу набора данных, полученных с помощью линейной регрессии из лабораторной работы №1.
![image](https://user-images.githubusercontent.com/113353473/195169263-769be8a6-0828-4262-abc3-fdece9fcd13a.png)

Будем выгружать разницу между текущей и предыдущей величиной loss. Рассмотрим 10 итераций.
![image](https://user-images.githubusercontent.com/113353473/195169661-2d7bcd50-66c0-4499-be3a-aab494633b9b.png)
![image](https://user-images.githubusercontent.com/113353473/195169712-3c04a84b-b2ad-4cc0-ae86-20cf0e92c3b4.png)
![image](https://user-images.githubusercontent.com/113353473/195169751-f5401384-3064-4cf8-bccd-8b9b85a0dbb2.png)
![image](https://user-images.githubusercontent.com/113353473/195169007-c4734560-80ae-411d-b30a-e8c328e08947.png)


## Выводы

В ходе работы освоена связка Python - Google Sheets - Unity.

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
