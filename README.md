# Тема 10. Декораторы и исключения
Отчет по Теме #10 выполнил:
- Верхотуров Иван Сергеевич
- ПИЭ-21-1

| Задание | Лаб_раб | Сам_раб |
| ------ | ------ | ------ |
| Задание 1 | + | + |
| Задание 2 | + | + |
| Задание 3 | + | + |
| Задание 4 | + | + |
| Задание 5 | + | + |

# Лабораторная работа

## Задание 1
Наверняка вы думаете, что декораторы – это какая-то бесполезная  вещь, которая вам никогда не пригодится, но тут вдруг на паре по  математике преподаватель просит всех посчитать число Фибоначчи для  100. Кто-то будет считать вручную (так точно не нужно), кто-то  посчитает на калькуляторе, а кто-то подумает, что он самый крутой и  напишет рекурсивную программу на Python и немного огорчится,  потому что данная программа будет достаточно долго считаться, если  ее просто так запускать. Но именно тут к вам на помощь приходят  декораторы, например @lru_cache (он предназначен для решения задач  динамическим программированием, если простыми словами, то этот  декоратор запоминает промежуточные результаты и при рекурсивном  вызове функции программа не будет считать одни и те же значения, а  просто “возьмёт их из этого декоратора”). Вам нужно написать  программу, которая будет считать числа Фибоначчи для 100 и  запустить ее без этого декоратора и с ним, посмотреть на разницу во  времени решения поставленной задачи.  P.S. при запуске без декоратора можете долго не ждать, для  наглядности хватит 10 секунд ожидания

  ```python
from functools import lru_cache

@lru_cache(None)
def fibonacci(n):
    if n == 0:
        return 0
    elif n == 1:
        return 1
    return fibonacci(n-1) + fibonacci(n-2)
if __name__ == '__main__':
    print(fibonacci(100))
```
### Результат
![Desktop_231206_1728](https://github.com/d1VaN47/Software_Engineering/assets/145551753/15995e7b-dfe8-40f2-b5b0-acb9ed8d6a9d)

## Краткий вывод:
Благодаря декоратору программа выполняется очень быстро, так как она повторно не проводит расчёты, а берёт их из декоратора.

## Задание 2
Илья пишет свой сайт и ему необходимо сделать минимальную  проверку ввода данных пользователя при регистрации. Для этого он  реализовал функцию, которая выводит данные пользователя на экран и  решил, что будет проверять правильность введённых данных при  помощи декоратора, но в этом ему потребовалась ваша помощь.  Напишите декоратор для функции, который будет принимать все  параметры вызываемой функции (имя, возраст) и проверять чтобы  возраст был больше 0 и меньше 130.  Причем заметьте, что неважно сколько пользователь введет данных на  сайт к Илье, будут обрабатываться только первые 2 аргумента

  ```python
def check(input_func):
    def output_func(*args):
        name, age = args[0], args[1]
        if age < 0 or age > 130:
            age = 'Недопустимый возраст'
        input_func(name, age)
    return output_func

@check
def personal_info(name, age):
    print(f"Name: {name} Age: {age}")

if __name__ == '__main__':
    personal_info('Владимир', 38)
    personal_info('Александр', -5)
    personal_info('Петр', 138, 15, 48, 2)
```
### Результат
![Desktop_231206_1738](https://github.com/d1VaN47/Software_Engineering/assets/145551753/965f0165-8367-40c1-a9e3-ea6350d53360)

## Краткий вывод:
В данном коде мы создали свой декоратор, который проводит проверку одной из поступающих переменных age, если она не попадает в диапозон от 0 до 130, то заменяет значение переменной на ошибку и выводит.

## Задание 3
Вам понравилась идея Ильи с сайтом, и вы решили дальше работать  вместе с ним. Но вот в вашем проекте появилась проблема, кто-то  пытается сломать вашу функцию с получением данных для сайта. Эта  функция работает только с данными integer, а какой-то недохакер  пытается все сломать и вместо нужного типа данных отправляет string Воспользуйтесь исключениями, чтобы неподходящий тип данных не  ломал ваш сайт.  Также дополнительно можете обернуть весь код функции в  try/except/finally для того, чтобы программа вас оповестила о том, что  выявлена какая-то ошибка или программа успешно выполнена

  ```python
def data(*args):
    try:
        for i in range(len(*args)):
            try:
                result = (args[0][i]*15) // 10
                print(result)
            except Exception as ex:
                print(ex)
    except Exception as ex:
        print(ex)
    finally:
        print('Вся информация обработана')

if __name__ == '__main__':
    data([1, 15, 'Hello', 'i', 'try', 'to', 'crash', 'your', 'site', 38, 45])
```
### Результат
![Desktop_231206_1746](https://github.com/d1VaN47/Software_Engineering/assets/145551753/4e445b3a-2668-4b6d-8ba5-5b11a5a65b72)

## Краткий вывод:
В данном коде мы реализовали проверку вводимых значений с помощью try/except/finally, которые выводят ошибку в случае, если пользователь вводит неподходящие значения.

## Задание 4
Продолжая работу над сайтом, вы решили написать собственное  исключение, которое будет вызываться в случае, если в функцию  проверки имени при регистрации передана строка длиннее десяти  символов, а если имя имеет допустимую длину, то в консоль  выводиться “Успешная регистрация”

  ```python
class NegativeValueException(Exception):
    pass

def check_name(name):
    if len(name) > 10:
        raise NegativeValueException('Длина более 10 символов')
    else:
        print('Успешная регистрация')

if __name__ == '__main__':
    name = '12345678910'
    check_name(name)
```
### Результат
![Desktop_231206_2003](https://github.com/d1VaN47/Software_Engineering/assets/145551753/8d5dbd11-cfe2-4f76-88c1-cefcf15ff5a9)

## Краткий вывод:
В данном коде мы создали класс, который выводит ошибку в консоль, и в случае когда name имеет длину более 10 символов вызывается этот класс и передаётся ошибка.

## Задание 5
После запуска сайта вы поняли, что вам необходимо добавить логгер,  для отслеживания его работы. Готовыми вариантами вы не захотели  пользоваться, и поэтому решили создать очень простую пародию. Для  этого создали две функции: __init__() (вызывается при создании класса  декоратора в программе) и __call__() (вызывается при вызове  декоратора). Создайте необходимый вам декоратор. Выведите все логи  в консоль

  ```python
class SiteChecker:
    def __init__(self, func):
        print('> Класс SiteChecker метод __init__ успешный запуск')
        self.func = func

    def __call__(self):
        print('> Проверка перед запуском', self.func.__name__)
        self.func()
        print('> Проверка безопасности выключения')

@SiteChecker
def site():
    print('Усердная работа сайта')

if __name__ == '__main__':
    print('>> Сайт запущен')
    site()
    print('>> Сайт выключен')
```
### Результат
![Desktop_231206_2011](https://github.com/d1VaN47/Software_Engineering/assets/145551753/a9b8ce25-7bcf-4958-9ee8-d3bf5e86b857)

## Краткий вывод:
Данный код реализован с помиощью класса с 2мя методами, первый __init__, который срабатывает при создании класса декоратора, а второй __call__, при вызове декоратора.

# Самостоятельная работа
## Задание 1
Вовочка решил заняться спортивным программированием на python, но  для этого он должен знать за какое время выполняется его программа.  Он решил, что для этого ему идеально подойдет декоратор для  функции, который будет выяснять за какое время выполняется та или  иная функция. Помогите Вовочке в его начинаниях и напишите такой  декоратор.

  ```python
def secundomer(func):
    def wrapper(*args, **kwargs):
        start_time = time.time()
        result = func(*args, **kwargs)
        end_time = time.time()
        itog = end_time - start_time
        print(f"\nВремя выполнения {func.__name__}: {itog} секунд")
        return result
    return wrapper

@secundomer
def fibonacci():
    fib1 = fib2 = 1
    for i in range(2, 200):
        fib1, fib2 = fib2, fib1 + fib2
        print(fib2, end='')

if __name__ == '__main__':
    fibonacci()
```
### Результат
![Desktop_231206_2029](https://github.com/d1VaN47/Software_Engineering/assets/145551753/df704b41-4d0d-4e1d-aaec-bb75dcd0d8c2)

## Краткий вывод:
Для выполнения данного задания мы создаём декоратор secundomer, который считает начал выполения и конец выполнения и тем самым находит время выполнения кода в секундах и выводит его.

## Задание 2
Посмотрев на Вовочку, вы также загорелись идеей спортивного  программирования, начав тренировки вы узнали, что для решения  некоторых задач необходимо считывать данные из файлов. Но через  некоторое время вы столкнулись с проблемой что файлы бывают  пустыми, и вы не получаете вводные данные для решения задачи.  После этого вы решили не просто считывать данные из файла, а всю  конструкцию оборачивать в исключения, чтобы избежать такой проблемы. Создайте пустой файл и файл, в котором есть какая-то  информация. Напишите код программы. Если файл пустой, то, нужно  вызвать исключение (“бросить исключение”) и вывести в консоль  “файл пустой”, а если он не пустой, то вывести информацию из файла.

  ```python
def opener(file):
    with open(file, 'r') as file:
        file_content = file.read()
    if file_content == "":
        print("Файл пустой")
    else:
        print(file_content)


if __name__ == '__main__':
    opener('1.txt')
    opener('2.txt')
```
### Результат
![Desktop_231206_2047](https://github.com/d1VaN47/Software_Engineering/assets/145551753/635f43ba-d6c2-4c88-82fc-bbd4fbce2518)

## Краткий вывод:
Для реализации данного задания мы создаём класс, который на вход получает название файла, далее открывает его и проверяет пустой ли файл, если пустой то выводит, что файл пуст, а если есть текст, то он его выводит в консоль.

## Задание 3
Напишите функцию, которая будет складывать 2 и введенное  пользователем число, но если пользователь введет строку или другой  неподходящий тип данных, то в консоль выведется ошибка  “Неподходящий тип данных. Ожидалось число.”. Реализовать  функционал программы необходимо через try/except и подобрать  правильный тип исключения. Создавать собственное исключение  нельзя. Проведите несколько тестов, в которых исключение вызывается  и нет. Результатом выполнения задачи будет листинг кода и  получившийся вывод в консоль

  ```python
def opener():
    try:
        a = int(input("Введите число: "))
        sum = a + 2
        print(sum)
    except ValueError:
        print("Неподходящий тип данных. Ожидалось число")

if __name__ == '__main__':
    opener()
```
### Результат
![Desktop_231206_2055](https://github.com/d1VaN47/Software_Engineering/assets/145551753/31ff2d1a-548d-4519-b85b-336a8038222c)

## Краткий вывод:
Для выполнения задания мы использовали конструкцию try/except с исключением ValueError, которое срабатывает когда пользователь вводит, что либо вместо числа и выводит сообщение о неправильно введённых данных.

## Задание 4
Создайте собственный декоратор, который будет использоваться для  двух любых вами придуманных функций. Декораторы, которые  использовались ранее в работе нельзя воссоздавать. Результатом  выполнения задачи будет: класс декоратора, две как-то связанными с  ним функциями, скриншот консоли с выполненной программой и  подробные комментарии, которые будут описывать работу вашего  кода.

  ```python
class Decorator:
    def __init__(self,func):
        self.func = func
    def __call__(self, *args):
        x, y = args[0], args[1]
        if x*x == y:
            print("Второе число является квадратом первого ")
        elif y*y == x:
            print("Первое число является квадратом второго ")
        else:
            print("просто два числа")
        self.func(*args)
@Decorator
def opener(a, b):
    itog = a * b + b ^ 3 // 2
    print(itog)

@Decorator
def closer(a, b):
    aa = a * a
    bb = b * b
    print(f"Число {aa} является квадратом числа {a}\nЧисло {bb} является квадратом числа {b}")

if __name__ == '__main__':
    a =int(input("Ведите первое число "))
    b =int(input("Ведите второе число "))
    opener(a, b)
    closer(a, b)
```
### Результат
![Desktop_231206_2128](https://github.com/d1VaN47/Software_Engineering/assets/145551753/be2668dc-fb84-4556-8fd3-4c6f12373470)

## Краткий вывод:
В данном коде реализован декоратор, который определяет являются ли введёные числа квадратами друг друга и выводит об этом сообщение.

## Задание 5
Создайте собственное исключение, которое будет использоваться в  двух любых фрагментах кода. Исключения, которые использовались  ранее в работе нельзя воссоздавать. Результатом выполнения задачи  будет: класс исключения, код к котором в двух местах используется это  исключение, скриншот консоли с выполненной программой и  подробные комментарии, которые будут описывать работу вашего  кода

  ```python
class MyException(Exception):
    def __init__(self, erro="ОШИБКА! Вы не передали значение"):
        self.error = erro
        super().__init__(self.error)

def pervii(i):
    if not i:
        raise MyException
    else:
        itog = i * i * 5 // (i + 1)
        print(itog)

def vtoroy(b):
    kub = b * b * b
    print(kub)

if __name__ == '__main__':
    i = None
    b = int(input("Введите число_2: "))
    try:
        vtoroy(b)
    except MyException as x:
        print(x.error)
    pervii(i)
```
### Результат
![Desktop_231206_2153](https://github.com/d1VaN47/Software_Engineering/assets/145551753/7f908d34-1638-4f64-ba36-467170ddd9e2)

## Краткий вывод:
Для выполнения данного задания создаём класс, которыq в случае исключения (ожидалось, что будет передано число, но этого не произошло) выводит ошибку в консоль.
