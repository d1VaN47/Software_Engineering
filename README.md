# Тема 4. Функции и стандартные модули/библиотеки
Отчет по Теме #4 выполнил:
- Верхотуров Иван Сергеевич
- ПИЭ-21-1

| Задание | Лаб_раб | Сам_раб |
| ------ | ------ | ------ |
| Задание 1 | + | + |
| Задание 2 | + | + |
| Задание 3 | + | + |
| Задание 4 | + | + |
| Задание 5 | + | + |
| Задание 6 | + |  |
| Задание 7 | + |  |
| Задание 8 | + |  |
| Задание 9 | + |  |
| Задание 10 | + |  |

# Лабораторная работа

## Задание 1
Напишите функцию, которая выполняет любые арифметические  действия и выводит результат в консоль. Вызовите функцию используя  “точку входа”.

  ```python
def main():
    print(2+2)
if __name__ == "__main__":
    main()
```
  ### Результат
![Desktop_231027_1852](https://github.com/d1VaN47/Software_Engineering/assets/145551753/4a7c5649-1f34-4927-9a9c-28b52d3aa885)

## Краткий вывод:
В данном коде мы выполняем функцию main, которая вызовается через точку входа и выполняет print(2+2)

## Задание 2
Напишите функцию, которая выполняет любые арифметические  действия, возвращает при помощи return значение в место, откуда  вызывали функцию. Выведите результат в консоль. Вызовите функцию  используя “точку входа”.

  ```python
def main():
    return 2+2
if __name__ == "__main__":
    print(main())
```
  ### Результат
![Desktop_231027_1856](https://github.com/d1VaN47/Software_Engineering/assets/145551753/5d75a869-5cf1-476f-8a55-ec3e43ba9850)

## Краткий вывод:
В данном коде мы использовали return, который после выполнения функции возвращает получившееся значение

## Задание 3
Напишите функцию, в которую передаются два аргумента, над ними  производится арифметическое действие, результат возвращается туда,  откуда эту функцию вызывали. Выведите результат в консоль.  Вызовите функцию в любом небольшом цикле.

  ```python
def main(one, two):
    return one + two
for i in  range(5):
    answer = main(one=1,two=10)
    print(answer)
```
  ### Результат
![Desktop_231027_1900](https://github.com/d1VaN47/Software_Engineering/assets/145551753/adde6e87-6dd2-4495-8a23-d2bc2fa8ad28)

## Краткий вывод:
В данном коде мы вызываем функцию с 2 обязательными переменными, значения которых мы указали при вызове данной функции main(one=1,two=10)

## Задание 4
Напишите функцию, на вход которой подается какое-то изначальное  неизвестное количество аргументов, над которыми будет производится  арифметические действия. Для выполнения задания необходимо  использовать кортеж “*args”. На скриншоте ниже приведен пример  такой программы с комментариями.

  ```python
def main(x, *args):
    one = x
    two = sum(args)
    three = float(len(args))
    print(f"one={one}\ntwo={two}\nthree={three}")
    return x + sum(args) / float(len(args))
itog = main(10, 5, 8, 9, -7, 6, -1, 0, 9, 15, -29)
print(f"\nitog={itog}")
```
  ### Результат
![Desktop_231027_1911](https://github.com/d1VaN47/Software_Engineering/assets/145551753/9e5d51b2-5da8-400c-8b6b-266d3de82293)

## Краткий вывод:
В данном коде мы используем картеж *args, благодаря которому мы можем на вход функции подать любое кол-во аргументов.

## Задание 5
Напишите функцию, которая на вход получает кортеж “**kwargs” и  при помощи цикла выводит значения, поступившие в функцию. На  скриншоте ниже указаны два варианта вызова функции с “**kwargs” и  два варианта работы с данными, поступившими в эту функцию.  Комментарии в коде и теоретическая часть помогут вам разобраться в  этом нелегком аспекте. Вызовите функцию используя “точку входа”.

  ```python
def main(**kwargs):
    for i in kwargs.items():
        print(i[0], i[1])
    print()
    for key in kwargs:
        print(f"{key} = {kwargs[key]}")
if __name__ == "__main__":
    main(x = [1, 2, 3], y = [3, 3, 0], z = [2, 3, 0], q = [3, 3, 0], w = [3, 3, 0])
    print()
    main(**{"x" : [1, 2, 3], "y" : [3, 3, 0]})
```
  ### Результат
![Desktop_231027_1938](https://github.com/d1VaN47/Software_Engineering/assets/145551753/01bccb16-af57-4181-9386-2f1779160f45)

## Краткий вывод:
В данном коде используется **kwargs, с помощью которого на вход функции подаётся любое кол-во именованных аргументов.

Для вывода отдельно имени аргумента и его самого испльзуем print(i[0], i[1]), где i[0] - имя аргумента, а i[0] - значение данного аргумента

Так же print(f"{key} = {kwargs[key]}") выводит каждый ключ и соответствующее значение.

## Задание 6
Напишите две функции. Первая – получает в виде параметра  “**kwargs”. Вторая считает среднее арифметическое из значений  первой функции. Вызовите первую функцию используя “точку входа”  и минимум 4 аргумента.

  ```python
def main(**kwargs):
    for i, j in kwargs.items():
        print(f"{i}. Mean = {mean(j)}")
def mean(data):
    return sum(data) / float(len(data))
if __name__ == "__main__":
    main(x=[1,2,3], y=[3,3,0])
```
  ### Результат
![Desktop_231027_2005](https://github.com/d1VaN47/Software_Engineering/assets/145551753/6c0f45f8-0bfa-4310-9d1a-db90c2a6715c)

## Краткий вывод:
В данном коде мы вызываем функцию из другой функции с помощью print(f"{i}. Mean = {mean(j)}")

Для вычисления среднего арефметического мы во второй функции сумму аргумента делим на его длину.

## Задание 7
Создайте дополнительный файл .py. Напишите в нем любую функцию,  которая будет что угодно выводить в консоль, но не вызывайте ее в  нем. Откройте файл main.py, импортируйте в него функцию из нового  файла и при помощи “точки входа” вызовите эту функцию.

  ```python
from function import say_hello
if __name__ == "__main__":
    say_hello()

def say_hello():
    print("Hello students!")
```
  ### Результат
![Desktop_231027_2014](https://github.com/d1VaN47/Software_Engineering/assets/145551753/345da443-a3c9-4022-9ee5-8a9374d3ea6d)
![Desktop_231027_2014_1](https://github.com/d1VaN47/Software_Engineering/assets/145551753/c5de14c4-3f83-4a8a-aba2-8cd5e73c3eef)


## Краткий вывод:
Для использования функции из другого файла .py необходимо его импортировать - from function import say_hello - данный фрагмент кода импортирует определённую часть файла function

## Задание 8
Напишите программу, которая будет выводить корень, синус, косинус  полученного от пользователя числа.

  ```python
import  math
def main():
    value = int(input("Введите значение: "))
    print(math.sqrt(value))
    print(math.sin(value))
    print(math.cos(value))
if __name__ == "__main__":
    main()
```
  ### Результат
![Desktop_231027_2021](https://github.com/d1VaN47/Software_Engineering/assets/145551753/1fad338b-6ff0-43d2-968f-3f95784d6e03)

## Краткий вывод:
Для вычисления корня, косинуса и синуса необходимо импортировать math, тогда станут доступны sqrt, cos, sin

## Задание 9
Напишите программу, которая будет рассчитывать какой день недели  будет через n-нное количество дней, которые укажет пользователь.
  ```python
from datetime import datetime as dt
from datetime import timedelta as td
def main():
    print(f"Сегодня {dt.today().date()}. "
          f"День недели - {dt.today().isoformat()}")
    n = int(input("Введите кол-во дней: "))
    today = dt.today()
    result = today + td(days=n)
    print(f"Через {n} дней будет {result.date()}. "
          f"День недели - {result.isoweekday()}")
if __name__ == "__main__":
    main()
```
  ### Результат
![Desktop_231027_2032](https://github.com/d1VaN47/Software_Engineering/assets/145551753/b4e2e312-2f0d-45e5-a4f4-54c81f274879)

## Краткий вывод:
В данном коде мы импортируем модуль datatime для определения даты и расчётов.

## Задание 10
Напишите программу с использованием глобальных переменных,  которая будет считать площадь треугольника или прямоугольника в  зависимости от того, что выберет пользователь. Получение всей  необходимой информации реализовать через input(), а подсчет  площадей выполнить при помощи функций. Результатом программы  Михаил  будет число, равное площади, необходимой фигуры 

  ```python
global result
def rectangle():
    a = float(input("Ширина: "))
    b = float(input("Высота: "))
    global result
    result = a * b
def triangle():
    a = float(input("Основание: "))
    h = float(input("Высота: "))
    global result
    result = 0.5 * a * h
figure = input("1 - прямоугольник, 2 - треугольник: ")
if figure == "1":
    rectangle()
elif figure == "2":
    triangle()
print(f"Площадь: {result}")
```
  ### Результат
![Desktop_231028_0027](https://github.com/d1VaN47/Software_Engineering/assets/145551753/038b3fab-0960-482f-a0e6-fc342dde33b5)

## Краткий вывод:
Для определения фигуры мы устраиваем проверку, что выбрал пользователь, а далее в зависимости от этого выбора запускаем функцию расчёта площади треугольника или прямоугольника

Так же мы используем глобальную переменную, в которую записываем результат

# Самостоятельная работа
## Задание 1
Дайте подробный комментарий для кода, написанного ниже.  Комментарий нужен для каждой строчки кода, нужно описать что она  делает. Не забудьте, что функции комментируются по-особенному.

  ```python
from datetime import datetime # импортируем модуль datatime
from math import sqrt # импортируем функцию sqrt из модуля math
def main(**kwargs): # запускаем функцию с изменяемым кол-во переменных
    for key in kwargs.items(): # запускаем цикл for и перебераем все элементы kwargs
        result = sqrt(key[1][0] ** 2 + key[1][1] ** 2) #  вычисляем квадрат суммы квадратов
        print(result) # выводим результат вычисления
if __name__ == "__main__": # проверка запущен ли код
    start_time = datetime.now() # засекаем начальное время запуска программы
    main( # запускаем функцию main с н6абором аргументов
        one=[10, 3], # вводим аргумент
        two=[5, 4], # вводим аргумент
        three=[15, 13], # вводим аргумент
        four=[93, 53], # вводим аргумент
        five=[133, 15] # вводим аргумент
    )
    time_costs = datetime.now() - start_time #отнимаем время начала работы от конца работы программы
    print(f"Время выполнения программы - {time_costs}") # выводим итоговое время
```
  ### Результат
![Desktop_231028_0052](https://github.com/d1VaN47/Software_Engineering/assets/145551753/e2120db9-dbe3-4303-a0a5-a313bb348614)

## Краткий вывод:
В данном коде представлена система замера времени вычисления

## Задание 2
Напишите программу, которая будет заменять игральную кость с 6  гранями. Если значение равно 5 или 6, то в консоль выводится «Вы  победили», если значения 3 или 4, то вы рекурсивно должны вызвать  эту же функцию, если значение 1 или 2, то в консоль выводится «Вы  проиграли». При этом каждый вызов функции необходимо выводить в  консоль значение “кубика”. Для выполнения задания необходимо использовать стандартную библиотеку random. Программу нужно  написать, используя одну функцию и “точку входа”

  ```python
import random
def kubik():
    kub = random.randint(1,6)
    if kub < 3:
        print(f"Выпало число: {kub}")
        print("Вы проиграли")
    elif kub < 5:
        kubik()
    else:
        print(f"Выпало число: {kub}")
        print("Вы победили")



if __name__ == "__main__":
    kubik()
```
  ### Результат
![Desktop_231028_0102](https://github.com/d1VaN47/Software_Engineering/assets/145551753/82f226a9-6f22-4359-8d92-d7785cf54104)

## Краткий вывод:
Для выпадения рандомного числа из диапозона от 1 до 6 включительно, необходимо импортировать random

Далее для присваивания переменной рандомного числа используем random.randint(1,6) оно выдаёт рандомное число от 1 до 6

## Задание 3
Напишите программу, которая будет выводить текущее время, с  точностью до секунд на протяжении 5 секунд. Программу нужно  написать с использованием цикла. Подсказка: необходимо  использовать модуль datetime и time, а также вам необходимо как-то  “усыплять” программу на 1 секунду. 

  ```python
import time
import datetime
def chasi():
    for i in range(5):
        vremia = datetime.datetime.now()
        print(f"Время: {vremia}")
        time.sleep(1)

if __name__ == "__main__":
    chasi()
```
  ### Результат
![Desktop_231028_0108](https://github.com/d1VaN47/Software_Engineering/assets/145551753/1300129d-a5df-44e4-a553-ae4ca84811d3)

## Краткий вывод:
Для выполнения данного задания необходимо импортировать time и datatime

С помощью time мы усыпляем программу на 1 секунду

С помощью datatime мы выводим актуальное время

## Задание 4
Напишите программу, которая считает среднее арифметическое от  аргументов вызываемое функции, с условием того, что изначальное  количество этих аргументов неизвестно. Программу необходимо  реализовать используя одну функцию и “точку входа”

  ```python
def sr(*args):
    result = sum(args) / len(args)
    print(result)

if __name__ == "__main__":
    sr(1, 50, 80, 12, 15)
    sr(2, 2, 0, 6, 8)
```
  ### Результат
![Desktop_231028_0123](https://github.com/d1VaN47/Software_Engineering/assets/145551753/b8be39d7-0d98-4649-8014-be06f9ba2fb6)

## Краткий вывод:
В данном коде для вычисления среднего арифметического мы делим сумму чисел на из кол-во

Ввести возможно любое кол-во чисел, так как мы используем *args, которое позволяет ввести либое кол-во аргументов

## Задание 5
Создайте два Python файла, в одном будет выполняться вычисление  площади треугольника при помощи формулы Герона (необходимо  реализовать через функцию), а во втором будет происходить  взаимодействие с пользователем (получение всей необходимой  информации и вывод результатов). Напишите эту программу и  выведите в консоль полученную площадь.

  ```python
import geron
if __name__ == "__main__":
    a = int(input("Введите длину 1 стороны: "))
    b = int(input("Введите длину 2 стороны: "))
    c = int(input("Введите длину 3 стороны: "))
    geron.ger(a, b, c)




from math import sqrt
def ger(a, b, c):
    pp = (a + b + c) / 2
    result = sqrt(pp*(pp-a)*(pp-b)*(pp-c))
    print("Площадь треугольника: ", result)
```
  ### Результат
![Desktop_231028_0134](https://github.com/d1VaN47/Software_Engineering/assets/145551753/b18484fa-39ab-47fe-805e-b1de837f5862)
![Desktop_231028_0134_1](https://github.com/d1VaN47/Software_Engineering/assets/145551753/b93aa3dc-7d48-482a-b6c5-927e4ef5bc30)

## Краткий вывод:
Для выполнения задания создаём 2 файла .py, в одном из которых запуск программы с вводом пользователя, а во втором функция с вычислениями

Для использования функции мы импортируем её в первый файл - import geron
