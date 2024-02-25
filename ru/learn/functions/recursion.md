> [!NOTE]
> Вы можете прочитать эту статью на сайте: https://diveintopython.org/ru/learn/functions/recursion

**Рекурсивное программирование** - это техника в программировании, при которой функция **вызывает себя повторно** до тех пор, пока не достигнет базового или терминального случая. Это мощный инструмент при работе с определенными типами задач, которые могут быть естественно определены рекурсивным способом. В Python мы можем реализовать эту технику через рекурсивные функции.

## Рекурсивные Функции Python

Рекурсивные функции - это функции, которые **вызывают себя** во время выполнения для решения задачи, разбивая её на меньшие подзадачи. Рекурсия в Python включает в себя два основных шага: определение базового случая (случаев) и рекурсивного случая (случаев).

### Пример 1: Вычисление Факториала с Использованием Рекурсии

```python
def factorial(n):
    if n == 0:
        return 1
    else:
        return n * factorial(n-1)

# driver code
num = 5
print("Factorial of", num, "is", factorial(num))
```

В этом примере функция `factorial()` принимает целое число `n` в качестве входных данных и **рекурсивно** вычисляет **факториал** `n`, умножая его на факториал `n-1`. Базовый случай, когда `n` равно `0`, в этом случае функция возвращает `1`.

### Пример 2: Вычисление Ряда Фибоначчи с Использованием Рекурсии

```python
def fibonacci(n):
    if n <= 1:
        return n
    else:
        return (fibonacci(n-1) + fibonacci(n-2))

# driver code
num_terms = 10

if num_terms <= 0:
    print("Invalid input")
else:
    print("Fibonacci series:")
    for i in range(num_terms):
        print(fibonacci(i), end=" ")
```

В этом примере функция `fibonacci()` принимает целое число `n` в качестве входного параметра и рекурсивно вычисляет `n`-ный член **последовательности Фибоначчи**, складывая два предыдущих члена. Базовый случай - когда `n` равно `0` или `1`, в этом случае функция возвращает `n`. Драйвер код печатает первые `num_terms` членов последовательности Фибоначчи, где `num_terms` - это значение, введенное пользователем.

## Советы и Лучшие Практики Для Рекурсивного Программирования на Python

1. **Четко определите базовый случай**: Базовый случай - это условие, при котором функция должна перестать вызывать себя рекурсивно и возвращать значение. Убедитесь, что базовый случай четко определен и что функция в конечном итоге достигает его, чтобы избежать бесконечной рекурсии.

2. **Следите за глубиной рекурсии**: Глубина рекурсии относится к количеству раз, когда функция вызывает себя рекурсивно. В Python есть **лимит глубины рекурсии в 1000**, поэтому убедитесь, что ваши рекурсивные функции находятся в пределах этого лимита или настройте лимит глубины рекурсии, используя модуль sys.

3. **Рассмотрите возможность использования мемоизации**: Мемоизация - это техника, используемая для кэширования результатов дорогостоящих вызовов функций и их повторного использования при повторении одних и тех же входных данных. Это может значительно улучшить производительность рекурсивных функций в Python, избегая повторных вычислений.

4. **Тестируйте и отлаживайте тщательно**: Рекурсивные функции могут быть сложными в отладке из-за их сложной природы. Убедитесь, что вы тестируете вашу функцию с различными входными значениями и уделяете время пониманию ее работы перед тем, как развернуть ее в производстве.

## Пример: Бинарный Поиск

```python
def binary_search(arr, target, low, high):
    # base case
    if low > high:
        return -1
    # recursive case
    mid = (low + high) // 2
    if arr[mid] == target:
        return mid
    elif arr[mid] > target:
        return binary_search(arr, target, low, mid-1)
    else:
        return binary_search(arr, target, mid+1, high)
```

Эта рекурсивная функция выполняет **бинарный поиск** в отсортированном массиве, **вызывая себя** с меньшими подмассивами, пока не найдет цель или не достигнет базового случая, когда нижний индекс больше верхнего индекса.

## Распространённые Ошибки и Ловушки При Работе с Рекурсией в Python

Рекурсивные функции на Python могут быть мощным инструментом для решения сложных задач, но они также могут подвергаться распространённым ошибкам и ловушкам. Вот несколько распространённых ошибок, которых стоит избегать при использовании рекурсии на Python:

1. **Бесконечные циклы**: Создать бесконечные циклы в рекурсивных функциях легко, если у вас нет базового случая, который в конечном итоге прерывает рекурсию. Обязательно определите базовый случай, который остановит рекурсию.

2. **Переполнение стека**: Рекурсия может создать большую нагрузку на память, что может привести к ошибкам переполнения стека. Будьте осторожны при использовании рекурсии с большими наборами данных.

## Улучшение Рекурсивных Функций Python Для Повышения Эффективности и Производительности

Улучшение рекурсии относится к процессу оптимизации рекурсивной функции Python для лучшей эффективности и производительности. Это включает в себя выявление областей, которые могут быть настроены, таких как сокращение сложности по памяти или использование мемоизации для уменьшения числа рекурсивных вызовов.

Ниже приведены два примера того, как улучшить рекурсивные функции Python для большей эффективности:

### Мемоизация

Мемоизация — это процесс хранения ранее вычисленных результатов для избежания повторного расчета. Это может значительно сократить время выполнения рекурсивной функции.

```python
def fibonacci(n, memo={}):
    if n <= 1:
        return n
    elif n in memo:
        return memo[n]
    else:
        memo[n] = fibonacci(n-1, memo) + fibonacci(n-2, memo)
        return memo[n]
```

В вышеупомянутом коде, словарь `memo` используется для хранения ранее вычисленных чисел Фибоначчи. Когда функция вызывается с ранее рассчитанным значением `n`, возвращается значение `memo` вместо того, чтобы функция совершала еще один рекурсивный вызов.

### Оптимизация Хвостовой Рекурсии

Оптимизация хвостовой рекурсии - это способ оптимизации рекурсивных функций таким образом, чтобы они использовали меньше места в стеке вызовов.

```python
def sum_n(n, acc=0):
    if n == 0:
        return acc
    else:
        return sum_n(n-1, acc+n)

# Example usage
print(sum_n(5)) # Outputs: 15
```

В приведенном выше коде, `sum_n()` является **рекурсивной функцией**, которая вычисляет сумму всех чисел от `1` до `n`. Аргумент acc является **накопителем**, который хранит промежуточные результаты вычисления.

На каждом рекурсивном вызове функция добавляет текущее значение `n` к накопителю и передает результат следующему рекурсивному вызову, не сохраняя в памяти кадр стека предыдущего вызова. Таким образом, функция использует постоянное количество памяти на стеке вызовов и избегает риска переполнения стека при больших значениях `n`.

> Обратите внимание, что оптимизация хвостовой рекурсии может быть применена только к рекурсивным функциям, которые имеют хвостовой вызов, т.е., рекурсивный вызов, который происходит в конце выполнения функции.