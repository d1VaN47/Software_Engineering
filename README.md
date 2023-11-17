# Тема 8. Введение в ООП
Отчет по Теме #8 выполнил:
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
Создайте класс “Car” с атрибутами производитель и модель. Создайте  объект этого класса. Напишите комментарии для кода, объясняющие  его работу. Результатом выполнения задания будет листинг кода с  комментариями.

  ```python
class Car: #Создаёт класс car
    def __init__(self, make, model): #Конструктор init принимающий 2 аргумента
        self.make = make # Присвоение аргумента атрибуту
        self.model = model # Присвоение аргумента атрибуту
my_car = Car("Toyota", "Corolla") #Создание экземпляра класса с аргументами Toyota и Corolla
```
### Результат
![Desktop_231117_1355](https://github.com/d1VaN47/Software_Engineering/assets/145551753/a6d2328c-1dd4-45d2-9e0f-1d5d3c8effb7)

## Краткий вывод:
Создание экземпляра класса с аргументами

## Задание 2
Дополните код из первого задания, добавив в него атрибуты и методы  класса, заставьте машину “поехать”. Напишите комментарии для кода,  объясняющие его работу. Результатом выполнения задания будет  листинг кода с комментариями и получившийся вывод в консоль

  ```python
class Car: #Создаёт класс car
    def __init__(self, make, model): #Конструктор init принимающий 2 аргумента
        self.make = make # Присвоение аргумента атрибуту
        self.model = model # Присвоение аргумента атрибуту

    def drive(self): #Создание метода
        print(f"Driving the {self.make} {self.model}") #Вывод в консоль марки и модели объекта класса
my_car = Car("Toyota", "Corolla") #Создание экземпляра класса с аргументами Toyota и Corolla
my_car.drive() #вызов метода drive для объекта my_car
```
### Результат
![Desktop_231117_1404](https://github.com/d1VaN47/Software_Engineering/assets/145551753/6940c698-8a0f-4551-a538-818b7eaebc4b)

## Краткий вывод:
Создание экземпляра класса с последующим вызовом метода для него

## Задание 3
Создайте новый класс “ElectricCar” с методом “charge” и атрибутом  емкость батареи. Реализуйте его наследование от класса, созданного в  первом задании. Заставьте машину поехать, а потом заряжаться. Напишите комментарии для кода, объясняющие его работу.  Результатом выполнения задания будет листинг кода с комментариями  и получившийся вывод в консоль.

  ```python
class Car: #Создаёт класс car
    def __init__(self, make, model): #Конструктор init принимающий 2 аргумента
        self.make = make # Присвоение аргумента атрибуту
        self.model = model # Присвоение аргумента атрибуту

    def drive(self): #Создание метода
        print(f"Driving the {self.make} {self.model}") #Вывод в консоль марки и модели объекта класса
my_car = Car("Toyota", "Corolla") #Создание экземпляра класса с аргументами Toyota и Corolla
my_car.drive() #вызов метода drive для объекта my_car

class ElectricCar(Car): #Создаёт класс ElectricCar, наследующий класс Car
    def __init__(self, make, model, battery_capacity): # конструктор init принимающий 3 аргумента
        super().__init__(make, model) #Унаследование атрибутов make и model
        self.battery_capacity = battery_capacity # Присвоение аргумента атрибуту

    def charge(self): #Создание метода
        print(f"Charging the {self.make} {self.model} with {self.battery_capacity} kWh" ) #Вывод в консоль сообщения с атрибутами объекта
my_electric_car = ElectricCar("Tesla", "Model S", 75) #Создание экземпляра класса с аргументами Tesla, Model S и 75
my_electric_car.drive() #вызов метода drive для объекта my_electric_car
my_electric_car.charge() #вызов метода charge для объекта my_electric_car
```
### Результат
![Desktop_231117_1417](https://github.com/d1VaN47/Software_Engineering/assets/145551753/0a62c1ff-21b5-4a78-ac12-2a7568509a49)

## Краткий вывод:
Создание экземпляра класса с последующим вызовом метода для него. 

Создание нового класса ElectricCar с наследование car, создание экземпляра этого класса и вызов 2х методов для него

## Задание 4
Реализуйте инкапсуляцию для класса, созданного в первом задании.  Создайте защищенный атрибут производителя и приватный атрибут  модели. Вызовите защищенный атрибут и заставьте машину поехать.  Напишите комментарии для кода, объясняющие его работу.  Результатом выполнения задания будет листинг кода с комментариями  и получившийся вывод в консоль

  ```python
class Car: #Создаёт класс car
    def __init__(self, make, model): #Конструктор init принимающий 2 аргумента
        self._make = make # Защищённый атрибут
        self.__model = model # Приватный атрибут

    def drive(self): #Создание метода
        print(f"Driving the {self._make} {self.__model}") #Вывод в консоль атрибутов объекта класса
my_car = Car("Toyota", "Corolla") #Создание экземпляра класса с аргументами Toyota и Corolla
print(my_car._make) # вывод защищённого атрибута
my_car.drive() #вызов метода drive для объекта my_car
```
### Результат
![Desktop_231117_1425](https://github.com/d1VaN47/Software_Engineering/assets/145551753/8c50af48-3437-40cc-a95a-a59a3c4124ac)

## Краткий вывод:
Создание класса с защищёнными и приватными аргументами.

Создание экземпляра класса с последующим вызовом метода для него и защищённого аргумента 

## Задание 5
Реализуйте полиморфизм создав основной (общий) класс “Shape”, а  также еще два класса “Rectangle” и “Circle”. Внутри последних двух  классов реализуйте методы для подсчета площади фигуры. После этого  создайте массив с фигурами, поместите туда круг и прямоугольник,  затем при помощи цикла выведите их площади. Напишите  комментарии для кода, объясняющие его работу. Результатом  выполнения задания будет листинг кода с комментариями и  получившийся вывод в консоль.

  ```python
class Share: #Создаём класс
    def area(self): #Создание метода
        pass #Нулевой оператор, для дальнейшего заполнения
class Rectangle(Share): #Создаём класс с наследованием Share
    def __init__(self, width, height): #Конструктор init принимающий 2 аргумента
        self.width = width # Присвоение аргумента атрибуту
        self.height = height # Присвоение аргумента атрибуту
    def area(self): #Создание метода
        return self.width * self.height #Вовращаем ширину перемноженную на высоту
class Circle(Share): #Создаём класс с наследованием Share
    def __init__(self, radius): #Конструктор init принимающий 1 аргумент
        self.radius = radius # Присвоение аргумента атрибуту
    def area(self): #Создание метода
        return 3.14 * self.radius * self.radius #Возвращаем 3.14 умноженное на квадрат радиуса
priamougolnik = Rectangle(10,5) #Создание экземпляра класса с 2 аргументами
krug = Circle(14) #Создание экземпляра класса с аргументом
print(f"Площадь прямоугольника: {priamougolnik.area()} \nПлощадь круга равна: {krug.area()}") #Вывод 2х площадей
```
### Результат
![Desktop_231117_1730](https://github.com/d1VaN47/Software_Engineering/assets/145551753/521955e9-a9b8-4345-b634-24c84983c718)

## Краткий вывод:
Создание 3х классов, 2 из которых наследуют первый. При вызове класса Rectangle возвращает площадь прямоугольника, а при вызове Circle возвращает площадь круга.

# Самостоятельная работа
## Задание 1
Самостоятельно создайте класс и его объект. Они должны  отличаться, от тех, что указаны в теоретическом материале  (методичке) и лабораторных заданиях. Результатом выполнения  задания будет листинг кода и получившийся вывод консоли

  ```python
class Dostavka:
    def __init__(self, adres, time):
        self.adres = adres
        self.time = time

klient1111 = Dostavka("Библиотечная 45", "18:45")
```
### Результат
![Desktop_231117_1957](https://github.com/d1VaN47/Software_Engineering/assets/145551753/d5b249e6-3b24-445c-b75b-a0ae5b99c60b)

## Краткий вывод:
Данный код создаёт класс Dostavka, которому на вход нужен адрес и время доставки.

## Задание 2
Самостоятельно создайте атрибуты и методы для ранее созданного  класса. Они должны отличаться, от тех, что указаны в  теоретическом материале (методичке) и лабораторных заданиях.  Результатом выполнения задания будет листинг кода и  получившийся вывод консоли
```python
class Dostavka:
    def __init__(self, adres, time):
        self.adres = adres
        self.time = time
    def inf(self):
        print(f"Адрес клиента: {self.adres}, необходимо доставить к {self.time}")
klient1111 = Dostavka("Библиотечная 45", "18:45")
klient1111.inf()
```
### Результат
![Desktop_231117_1950](https://github.com/d1VaN47/Software_Engineering/assets/145551753/2b203f34-0c9b-49f9-8155-865047410a66)

## Краткий вывод:
Данный код создаёт класс Dostavka, которому на вход нужен адрес и время доставки. После вызова метода inf он выведет сообщение об адресе и времени объекта. 

## Задание 3
Самостоятельно реализуйте наследование, продолжая работать с  ранее созданным классом. Оно должно отличаться, от того, что  указано в теоретическом материале (методичке) и лабораторных  заданиях. Результатом выполнения задания будет листинг кода и  получившийся вывод консоли

  ```python
class Dostavka:
    def __init__(self, adres, time):
        self.adres = adres
        self.time = time

    def inf(self):
        print(f"Адрес клиента: {self.adres}, необходимо доставить к {self.time}")

class Voditel(Dostavka):
    def __init__(self, adres, time, Name):
        super().__init__(adres, time)
        self.Name = Name
    def naznachenie(self):
        print(f"Водитель {self.Name} назначен на адрес: {self.adres}, необходимо доставить к {self.time}")
klient1111 = Voditel("Библиотечная 45", "18:45", "Николай")
klient1111.inf()
klient1111.naznachenie()
```
### Результат
![Desktop_231117_2009](https://github.com/d1VaN47/Software_Engineering/assets/145551753/063203e1-c30c-4b6e-a792-cf7ffe1be370)

## Краткий вывод:
В данном коде создаёются 2 класса Dostavka и Voditel, который наследует Dostavka. Класс водители наследует все атрибуты и добавляет ещё 1 свой. Так же 2 метода. Первый выводит данные об адресе и времени, второй выводит имя назначенного водителя, адрес и время к которому необходимо доставить.

## Задание 4
Самостоятельно реализуйте инкапсуляцию, продолжая работать с  ранее созданным классом. Она должна отличаться, от того, что  указана в теоретическом материале (методичке) и лабораторных  заданиях. Результатом выполнения задания будет листинг кода и  получившийся вывод консоли.

  ```python
class Dostavka:
    def __init__(self, adres, time):
        self._adres = adres
        self.__time = time

    def inf(self):
        print(f"Адрес клиента: {self._adres}, необходимо доставить к {self.__time}")


klient1111 = Dostavka("Библиотечная 45", "18:45")
klient1111.inf()
print(klient1111._adres)
```
### Результат
![Desktop_231117_2019](https://github.com/d1VaN47/Software_Engineering/assets/145551753/547f8a2e-dda9-46b2-a7bd-7612302fd9a3)

## Краткий вывод:
В данном коде создаётся класс в котором 2 атрибута - защищённый и приватный. С помощью метода inf мы можем вывести оба, а через print(klient1111._adres) только защищённый, при попытке вывести приватный вадаёт ошибку.

## Задание 5
Самостоятельно реализуйте полиморфизм. Он должен отличаться,  от того, что указан в теоретическом материале (методичке) и  лабораторных заданиях. Результатом выполнения задания будет  листинг кода и получившийся вывод консоли.

  ```python
class Botanica:
    def __init__(self, adres, time):
        self.adres = adres
        self.time = time

    def inf(self):
        print(f"Адрес клиента: {self.adres}, необходимо доставить к {self.time}")
    def cena(self):
        print(f"Стоимость доставки 120 рублей")

class Kompressornii(Botanica):
    def cena(self):
        print(f"Стоимость доставки 350 рублей")

class Aramil(Botanica):
    def cena(self):
        print(f"Стоимость доставки 500 рублей")

klient1111 = Kompressornii("Латвийская 56/3", "12:00")
klient1111.inf()
klient1111.cena()
klient1112 = Aramil("Текстильщиков 11", "13:15")
klient1112.inf()
klient1112.cena()
```
### Результат
![Desktop_231117_2042](https://github.com/d1VaN47/Software_Engineering/assets/145551753/ddd497db-54e5-4a8d-80e7-72b1473a4b98)

## Краткий вывод:
В данном коде мы создаём 3 класса с названиями районов. Kompressornii и Aramil - классы которые наследуют класс Botanica, переопеределяя только метод "cena" в зависимости от стоиомсти доставки в данный район.
