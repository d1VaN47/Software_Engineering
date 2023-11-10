# Тема 6. Базовые коллекции: словари, картежи
Отчет по Теме #6 выполнил:
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
В школе, где вы учились, узнали, что вы крутой программист и  попросили написать программу для учителей, которая будет при вводе  кабинета писать для него ключ доступа и статус, занят кабинет или нет.  При написании программы необходимо использовать словарь (dict),  который на вход получает номер кабинета, а выводит необходимую  информацию. Если кабинета, который вы ввели нет в словаре, то в  консоль в виде значения ключа нужно вывести “None” и виде статуса  вывести “False”.

  ```python
request = int(input("Введите номер кабинета: "))
dictionary = {
    101: {"key":1234, "access": True},
    102: {"key":1337, "access": True},
    103: {"key":8943, "access": True},
    104: {"key":5555, "access": False},
    None: {"key":None, "access": False},
}
response = dictionary.get(request)
if not response:
    response = dictionary.get(None)
key = response.get("key")
access = response.get("access")
print(key, access)
```
### Результат
![Desktop_231110_1552](https://github.com/d1VaN47/Software_Engineering/assets/145551753/fd12f39a-5911-471c-833c-4f7a0b3e673e)

## Краткий вывод:
Для выполнения данного задания мы создаём словарь, в котором хранится информация о кабинетах, их ключах и состоянии. Для получения информации о необходимом кабинете, мы запрашиваем номер у пользователя, а далее создаём новый словарь в который присваиваем информацию о необходимом кабинете с помощью response = dictionary.get(request), а для вывода ссылаемся на необходимые ключи этого словаря и выводим их. 

## Задание 2
Алексей решил создать самый большой словарь в мире. Для этого он  придумал функцию dict_maker (**kwargs), которая принимает  неограниченное количество параметров «ключ: значение» и обновляет созданный им словарь my_dict, состоящий всего из одного элемента  «first» со значением «so easy». Помогите Алексею создать данную  функцию

  ```python
from pprint import pprint
my_dict = {"first": "so easy"}
def dict_maker(**kwargs):
    my_dict.update(**kwargs)
dict_maker(a1=1, a2=20, a3=54, a4=13)
dict_maker(name="Михаил", age=31, weight=70, eyes_color="blue")
pprint(my_dict)
```
### Результат
![Desktop_231110_1603](https://github.com/d1VaN47/Software_Engineering/assets/145551753/2f13fa74-9337-485f-a698-bb598a7ffb18)

## Краткий вывод:
Для добавления новых элементов в словарь создаём функцию, которая принмиает неограниченоое кол-во элементов с помощью (**kwargs) и добавляет их в словарь.

## Задание 3
Для решения некоторых задач бывает необходимо разложить строку на  отдельные символы. Мы знаем что это можно сделать при помощи  split(), у которого более гибкая настройка для разделения для этого, но  если нам нужно посимвольно разделить строку без всяких условий, то  для этого мы можем использовать кортежи (tuple). Для этого напишем  любую строку, которую будем делить и “обвернем” ее в tuple и дальше  мы можем как нам угодно с ней работать, например, сделать ее  списком (тогда получится полный аналог split()) или же работать с ним  дальше, как с кортежем.

  ```python
input_string = "HelloWorld"
result = tuple(input_string)
print(result)
print(list(result))
```
### Результат
![Desktop_231110_1608](https://github.com/d1VaN47/Software_Engineering/assets/145551753/e8343dff-f457-489c-9b66-57a7ec0810eb)

## Краткий вывод:
Для разделения строки посимвольно мы используем tuple(), который превраает строку картеж в котором каждый символ, это отдельный элемент

## Задание 4
Вовочка решил написать крутую функцию, которая будет писать имя,  возраст и место работы, но при этом на вход этой функции будет  поступать кортеж. Помогите Вовочке написать эту программу

  ```python
def personal_info(name, age, company="unnamed"):
    print(f"Имя: {name} Возраст: {age} Компания: {company}")
tom = ("Григорий", 22)
personal_info(*tom)
bob = ("Георгий", 41, "Yandex")
personal_info(*bob)
```
### Результат
![Desktop_231110_1616](https://github.com/d1VaN47/Software_Engineering/assets/145551753/65c26221-90fa-4b5f-913e-ac0472163e24)

## Краткий вывод:
Для выполнения данной задачи необходимо создать функцию, которая входящий картеж разделяет на 3 переменные и выводит их

## Задание 5
Для сопровождения первых лиц государства X нужен кортеж, но никто  не может определиться с порядком машин, поэтому вам нужно  написать функцию, которая будет сортировать кортеж, состоящий из  целых чисел по возрастанию, и возвращает его. Если хотя бы один  элемент не является целым числом, то функция возвращает исходный  кортеж

  ```python
def tuple_sort(tpl):
    for elm in tpl:
        if not isinstance(elm,int):
            return tpl
    return tuple(sorted(tpl))

print(tuple_sort((5, 5, 3, 1, 9)))
print(tuple_sort((5, 5, 2.1, "1", 9)))
```
### Результат
![Desktop_231110_1623](https://github.com/d1VaN47/Software_Engineering/assets/145551753/74816cf6-51da-4453-8c23-0fccff6124e1)

## Краткий вывод:
Для выполнения задния необходимо создать функцию, которая проверяет все ли введённые значения это целые числа спомощью if not isinstance(elm,int), если все элменты - это простые числа, то сортируем их и выводим с помощью sorted(tpl)

# Самостоятельная работа
## Задание 1
При создании сайта у вас возникла потребность обрабатывать  данные пользователя в странной форме, а потом переводить их в  нужные вам форматы. Вы хотите принимать от пользователя  последовательность чисел, разделенных пробелом, а после  переформатировать эти данные в список и кортеж. Реализуйте вашу  задумку. Для получения начальных данных используйте input().  Результатом программы будет выведенный список и кортеж из  начальных данных.

  ```python

```
  ### Результат

## Краткий вывод:


## Задание 2
Николай знает, что кортежи являются неизменяемыми, но он очень  упрямый и всегда хочет доказать, что он прав. Студент решил  создать функцию, которая будет удалять первое появление  определенного элемента из кортежа по значению и возвращать  кортеж без него. Попробуйте повторить шедевр не признающего  авторитеты начинающего программиста. Но учтите, что Николай не  всегда уверен в наличии элемента в кортеже (в этом случае кортеж  вернется функцией в исходном виде).  

Входные данные:  

(1, 2, 3), 1)  

(1, 2, 3, 1, 2, 3, 4, 5, 2, 3, 4, 2, 4, 2), 3)  

(2, 4, 6, 6, 4, 2), 9) 

Ожидаемый результат:  

(2, 3)  

(1, 2, 1, 2, 3, 4, 5, 2, 3, 4, 2, 4, 2)  

(2, 4, 6, 6, 4, 2)

  ```python

```
  ### Результат

## Краткий вывод:


## Задание 3
Ребята поспорили кто из них одним нажатием на numpad наберет  больше повторяющихся цифр, но не понимают, как узнать  победителя. Вам им нужно в этом помочь. Дана строка в виде  случайной последовательности чисел от 0 до 9 (длина строки  минимум 15 символов). Требуется создать словарь, который в  качестве ключей будет принимать данные числа (т. е. ключи будут  типом int), а в качестве значений – количество этих чисел в  имеющейся последовательности. Для построения словаря создайте функцию, принимающую строку из цифр. Функция должна  возвратить словарь из 3-х самых часто встречаемых чисел, также  эти значения нужно вывести в порядке возрастания ключа.

  ```python

```
  ### Результат

## Краткий вывод:


## Задание 4
Ваш хороший друг владеет офисом со входом по электронным  картам, ему нужно чтобы вы написали программу, которая  показывала в каком порядке сотрудники входили и выходили из  офиса. Определение сотрудника происходит по id. Напишите  функцию, которая на вход принимает кортеж и случайный элемент  (id), его можно придумать самостоятельно. Требуется вернуть  новый кортеж, начинающийся с первого появления элемента в нем и  заканчивающийся вторым его появлением включительно.  Если элемента нет вовсе – вернуть пустой кортеж.  Если элемент встречается только один раз, то вернуть кортеж,  который начинается с него и идет до конца исходного.  

Входные данные:  

(1, 2, 3), 8)  

(1, 8, 3, 4, 8, 8, 9, 2), 8)  

(1, 2, 8, 5, 1, 2, 9), 8)  

Ожидаемый результат:  

()  

(8, 3, 4, 8)  

(8, 5, 1, 2, 9)

  ```python

```
  ### Результат

## Краткий вывод:


## Задание 5
Самостоятельно придумайте и решите задачу, в которой будут  обязательно использоваться кортеж или список. Проведите  минимум три теста для проверки работоспособности вашей задачи.

  ```python

```
  ### Результат

## Краткий вывод:


