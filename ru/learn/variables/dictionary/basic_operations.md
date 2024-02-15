> [!NOTE]
> Вы можете прочитать эту статью на сайте: https://diveintopython.org/ru/learn/variables/dictionary/basic-operations

Словари - это мощная и гибкая структура данных, которая позволяет вам хранить и манипулировать парами ключ-значение. Давайте рассмотрим некоторые общие операции и методы, которые вы можете выполнять со словарями в Python.

## Добавление Элемента в Словарь

Существует несколько способов добавления элемента в словарь.

### Присваивание Значения

Чтобы добавить пару ключ-значение в словарь Python, вы можете использовать следующий синтаксис:

```python
my_dict[key] = value
```

Здесь, `my_dict` это словарь, к которому вы хотите добавить элемент, `key` это ключ для нового элемента, а `value` это значение для нового элемента.

Например, если у вас есть пустой словарь и вы хотите добавить в него новый элемент с ключом `"name"` и значением `"John"`, вы можете сделать следующее:

```python
my_dict = {}
my_dict["name"] = "John"
print(my_dict) # Output: {'name': 'John'}.
```

Если ключ уже существует в словаре, его значение будет обновлено на новое значение. Если ключа не существует, новая пара ключ-значение будет добавлена в словарь.

### Метод `update()`

Метод `update()` принимает другой словарь в качестве аргумента и добавляет его пары ключ-значение к оригинальному словарю. Если ключ уже существует в оригинальном словаре, его значение будет обновлено на значение из нового словаря.

Вот пример:

```python
my_dict = {'a': 1, 'b': 2}
new_dict = {'c': 3, 'd': 4}

my_dict.update(new_dict)

print(my_dict)  # Output: {'a': 1, 'b': 2, 'c': 3, 'd': 4}
```

> Примечание: В словарях нет встроенного метода `append()`, так как словари не имеют внутреннего порядка. Вы не можете добавить элемент, используя метод `append()`.

## Удаление Элемента из Словаря

Чтобы удалить элемент из словаря в Python, вы можете использовать ключевое слово `del` вместе с ключом словаря.

Вот пример того, как удалить ключ из словаря вместе с его значением:

```python
# create a dictionary
my_dict = {'a': 1, 'b': 2, 'c': 3}

# delete an element with key 'b'
del my_dict['b']

# print the updated dictionary
print(my_dict) # Output: {'a': 1, 'c': 3}
```

В приведенном выше примере ключевое слово `del` используется для удаления пары ключ-значение с ключом `'b'` из словаря `my_dict`. Результирующий словарь содержит только элементы с ключами `'a'` и `'c'`.

## Итерация или Циклы со Словарями в Python

Мы покажем вам, как осуществлять итерацию по словарю в Python с использованием цикла `for`. Вот несколько способов итерации:

- Итерация по ключам:

```python
# create a dictionary
my_dict = {'a': 1, 'b': 2, 'c': 3}

# iterate over the keys and print them
for key in my_dict:
    print(key)
```

Выход:

```python
a
b
c
```

- Перебрать значения:

```python
# create a dictionary
my_dict = {'a': 1, 'b': 2, 'c': 3}

# iterate over the values and print them
for value in my_dict.values():
    print(value)
```

Выход:

```python
1
2
3
```

- Итерируйте по парам ключ-значение:

```python
# create a dictionary
my_dict = {'a': 1, 'b': 2, 'c': 3}

# iterate over the key-value pairs and print them
for key, value in my_dict.items():
    print(key, value)
```

Выход:

```python
a 1
b 2
c 3
```

В третьем примере мы используем метод `items()` словаря для получения списка пар ключ-значение. Затем мы используем распаковку кортежей для извлечения ключа и значения из каждой пары и выводим их.

Мы использовали `for` в наших примерах, но, конечно, вы также можете использовать `while` для перебора словаря в Python.

## Объединение Словарей в Python

Вы можете объединить два словаря, используя метод `update()`, о котором мы упоминали ранее. Метод `update()` добавляет пары ключ-значение из одного словаря в другой. Если ключ уже существует в целевом словаре, соответствующее значение будет обновлено новым значением.

Вот пример:

```python
dict1 = {'a': 1, 'b': 2}
dict2 = {'b': 3, 'c': 4}

dict1.update(dict2)

print(dict1) # Output: {'a': 1, 'b': 3, 'c': 4}
```

В этом примере у нас есть два словаря `dict1` и `dict2`. Мы используем метод `update()` для слияния `dict2` в `dict1`. Результирующий словарь это `{'a': 1, 'b': 3, 'c': 4}`.

> Обратите внимание: когда вызывается метод `update()`, он изменяет словарь, к которому был применен. Если вы не хотите изменять оригинальный словарь, вы можете создать новый словарь и использовать метод `update()` для слияния двух словарей.

## Упорядоченный или Отсортированный Словарь

Начиная с Python 3.7 и более поздних версий, словари гарантированно сохраняют порядок своих элементов так, как они были добавлены. Это означает, что элементы в словаре будут итерироваться в том же порядке, в котором они были вставлены.

До Python 3.7 словари не сохраняли порядок своих элементов, и итерация по словарю возвращала его элементы в произвольном порядке.

Вы можете получить отсортированный словарь по его ключам или значениям. Сортировка словаря может быть выполнена с использованием встроенной функции `sorted()`, которая возвращает список ключей или значений словаря в отсортированном порядке. Например:

```python
my_dict = {'c': 3, 'a': 1, 'b': 2}

# sort by keys
sorted_dict_by_keys = {k: my_dict[k] for k in sorted(my_dict)}

# sort by values
sorted_dict_by_values = {k: v for k, v in sorted(my_dict.items(), key=lambda item: item[1])}
```

Обратите внимание, что в приведенном выше примере исходный словарь `my_dict` не изменяется, и вместо этого создаются два новых словаря: `sorted_dict_by_keys` и `sorted_dict_by_values`.

## Вывод Словаря на Печать

Чтобы напечатать словарь в Python, вы можете использовать встроенную функцию `print()`. Существуют различные способы печати словаря в зависимости от того, как вы хотите форматировать вывод.

Вот пример того, как напечатать словарь:

```python
my_dict = {'apple': 1, 'pineapple': 2, 'orange': 3}

# Print the dictionary using the print() function
print(my_dict)
```

Это выведет следующее:

```python
{'apple': 1, 'pineapple': 2, 'orange': 3}
```

Если вы хотите напечатать каждую пару ключ-значение словаря на отдельной строке, вы можете использовать цикл `for` для итерации по словарю и печати каждого элемента:

```python
my_dict = {'apple': 1, 'pineapple': 2, 'orange': 3}

# Print each key-value pair on a separate line
for key, value in my_dict.items():
    print(key, ":", value)
```

Это выведет следующее:

```python
apple : 1
pineapple : 2
orange : 3
```

## Преобразование Словаря в Формат JSON в Python

Вы можете использовать встроенный модуль json в Python для преобразования словаря в формат JSON.

Вот пример кода:


```python
import json

# sample dictionary
my_dict = {'name': 'John', 'age': 30, 'city': 'New York'}

# convert dictionary to JSON
json_obj = json.dumps(my_dict)

# print the JSON object
print(json_obj)
```

В этом примере функция `json.dumps()` используется для преобразования словаря `my_dict` в объект JSON `json_obj`. Функция `print()` используется для отображения объекта JSON на консоли.

Вывод:

```python
{"name": "John", "age": 30, "city": "New York"}
```

Вы также можете сохранить объект JSON в файл, используя функцию `json.dump()` . Вот пример:

    
```python
import json

# sample dictionary
my_dict = {'name': 'John', 'age': 30, 'city': 'New York'}

# save dictionary to a JSON file
with open('data.json', 'w') as f:
    json.dump(my_dict, f)
```

В этом примере функция `json.dump()` используется для сохранения словаря `my_dict` в файл с именем `data.json`. Файл открывается в режиме записи с использованием оператора with.