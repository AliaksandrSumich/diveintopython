[!NOTE]
>  Вы можете прочитать эту статью на сайте: https://diveintopython.org/ru/learn/variables/number

Python поддерживает несколько числовых типов данных, которые используются для различных математических операций в программировании. К этим типам данных относятся целые числа, числа с плавающей точкой и комплексные числа. Понимание этих типов данных и их характеристик является важным для любого программиста, который хочет работать с числовыми данными в Python.

## Типы Чисел в Python

В Python существует несколько типов чисел, которые могут использоваться для различных целей. Самые распространенные типы чисел в Python:

- **Целое число** (int): Это целое число без десятичной точки. Например, `1`, `2`, `3` и т. д. являются целыми числами.
- **Число с плавающей точкой** (float): Это десятичное число. Например, `1.2`, `3.14159` и т. д. являются числами с плавающей точкой.
- **Комплексное число** (complex): Это число с действительной и мнимой частями. Например, `1 + 2j`, `3.14 - 4j` и т. д. являются комплексными числами.

Вот несколько примеров того, как определить эти типы чисел в Python:

```python
# Integer
x = 5
print(type(x))  # Output: <class 'int'>

# Float
y = 3.14
print(type(y))  # Output: <class 'float'>

# Complex
z = 2 + 3j
print(type(z))  # Output: <class 'complex'>
```

## Функция `isinstance()`

Чтобы проверить, является ли переменная числом в Python, вы можете использовать функцию `isinstance()` для проверки, принадлежит ли переменная к типу данных int, float или complex. Вот пример:

```python
x = 10
y = 3.14
z = 2 + 3j

print(isinstance(x, (int, float, complex)))  # Output: True
print(isinstance(y, (int, float, complex)))  # Output: True
print(isinstance(z, (int, float, complex)))  # Output: True
print(isinstance('hello', (int, float, complex)))  # Output: False
```

## Округление Числа в Python

Вы можете округлить число, используя встроенную функцию `round()`. Функция `round()` принимает два аргумента: число, которое нужно округлить, и количество десятичных знаков, до которых нужно округлить.

Вот пример:

```python
x = 3.14159
rounded_x = round(x, 2)
print(rounded_x) # Output: 3.14
```

Обратите внимание, что если число, которое нужно округлить, заканчивается на 5, функция `round()` будет округлять до ближайшего четного числа. Это известно как "банковское округление". Например:

```python
x = 2.5
rounded_x = round(x)
print(rounded_x) # Output: 2
```

## Форматирование Чисел

В Python есть несколько способов форматирования чисел. Вот несколько примеров:

### Использование Встроенной Функции `format()`

```python
x = 3.14159
print("{:.2f}".format(x))  # Output: 3.14
```

Строка `"{:.2f}"` внутри функции `format()` указывает Python на форматирование числа как числа с плавающей точкой с двумя десятичными знаками.

### Использование f-строк (Python 3.6 и выше)

```python
x = 3.14159
print(f"{x:.2f}")  # Output: 3.14
```

Буква `f` перед строкой указывает, что это f-строка, а `"{x:.2f}"` внутри строки сообщает Python оформатировать значение `x` как число с плавающей точкой с двумя десятичными знаками.

### Использование Оператора `%`

```python
x = 3.14159
print("%.2f" % x)  # Output: 3.14
```

Строка `%.2f` внутри оператора `%` указывает Python на форматирование числа как числа с плавающей точкой с двумя десятичными знаками.

## Проверка, Является ли Строка Числом

Вы можете проверить, является ли строка числом в Python, используя различные методы. Вот несколько примеров:

### Использование Метода `isnumeric()`

```python
my_string = "123"
if my_string.isnumeric():
    print("String is a number")
else:
    print("String is not a number") # Output: String is a number

### Using `isdigit()` method

```python
my_string = "456"
if my_string.isdigit():
    print("String is a number")
else:
    print("String is not a number") # Output: String is a number
 ```

 ### Использование Блока try-except для Преобразования Строки в Число с Плавающей Точкой


```python
my_string = "789.12"
try:
    float(my_string)
    print("String is a number")
except ValueError:
    print("String is not a number") # Output: String is a number
```

Строка `%.2f` внутри оператора `%` указывает Python на форматирование числа как числа с плавающей точкой с двумя десятичными знаками.

## Проверка, Является ли Строка Числом

Вы можете проверить, является ли строка числом в Python, используя различные методы. Вот несколько примеров:

### Использование Метода `isnumeric()`

```python
num = 5.0  # the number you want to check

if num % 1 == 0:
    print("The number is whole.")
else:
    print("The number is not whole.") # Output: "The number is whole.
    "
```

## Генерация случайного числа

Чтобы получить случайное число в Python, вы можете использовать модуль random. Вот пример того, как сгенерировать случайное целое число между 0 и 10:

```python
import random

random_number = random.randint(0, 10)
print(random_number)
```

Это выведет случайное целое число от 0 до 10 (включительно) каждый раз при запуске скрипта. Если вы хотите сгенерировать случайное число с плавающей точкой, вы можете использовать функцию `random.uniform()` вместо этого:

```python
import random

random_number = random.uniform(0, 1)
print(random_number)
```

## Возведение числа в квадрат в Python

Давайте посмотрим, как возвести число в квадрат в Python.
Первый метод - использование оператора степени `**`. Вот пример:

```python
x = 5
squared = x ** 2
print(squared) # Output: 25
```

В качестве альтернативы, вы также можете использовать функцию `pow()` для вычисления квадрата числа. Вот пример:

```python
x = 5
squared = pow(x, 2)
print(squared)
```

## Отрицание Числа

Вы можете изменить знак числа, используя оператор `-` (минус).

Вот пример:

```python
number = 10
negated_number = -number
print(negated_number) # Output: -10
```

## Простое число

Простое число - это положительное целое число, большее 1, которое не имеет положительных целых делителей, кроме 1 и самого себя. В Python вы можете проверить, является ли число простым, проверив, делится ли оно на любое число, кроме 1 и самого себя.

Вот пример функции, которая проверяет, является ли число простым или нет:

```python
def is_prime(n):
    if n <= 1:
        return False
    for i in range(2, int(n**0.5) + 1):
        if n % i == 0:
            return False
    return True
```

Эта функция принимает положительное целое число `n` на входе и возвращает `True`, если `n` является простым, и `False` в противном случае.

Функция сначала проверяет, является ли `n` меньше или равным 1, что по определению не является простым числом. Если `n` меньше или равен 1, функция возвращает `False`.

Если `n` больше 1, функция проверяет, делится ли оно на любое число от 2 до квадратного корня из `n`. Если `n` делится на любое число в этом диапазоне, оно не является простым, и функция возвращает `False`. В противном случае `n` простое, и функция возвращает `True`.

Вот пример того, как использовать функцию `is_prime`:

```python
print(is_prime(7)) # True
print(is_prime(15)) # False
print(is_prime(23)) # True
print(is_prime(1)) # False
```

Вывод:

```python
True
False
True
False
```
В этом примере мы вызвали функцию `is_prime` с различными входными значениями и вывели результат.

## Число Эйлера в Python

Число Эйлера, также известное как математическая константа `e`, является математической константой, которая приблизительно равна 2,71828. В Python вы можете вычислить число Эйлера с помощью модуля `math`.

Вот пример того, как вычислить число Эйлера:

```python
import math

e = math.e

print(e) # Output: 2.718281828459045
```

## Извлечение Числа из Строки

Чтобы извлечь число из строки в Python, вы можете использовать регулярные выражения с модулем `re`. Вот пример:

```python
import re

string = "The price is $12.34"

number = re.findall(r'\d+\.\d+', string)[0]

print(number) # Output: 12.34
```

В этом примере мы сначала импортировали модуль `re`, который обеспечивает поддержку регулярных выражений. Затем мы определили переменную `string`, которая содержит предложение с числом.

Для извлечения числа из строки мы использовали функцию `re.findall` с шаблоном регулярного выражения `\d+\.\d+`. Этот шаблон соответствует одной или более цифрам `\d+`, за которыми следует точка `\.` и одна или более цифр `\d+`. Полученное совпадение представляет собой строку, которая представляет число в предложении.

Поскольку `re.findall` возвращает список совпадений, мы получаем доступ к первому элементу `[0]` списка, чтобы получить число в виде строки.

Если вам нужно преобразовать извлеченное число из строки в числовое значение, вы можете использовать функцию float или int:

```python
number = float(number)
print(number) # Output: 12.34
```

## Цифры Числа

Чтобы найти цифры числа в Python, вы можете преобразовать число в строку, а затем перебирать строку, чтобы извлечь каждую цифру. Вот пример:

```python
num = 12345

# Convert number to string
num_str = str(num)

# Iterate over string and print each digit
for digit in num_str:
    print(digit)
```

