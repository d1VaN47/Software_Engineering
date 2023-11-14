# Тема 7. Работа с файлами (ввод, вывод)
Отчет по Теме #7 выполнил:
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
Составьте текстовый файл и положите его в одну директорию с  программой на Python. Текстовый файл должен состоять минимум из  двух строк

  ```python
hi
i'm Ivan
```
### Результат
![Desktop_231114_1454](https://github.com/d1VaN47/Software_Engineering/assets/145551753/b9551103-f9af-4dea-8f67-3caaf4697205)

## Краткий вывод:
Мы создали файл в директории с программой на Python

## Задание 2
Напишите программу, которая выведет только первую строку из  вашего файла, при этом используйте конструкцию open()/close()

  ```python
f = open("test.txt", "r")
print(f.readline())
f.close()
```
### Результат
![Desktop_231114_1456](https://github.com/d1VaN47/Software_Engineering/assets/145551753/056738fe-aad3-4660-bba6-c1153a54bc87)

## Краткий вывод:
Для открытия файла мы используем open(), далее мы выводим одну строку с помощью .readline() и закрываем файл с помощью .close()

## Задание 3
Напишите программу, которая выведет все строки из вашего файла в  массиве, при этом используйте конструкцию open()/close().

  ```python
f = open("test.txt", "r")
print(f.readlines())
f.close()
```
### Результат
![Desktop_231114_1458](https://github.com/d1VaN47/Software_Engineering/assets/145551753/7599f89a-fdb0-4efd-9f9a-4748b4e6b777)

## Краткий вывод:
Для вывода всех строк файла, используем .readlines()

## Задание 4
Напишите программу, которая выведет все строки из вашего файла в  массиве, при этом используйте конструкцию with open()

  ```python
with open("test.txt") as f:
    print(f.readlines())
```
### Результат
![Desktop_231114_1500](https://github.com/d1VaN47/Software_Engineering/assets/145551753/1ca19181-39ac-40f9-a347-3b1e96052bdd)

## Краткий вывод:
Для автоматического закрытия файла используем конструкцию with open

## Задание 5
Напишите программу, которая выведет каждую строку из вашего  файла отдельно, при этом используйте конструкцию with open().

  ```python
with open("test.txt") as f:
    for line in f:
        print(line)
```
### Результат
![Desktop_231114_1502](https://github.com/d1VaN47/Software_Engineering/assets/145551753/4f4fc8ce-8622-494d-8a73-2f735550c4e3)

## Краткий вывод:
Для вывода кадой строки отдельно используем цикл for, в котором вызываем каждую строку отдельно и выводим её

## Задание 6
Напишите программу, которая будет добавлять новую строку в ваш  файл, а потом выведет полученный файл в консоль. Вывод можно  осуществлять любым способом. Обязательно проверьте сам файл,  чтобы изменения в нем тоже отображались.

  ```python
with open("test.txt", "a+") as f:
    f.write("\nIm additional line")

with open("test.txt", "r") as f:
    result =f.readlines()
    print(result)
```
### Результат
![Desktop_231114_1505](https://github.com/d1VaN47/Software_Engineering/assets/145551753/1cc3c1d9-2b32-4aa9-add2-a35004c6e673)

## Краткий вывод:
Для добавления новой строки используем .write(), которая добавляет текст в конец файла

## Задание 7
Напишите программу, которая перепишет всю информацию, которая  была у вас в файле до этого, например напишет любые данные из  произвольно вами составленного списка. Также не забудьте проверить  что измененная вами информация сохранилась в файле.

  ```python
lines = ["one", "two", "three"]
with open("test.txt", "w") as f:
    for line in lines:
        f.write("\nCycle run " + line)
    print("Done!")
```
### Результат
![Desktop_231114_1511](https://github.com/d1VaN47/Software_Engineering/assets/145551753/ee602739-ccbc-4294-b549-e21b0a4064a6)

![Desktop_231114_1508](https://github.com/d1VaN47/Software_Engineering/assets/145551753/8d001f96-745a-45e6-9f9f-2526dd3f02a8)

![Desktop_231114_1511_1](https://github.com/d1VaN47/Software_Engineering/assets/145551753/3ec98df6-ab16-461f-b706-e43ffa5e9089)

## Краткий вывод:
Для выполнения данной задачи мы открываем файл, в цикле for вызываем каждую строку и изменяем её значение

## Задание 8
Выберите любую папку на своем компьютере, имеющую вложенные  директории. Выведите на печать в терминал ее содержимое, как и всех  подкаталогов при помощи функции print_docs(directory).

  ```python
import os
def print_docs(directory):
    all_files = os.walk(directory)
    for catalog in all_files:
        print(f"Папка {catalog[0]} содержит: ")
        print(f"Директории: {', '.join([folder for folder in catalog[1]])}")
        print(f"Файлы: {', '.join([file for file in catalog[2]])}")
        print('-' * 40)
print_docs("C:Users\ivver\Pictures")
```
### Результат
![Desktop_231114_1528](https://github.com/d1VaN47/Software_Engineering/assets/145551753/b5d564a0-4e0d-4258-95b8-cdfb8b4800ad)

## Краткий вывод:
Для просмотра файлов из репозитория импортируем модуль os

## Задание 9
Документ «input.txt» содержит следующий текст:  

Приветствие  

Спасибо  

Извините  

Пожалуйста  

До свидания  

Ты готов?  

Как дела?  

С днем рождения!  

Удача!  

Я тебя люблю.  

Требуется реализовать функцию, которая выводит слово, имеющее  максимальную длину (или список слов, если таковых несколько).  Проверьте работоспособность программы на своем наборе данных

  ```python
def longest_words(file):
    with open(file, encoding='utf-8') as f:
        words = f.read().split()
        max_lenght = len(max(words, key=len))
        for word in words:
            if len(word) == max_lenght:
                sought_words = word
        if len(sought_words) == 1:
            return sought_words[0]
        return sought_words
print(longest_words('test.txt'))
```
### Результат
![Desktop_231114_1615](https://github.com/d1VaN47/Software_Engineering/assets/145551753/4308901a-7bda-4480-b8ff-715a961eda21)

## Краткий вывод:
Для выполнения задачи мы находим самую большую длину строки, а далее ищем какая именно строка равна этой длине и присваиваем её значение в переменную которую потом выводим

## Задание 10
Требуется создать csv-файл «rows_300.csv» со следующими  столбцами:  

• № - номер по порядку (от 1 до 300);

• Секунда – текущая секунда на вашем ПК;  

• Микросекунда – текущая миллисекунда на часах.  

Для наглядности на каждой итерации цикла искусственно  приостанавливайте скрипт на 0,01 секунды.

  ```python
import csv
import datetime
import time

with open('rows_300.csv', 'w', encoding='utf-8', newline='') as f:
    writer = csv.writer(f)
    writer.writerow(['№', 'Секунда', 'Микросекунда'])
    for line in range(1,301):
        writer.writerow([line, datetime.datetime.now().second, datetime.datetime.now().microsecond])
        time.sleep(0.01)
```
### Результат
![Desktop_231114_1625](https://github.com/d1VaN47/Software_Engineering/assets/145551753/fa8fd485-0c71-43f8-ac1b-a4ef0d9d227f)

![Desktop_231114_1625_1](https://github.com/d1VaN47/Software_Engineering/assets/145551753/7ebd002e-361b-43a7-978b-8fc75c47449a)

## Краткий вывод:
Для выполнения данной задачи создаём файл rows_300.csv, в котором создаём строку с заголовками, а далее запускаем цикл for который перебирает с задержкой в 0.01 создаёт строку с данными о секундах и микросекундах

# Самостоятельная работа
## Задание 1
Найдите в интернете любую статью (объем статьи не менее 200  слов), скопируйте ее содержимое в файл и напишите программу,  которая считает количество слов в текстовом файле и определит  самое часто встречающееся слово. Результатом выполнения задачи  будет: скриншот файла со статьей, листинг кода, и вывод в консоль,  в котором будет указана вся необходимая информация

  ```python
with open('test.txt', 'r', encoding='utf-8') as f:
    razmer = f.read().split()
    print(f"Количество слов = {len(razmer)}")
    popular = [0,""]
    for i in razmer:
        x = 0
        for z in razmer:
            if i == z:
                x += 1
        if x > popular[0]:
            popular[0] = x
            popular[1] = i
    print(f"Самое популярное слово: '{popular[1]}' - оно встречается {popular[0]} раз(а)")
```
### Результат
![Desktop_231114_1814](https://github.com/d1VaN47/Software_Engineering/assets/145551753/38ab1048-246f-46af-9049-eb88a1b614b9)

![Desktop_231114_1834](https://github.com/d1VaN47/Software_Engineering/assets/145551753/8e2bc5ca-abce-4965-873b-18c4a8205be3)

## Краткий вывод:
Для выполнения данной задачи нам необходимо импортировать текстовый файл с статьёй. Далее мы создаём массив в который сохраняем каждой слово как отдельный элемент.

Чтобы узнать кол-во слов мы просто узнаём количество элементов в массиве.

Чтобы найти самый повторяющийся мы просто перебираем все элементы и сравниваем между собой.

## Задание 2
У вас появилась потребность в ведении книги расходов, посмотрев  все существующие варианты вы пришли к выводу что вас ничего не  устраивает и нужно все делать самому. Напишите программу для  учета расходов. Программа должна позволять вводить информацию  о расходах, сохранять ее в файл и выводить существующие данные в  консоль. Ввод информации происходит через консоль. Результатом  выполнения задачи будет: скриншот файла с учетом расходов,  листинг кода, и вывод в консоль, с демонстрацией  работоспособности программы

  ```python

```
### Результат

## Краткий вывод:


## Задание 3
Имеется файл input.txt с текстом на латинице. Напишите программу,  которая выводит следующую статистику по тексту: количество букв  латинского алфавита; число слов; число строк.  

• Текст в файле:  

Beautiful is better than ugly.  

Explicit is better than implicit.  

Simple is better than complex.  

Complex is better than complicated.  

• Ожидаемый результат:  

Input file contains:  

108 letters  

20 words  

4 lines

  ```python

```
### Результат

## Краткий вывод:


## Задание 4
Напишите программу, которая получает на вход предложение,  выводит его в терминал, заменяя все запрещенные слова  звездочками * (количество звездочек равно количеству букв в  слове). Запрещенные слова, разделенные символом пробела,  хранятся в текстовом файле input.txt. Все слова в этом файле  записаны в нижнем регистре. Программа должна заменить  запрещенные слова, где бы они ни встречались, даже в середине  другого слова. Замена производится независимо от регистра: если файл input.txt содержит запрещенное слово exam, то слова exam,  Exam, ExaM, EXAM и exAm должны быть заменены на ****.  

• Запрещенные слова:  

hello email python the exam wor is  

• Предложение для проверки:  

Hello, world! Python IS the programming language of thE future. My EMAIL is....  

PYTHON is awesome!!!!  

• Ожидаемый результат:  

*****, ***ld! ****** ** *** programming language of *** future. My ***** **....  

****** ** awesome!!!!

  ```python

```
### Результат

## Краткий вывод:


## Задание 5
Самостоятельно придумайте и решите задачу, которая будет  взаимодействовать с текстовым файлом

  ```python

```
### Результат

## Краткий вывод:

