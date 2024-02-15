[!NOTE]
>  Вы можете прочитать эту статью на сайте: https://diveintopython.org/ru/learn/variables/list

Список в Python - это коллекция значений или элементов, которая упорядочена, изменяема и позволяет дубликаты. Списки являются одной из наиболее часто используемых структур данных в Python.

## Создание Списка

Вот пример того, как создать список в Python:

```python
my_list = [1, 2, 3, 4, 5]
```

Как вы можете видеть, создание списка - достаточно простой процесс. Чтобы создать пустой список, вы можете просто использовать следующий синтаксис:

```python
my_list = []
```

Давайте рассмотрим некоторые основные операции, которые можно выполнить со списками в Python.

## Индексы Списка и Доступ к Элементам

Индексы списка - это числовые позиции элементов внутри списка. Индекс первого элемента в списке всегда равен `0`, индекс второго элемента - `1`, и так далее. Вы можете получить доступ к элементу по определенному индексу, используя квадратные скобки и указав номер индекса.

Вот пример использования индексации:

```python
my_list = ['apple', 'banana', 'orange']
print(my_list[0])  # output: 'apple'
print(my_list[1])  # output: 'banana'
print(my_list[2])  # output: 'orange'
```

Если индекс списка находится вне диапазона, Python выдаст ошибку.

## Изменение или Замена Элемента Списка

```python
my_list = [1, 2, 3, 4, 5]
my_list[0] = 0
print(my_list) # Output: [0, 2, 3, 4, 5]
```

## Добавление Элементов в Список в Python

Существует несколько методов, которые могут помочь вам добавить элемент в список.

### Метод `insert()`

Вот пример, который показывает, как добавить элемент в список с помощью метода `insert()`:

```python
my_list = [1, 2, 3, 4]
my_list.insert(2, "hello")
print(my_list)  # [1, 2, 'hello', 3, 4]
```

### Метод `append()`

Чтобы добавить элемент в конец списка Python, вы можете использовать метод `append()`. Вот пример:

```python
my_list = [1, 2, 3, 4]
my_list.append(5)
print(my_list)  # [1, 2, 3, 4, 5]
```

Метод `insert()` может быть использован для добавления элемента в список по указанному индексу. Синтаксис использования метода `insert()` следующий:

```python
list.insert(index, element)
```

### Метод `extend()`

Метод `extend()` в Python используется для добавления элементов из итерируемого объекта (такого как список, кортеж, множество или строка) в конец существующего списка.

Вот пример:

```python
# Create a list
my_list = [1, 2, 3]

# Append elements from another list to my_list using extend()
other_list = [4, 5, 6]
my_list.extend(other_list)

print(my_list)
# Output: [1, 2, 3, 4, 5, 6]
```

Обратите внимание, что метод `extend()` изменяет исходный список на месте и возвращает `None`. Он не создает новый список.

## Удаление Элемента из Списка

Чтобы удалить элемент из списка в Python, вы можете использовать метод `remove()` объекта списка. Вот пример:

```python
my_list = [1, 2, 3, 4, 5]
my_list.remove(3)
print(my_list) # Output: [1, 2, 4, 5]
```

Также существует оператор `del`, который можно использовать для удаления элемента из списка. Вот пример удаления элемента:

```python
my_list = [1, 2, 3, 4, 5]
del my_list[2]
print(my_list)
```

В этом примере у нас есть список `my_list` с пятью элементами. Мы хотим удалить элемент с индексом `2`, который имеет значение `3`. Мы используем оператор `del` и указываем индекс элемента, который мы хотим удалить. После удаления элемента мы выводим обновленный список.

Вывод этого кода будет:

```python
[1, 2, 4, 5]
```

Итак, если вы хотите удалить первый элемент из списка в Python, вы можете использовать оператор `del`, который мы рассмотрели ранее, или метод `pop()`. Вот примеры использования метода `pop()`:

```python
my_list = [1, 2, 3, 4, 5]
my_list.pop(0)
print(my_list) # Output: [2, 3, 4, 5]
```

Давайте также рассмотрим на примере, как удалить `None` из списка в Python, используя генератор списка:

```python
original_list = [1, None, "hello", None, 5.7, None, "world"]
new_list = [item for item in original_list if item is not None]
print(new_list) # Output: [1, 'hello', 5.7, 'world']
```

## Как Отсортировать Список в Python

Вы можете отсортировать список в Python с помощью метода `sort()`, который сортирует элементы списка по возрастанию по умолчанию. Вот пример:

```python
my_list = [3, 1, 4, 1, 5, 9, 2, 6, 5, 3, 5]

my_list.sort()

print(my_list) # Output: [1, 1, 2, 3, 3, 4, 5, 5, 5, 6, 9]
```

Если вы хотите отсортировать список в порядке убывания, вы можете передать аргумент `reverse=True` методу `sort()`:

```python
my_list = [3, 1, 4, 1, 5, 9, 2, 6, 5, 3, 5]

my_list.sort(reverse=True)

print(my_list) # Output: [9, 6, 5, 5, 5, 4, 3, 3, 2, 1, 1]
```

Вы также можете использовать встроенную функцию `sorted()` для сортировки списка, которая возвращает новый отсортированный список и оставляет исходный список неизменным:

```python
my_list = [3, 1, 4, 1, 5, 9, 2, 6, 5, 3, 5]

sorted_list = sorted(my_list)

print(sorted_list) # Output: [1, 1, 2, 3, 3, 4, 5, 5, 5, 6, 9]
```

## Копирование Списка

Для копирования списка в Python вы можете использовать оператор среза или метод `copy()`. Вот пример использования обоих методов:

```python
# Using the slice operator
original_list = [1, 2, 3, 4, 5]
new_list = original_list[:]
print(new_list)  # Output: [1, 2, 3, 4, 5]

# Using the copy() method
original_list = [1, 2, 3, 4, 5]
new_list = original_list.copy()
print(new_list)  # Output: [1, 2, 3, 4, 5]
```

Оба метода создают новый объект списка, который содержит те же элементы, что и исходный список. Однако важно отметить, что если исходный список содержит изменяемые объекты (например, другие списки или словари), копия будет только поверхностной, что означает, что новый список будет содержать ссылки на те же изменяемые объекты, что и исходный список, а не новые копии этих объектов. В таких случаях может потребоваться использовать глубокое копирование, чтобы убедиться, что все вложенные объекты также скопированы.

## Очистка Списка

В Python метод `list.clear()` - это встроенный метод, который удаляет все элементы из списка.

Вот пример того, как очистить список:

```python
my_list = [1, 2, 3, 4]
my_list.clear()
print(my_list)  # Output: []
```

## Как удалить список

В Python вы можете удалить список, используя ключевое слово `del`. Вот пример:

```python
my_list = [1, 2, 3, 4, 5]
del my_list
```