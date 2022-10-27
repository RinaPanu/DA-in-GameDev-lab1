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

С помощью Anaconda Prompt нужно активировать новый ML-агент и скачать новые библиотеки: mlagents 0.28.0 (в моем случае я устанавливала на версию ниже), torch 1.7.1. Вводим команды.
![image](https://user-images.githubusercontent.com/113353473/198361952-5d49e748-1021-45fe-925a-71e4a2985b27.png)
![image](https://user-images.githubusercontent.com/113353473/198361993-889818df-ee3b-440c-846f-29438c9fe6ce.png)
![image](https://user-images.githubusercontent.com/113353473/198362035-c7548694-750a-40a0-a738-06bd0473fee6.png)
![image](https://user-images.githubusercontent.com/113353473/198362085-c96d3572-1988-4f0c-a098-1d5384a147c0.png)
![image](https://user-images.githubusercontent.com/113353473/198361733-cea773bf-d61b-4f9e-8456-1f43873bf5ef.png)

## Задание 2 В разделе «ход работы» пошагово выполнить каждый пункт с описанием и примером реализации задачи по теме лабораторной работы.
Ход работы:
1) Произвести подготовку данных для работы с алгоритмом линейной регрессии. 10 видов данных были установлены случайным образом, и данные находились в линейной зависимости. Данные преобразуются в формат массива, чтобы их можно было вычислить напрямую при использовании умножения и сложения.

![image](https://user-images.githubusercontent.com/113353473/192839424-076b8400-0eac-40f5-b64b-1643522f748e.png)
2) Определить связанные функции. 
Функция модели: определяет модель линейной регрессии wx+b. 
def model(a, b, x):
  return a*x + b
  
Функция потерь: функция потерь среднеквадратичной ошибки. 
def loss_function(a, b, x, y):
  num = len(x)
  prediction = model(a, b, x)
  return (0.5 / num) * (np.square(prediction - y)).sum()
  
Функция оптимизации: метод градиентного спуска для нахождения частных производных w и b.
def optimize(a, b, x, y):
  num = len(x)
  prediction = model(a, b, x)
  #Обновление значений a и b, поиском частных производных функций потерь на a и b
  da = (1.0 / num) * ((prediction - y) * x).sum()
  db = (1.0 / num) * ((prediction - y).sum())
  a = a - Lr * da
  b = b - Lr * db
  return a, b
  
Функция итерации: возвращает значения a и b.
def iterate(a, b, x, y, times):
  for i in range(times):
    a, b= optimize(a, b, x, y)
  return a, b

3) Начать итерацию
Шаг 1 Инициализация и модель итеративной оптимизации.
![image](https://user-images.githubusercontent.com/113353473/192852828-b4935d58-dc61-479a-ab0c-9bb2ebd1666d.png)
![image](https://user-images.githubusercontent.com/113353473/192853002-bf3f3ffd-feb9-4193-a429-057e1e892690.png)


Шаг 2 На второй итерации отображаются значения параметров, значения потерь и эффекты визуализации после итерации.
![image](https://user-images.githubusercontent.com/113353473/192853167-531be52d-028d-4d93-b6cc-1297e192ada9.png)
Шаг 3 Третья итерация показывает значения параметров, значения потерь и визуализацию после итерации
![image](https://user-images.githubusercontent.com/113353473/192853314-5df8e431-daf1-402f-af51-81e5f106e18e.png)

Шаг 4 На четвертой итерации отображаются значения параметров, значения потерь и эффекты визуализации
![image](https://user-images.githubusercontent.com/113353473/192853402-37a56310-124a-4b9d-b442-170f8716be7e.png)

Шаг 5 Пятая итерация показывает значение параметра, значение потерь и эффект визуализации после итерации
![image](https://user-images.githubusercontent.com/113353473/192853586-3f972e4d-d442-4d1e-ac36-dd1c216723ac.png)

Шаг 6 10000-я итерация, показывающая значения параметров, потери и визуализацию после итерации
![image](https://user-images.githubusercontent.com/113353473/192853702-69a7dffb-9941-4cd1-9aed-0f2987a82d7a.png)

Смотря на значения в консоли и графики по итерациям, можно проследить, что значения параметров a и b с каждой итерацией увеличиваются, а вот значения потерь, наоборот, уменьшаются.

## Задание 3 Изучить код на Python и ответить на вопросы:
- Должна ли величина loss стремиться к нулю при изменении исходных данных? Ответьте на вопрос, приведите пример выполнения кода, который подтверждает ваш ответ.

Если уменьшить исходные данные, то значение потерь тоже уменьшается (при изначальных данных значение потерь где-то 190, а при уменьшенных около 32)
Новые исходные данные:
x = [2, 4, 9, 20, 4, 28, 28, 13, 27, 5]
x = np.array(x)
y = [3, 6, 9, 20, 12, 30, 4, 1, 16, 14]
y = np.array(y)

![image](https://user-images.githubusercontent.com/113353473/192854001-72cdb632-7244-451a-b8ee-edda05ac5d63.png)

- Какова роль параметра Lr? Ответьте на вопрос, приведите пример выполнения кода, который подтверждает ваш ответ. В качестве эксперимента можете изменить значение параметра.
Если, к примеру, уведичить Lr в 10 рвз, то произойдут изменения с графиком:
![image](https://user-images.githubusercontent.com/113353473/192854316-91b2b75f-c070-49f6-ad14-fc12492b8154.png)
Разница между значениями при итерациях стала больше, чем со старым значением параметра Lr.
И, таким образом, можно сделать вывод, что параметр Lr отвечает за разницу значений после каждой итерации. (чем больше значение Lr, тем больше разница между значениями)

## Выводы

В ходе работы осуществленно ознакомление с Python на примере организации линейной регрессии. В первом задании был написан код на языке Python для вывода фразы "Hello, World" в сервисе Google.colab и на языке C# в Visual Studio Code, который был запущен в Unity. Во втором задании осуществленна рвбота с кодом, реализующим линейную регрессию, были найдены закономерности: значения параметров a и b с каждой итерацией увеличиваются, а значения потерь уменьшаются. В третьем задании в ходе анализа кода сделаны выводы: 
1)Если уменьшить исходные данные, то значение потерь тоже уменьшается
2)параметр Lr отвечает за разницу значений после каждой итерации.

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
