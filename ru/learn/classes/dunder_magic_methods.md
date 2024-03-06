> [!NOTE]
> Вы можете прочитать эту статью на сайте: https://diveintopython.org/ru/learn/classes/dunder-magic-methods

**Dunder** (двойное подчёркивание) или **магические** методы — это особые методы в Python, которые позволяют настраивать классы и объекты. Эти методы называются **магическими**, потому что они могут изменять поведение кода неожиданными способами. Понимание и применение этих методов может значительно повысить функциональность и гибкость ваших программ на Python.

## Создание Объектов и Выражений

В Python объекты являются экземплярами классов, которые определяют атрибуты и методы объекта. Процесс создания объекта в Python включает в себя определение класса, который указывает структуру и поведение объекта, а затем создание экземпляров этого класса.

### Определение Классов в Python

Для определения класса в Python используется ключевое слово `class`, за которым следует название класса. Например, следующий код определяет простой класс под названием `Person`:

```python
class Person:
    def __init__(self, name, age):
        self.name = name
        self.age = age

    def say_hello(self):
        print(f"Hello, my name is {self.name} and I am {self.age} years old.")
```

Метод `__init__` является специальным методом, который вызывается при создании экземпляра класса. Он инициализирует атрибуты объекта.

### Python `__init__` Магический Метод

Метод `__init__` является специальным магическим методом, который вызывается при создании экземпляра класса. Он инициализирует атрибуты объекта. В приведенном выше примере метод `__init__` принимает два параметра, `name` и `age`, которые используются для инициализации атрибутов `name` и `age` объекта.

### Создание Экземпляров Классов в Python

Чтобы создать экземпляр класса, вы вызываете класс, как если бы это была функция, передавая любые аргументы, которые требует метод `__init__`. Например, следующий код создает два экземпляра класса `Person`:

```python
# Defining a car class
class Car:
    def __init__(self, make, model, year):
        self.make = make
        self.model = model
        self.year = year
    
    def describe_car(self):
        print(f"The car is a {self.year} {self.make} {self.model}.")
    
    
# Creating an instance of Car class
car1 = Car("Honda", "Accord", 2021)

# Calling the describe_car method
car1.describe_car()

# Output: The car is a 2021 Honda Accord.
```

```python
# Defining a book class
class Book:
    def __init__(self, title, author, pages):
        self.title = title
        self.author = author
        self.pages = pages
    
    def describe_book(self):
        print(f"The book '{self.title}' is written by {self.author} and has {self.pages} pages.")
        

# Creating an instance of Book class
book1 = Book("The Alchemist", "Paulo Coelho", 208)

# Calling the describe_book method
book1.describe_book()

# Output: The book 'The Alchemist' is written by Paulo Coelho and has 208 pages.
```

## Создание Объектов Итераторов

Итератор - это объект, который позволяет последовательно выполнять итерацию (перебор) по коллекции элементов, по одному элементу за раз. В Python вы можете создавать объекты итераторов с использованием классов или функций.

### Класс Генератора Python

Вы можете создать итератор с использованием класса генератора в Python. Класс генератора - это тип объекта, который используется для создания итерируемых объектов с использованием оператора `yield`.

```python
class MyGenerator:
    def __init__(self):
        self.num = 0

    def __iter__(self):
        return self
    
    def __next__(self):
        if self.num <= 5:
            value = self.num
            self.num += 1
            return value
        else:
            raise StopIteration
def my_generator():
    num = 0
    while num <= 5:
        yield num
        num += 1

# Using the generator class
gen = MyGenerator()
for x in gen:
    print(x)

# Using the function generator
gen = my_generator()
for x in gen:
    print(x)
```

В этом примере, `MyGenerator` это генератор класс, который наследует от встроенного класса `object`. Он определяет метод `__init__()`, который инициализирует атрибут `num` значением 0. Также он определяет метод `__iter__()`, который возвращает объект-итератор (`self` в данном случае) и магический метод `__next__()`, который генерирует следующее значение в последовательности.

Вы также можете создать итератор, используя генератор функций Python. Функциональный генератор - это функция, содержащая оператор `yield`.

В этом примере функция `my_generator` является генератором функций, который использует оператор `yield` для генерации следующего значения в последовательности.

В обоих примерах выше вы можете создать объект итератора следующим образом:

Оба примера кода будут выводить значения `0`, `1`, `2`, `3`, `4` и `5` при итерации.

## Обработка Ссылок на Атрибуты

Ссылки на атрибуты используются для доступа к атрибутам объекта в Python. Доступ к ним можно получить, используя синтаксис точечной нотации, а также динамически, используя функцию `getattr()`.

Функция `getattr()` принимает два аргумента - объект, чей атрибут нужно получить, и имя атрибута в виде строки. Если атрибут не найден, генерируется исключение `AttributeError`.

```python

class Dog:
    def __init__(self, name, breed):
        self.name = name
        self.breed = breed

my_dog = Dog("Max", "German Shepherd")
print(my_dog.name) ### Output

my_cat = {"name": "Fluffy", "breed": "Persian"}
cat_name = getattr(my_cat, "name")
print(cat_name) ### Output
```

В первом случае мы создаем класс `Dog` и получаем доступ к атрибуту `name`, используя синтаксис с точечной нотацией.

Во втором случае мы создаем объект словаря `my_cat` и динамически получаем доступ к атрибуту `name`, используя функцию `getattr()`. Мы сохраняем значение атрибута в `cat_name` и выводим его на печать.

## Представление Объектов в Виде Строк с Помощью Магического Метода

В Python мы можем представлять объекты в виде строк, используя магический метод `__repr__()`. Этот метод вызывается, когда мы используем функцию `repr()` или когда мы выводим объект на печать с помощью функции `print()`.

```python
class Point:
    def __init__(self, x, y):
        self.x = x
        self.y = y
        
    def __repr__(self):
        return f"Point({self.x}, {self.y})"
        
p = Point(2, 3)
print(p)  ### Output
```

В приведенном выше коде мы определили класс `Point` с атрибутами `x` и `y`. Также мы определили метод `__repr__()` для представления, который возвращает строковое представление объекта `Point`. Когда мы печатаем объект `p`, он вызывает магический метод `__repr__()` для получения его строкового представления.

```python
class Car:
    def __init__(self, make, model, year):
        self.make = make
        self.model = model
        self.year = year
        
    def __repr__(self):
        return f"Car(make={self.make}, model={self.model}, year={self.year})"
        
c = Car("Toyota", "Camry", 2021)
print(c)  ### Output
```

В этом примере мы определили класс `Car` с атрибутами `make`, `model` и `year`. Также мы определили метод `__repr__()` который возвращает строковое представление объекта `Car`. Когда мы печатаем объект `c`, вызывается метод `__repr__()` для получения его строкового представления.

## Очистка Объектов с Помощью Dunder Метода

В Python объекты автоматически удаляются сборщиком мусора, когда они больше не нужны. Однако иногда может потребоваться определить дополнительные действия по очистке для объекта. Это можно сделать с помощью метода `__del__`, который вызывается, когда объект собирается быть уничтоженным.
 
Этот dunder метод полезен для освобождения ресурсов, таких как файлы, сетевые соединения или другие системные объекты, которые не управляются автоматически Python.

```python
class MyClass:
    def __init__(self):
        self.file = open('example.txt', 'r')

    def __del__(self):
        self.file.close()
```

В этом примере конструктор `MyClass` создает объект файла и сохраняет его в переменной экземпляра `file`. Когда объект уничтожается, вызывается метод `__del__`, который закрывает файл.

## Выполнение Сравнений с Дандер Методами

Python предоставляет несколько способов сравнения значений, переменных или выражений. Некоторые часто используемые операторы для выполнения сравнений включают `==`, `!=`, `>`, `<`, `>=`, `<=`, `in` и `is`.

### Сравнение Строк в Python

Метод `__lt__()` используется для реализации оператора сравнения меньше в Python. Он возвращает `True`, если первая строка меньше второй, и `False` в противном случае.

```python
string1 = "apple"
string2 = "banana"
if string1.__lt__(string2):
    print("string1 is less than string2")
else:
    print("string1 is greater than or equal to string2")

# Output:
#string1 is less than string2
```

```python
fruits = ["apple", "banana", "orange", "kiwi"]
sorted_fruits = sorted(fruits, key=lambda x: x.__lt__("c"))
print(sorted_fruits)
# Output:

# ['orange', 'kiwi', 'apple', 'banana']
```

В приведенном выше примере мы сортировали список фруктов в порядке возрастания на основе того, меньше или больше первый символ каждой строки, чем `c`. `lambda x: x.__lt__(`c`)` возвращает `True`, если первый символ `x` меньше, чем `c`, и `False` в противном случае.