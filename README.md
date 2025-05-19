Основные встроенные типы данных
```python
int — целые числа (без ограничения размера, например, 42, -10).
float — числа с плавающей точкой (например, 3.14, -0.001).
complex — комплексные числа (например, 3 + 4j).
list — списки, изменяемые упорядоченные последовательности (например, [1, 2, 3]).
tuple — кортежи, неизменяемые упорядоченные последовательности (например, (1, 2, 3)).
range — диапазоны, неизменяемые последовательности чисел (например, range(5) → 0, 1, 2, 3, 4).
str — строки, неизменяемые последовательности символов (например, "hello", 'world').
set — множества, изменяемые неупорядоченные коллекции уникальных элементов (например, {1, 2, 3}).
frozenset — неизменяемые множества (например, frozenset([1, 2, 3])).
dict — словари, изменяемые ассоциативные массивы с парами ключ-значение (например, {"a": 1, "b": 2}).
bool — булевы значения: True или False.
NoneType — специальный тип, представляющий отсутствие значения (None).
bytes — неизменяемые последовательности байтов (например, b"hello").
bytearray — изменяемые последовательности байтов (например, bytearray(b"hello")).
memoryview — представление памяти для работы с бинарными данными.
function — функции, созданные с помощью def или lambda.
module — импортированные модули.
class - Пользовательские классы (создаются с помощью class).
object — экземпляры классов.

```

Main
----
```python
if __name__ == '__main__':      # Пропускает следующую строку, если файл был импортирован.
    main()                      # Runs `def main(): ...` function.
```

List
----
```python
l = [1, 2, 3, ...]  # Создает объект списка. Также list(<collection>).
```

```python
<el>   = <list>[index]          # Первый индекс - 0. Последний - 1. Разрешает присваивания.
<list> = <list>[<slice>]        # Также <list>[from_inclusive : to_exclusive : ±step].
```

```python
<list>.append(<el>)             # Добавляет элемент в конец. Также <list> += [<el>].
<list>.extend(<collection>)     # Добавляет элементы в конец. Также <list> += <coll>.
```

```python
<list>.sort()                   # Сортирует элементы в порядке возрастания.
<list>.reverse()                # Переворачивает список на месте.
<list> = sorted(<collection>)   # Возвращает новый список с отсортированными элементами.
<iter> = reversed(<list>)       # Возвращает обратный итератор элементов.
```

```python
<el>  = max(<collection>)       # Возвращает наибольший элемент. Также min(<el_1>, ...).
<num> = sum(<collection>)       # Возвращает сумму элементов. Также math.prod(<coll>).
```

```python
elementwise_sum  = [sum(pair) for pair in zip(list_a, list_b)]
sorted_by_second = sorted(<collection>, key=lambda el: el[1])
sorted_by_both   = sorted(<collection>, key=lambda el: (el[1], el[0]))
flatter_list     = list(itertools.chain.from_iterable(<list>))
```

```python
<int> = len(<list>)             # Возвращает количество элементов. Также работает с dict, set и string.
<int> = <list>.count(<el>)      # Возвращает количество вхождений. Также `if <el> in <coll>: ...`.
<int> = <list>.index(<el>)      # Возвращает индекс первого вхождения или вызывает ValueError.
<el>  = <list>.pop()            # Удаляет и возвращает элемент с конца или по индексу, если он передан.
<list>.insert(<int>, <el>)      # Вставляет элемент по индексу и перемещает остальные вправо.
<list>.remove(<el>)             # Удаляет первое вхождение элемента или вызывает исключение ValueError.
<list>.clear()                  # Удаляет все элементы. Также работает со словарем и множеством.
```

Dictionary
----------
```python
<dict> = {key_1: val_1, key_2: val_2, ...}      # Используйте `<dict>[key]` для получения или установки значения.
```

```python
<view> = <dict>.keys()                          # Сборник ключей, отражающих изменения.
<view> = <dict>.values()                        # Набор значений, отражающих изменения.
<view> = <dict>.items()                         # Колл. кортежей «ключ-значение», отражающих изменения.
```

```python
value  = <dict>.get(key, default=None)          # Возвращает значение по умолчанию, если ключ отсутствует.
value  = <dict>.setdefault(key, default=None)   # Возвращает и записывает значение по умолчанию, если ключ отсутствует.
<dict> = collections.defaultdict(<type>)        # Возвращает словарь со значением по умолчанию `<type>()`.
<dict> = collections.defaultdict(lambda: 1)     # Возвращает словарь со значением по умолчанию 1.
```

```python
<dict> = dict(<collection>)                     # Создает словарь из набора пар ключ-значение.
<dict> = dict(zip(keys, values))                # Создает словарь из двух коллекций.
<dict> = dict.fromkeys(keys [, value])          # Создает словарь из набора ключей.
```

```python
<dict>.update(<dict>)                           # Добавляет элементы. Заменяет их соответствующими ключами.
value = <dict>.pop(key)                         # Удаляет элемент или вызывает KeyError, если он отсутствует.
{k for k, v in <dict>.items() if v == value}    # Возвращает набор ключей, указывающих на значение.
{k: v for k, v in <dict>.items() if k in keys}  # Фильтрует словарь по ключам.
```

### Counter
```python
>>> from collections import Counter
>>> counter = Counter(['blue', 'blue', 'blue', 'red', 'red'])
>>> counter['yellow'] += 1
>>> print(counter.most_common())
[('blue', 3), ('red', 2), ('yellow', 1)]
```

Set
---
```python
<set> = {<el_1>, <el_2>, ...}                   # Используйте `set()` для пустого набора.
```

```python
<set>.add(<el>)                                 # Or: <set> |= {<el>}
<set>.update(<collection> [, ...])              # Or: <set> |= <set>
```

```python
<set>  = <set>.union(<coll.>)                   # Or: <set> | <set>
<set>  = <set>.intersection(<coll.>)            # Or: <set> & <set>
<set>  = <set>.difference(<coll.>)              # Or: <set> - <set>
<set>  = <set>.symmetric_difference(<coll.>)    # Or: <set> ^ <set>
<bool> = <set>.issubset(<coll.>)                # Or: <set> <= <set>
<bool> = <set>.issuperset(<coll.>)              # Or: <set> >= <set>
```

```python
<el> = <set>.pop()                              # Вызывает KeyError, если пусто.
<set>.remove(<el>)                              # При отсутствии выдает KeyError.
<set>.discard(<el>)                             # Ошибки не возникает.
```

### Frozen Set

```python
<frozenset> = frozenset(<collection>)
```

Tuple
-----
```python
<tuple> = ()                               # Empty tuple.
<tuple> = (<el>,)                          # Or: <el>,
<tuple> = (<el_1>, <el_2> [, ...])         # Or: <el_1>, <el_2> [, ...]
```

### Named Tuple
Позволяет обращаться к элементам по имени, а не только по индексу.
Экономит память, так как работает, как обычный tuple.
Упрощает работу с данными, которые имеют фиксированную структуру.
```python
from collections import namedtuple
Point = namedtuple('Point', 'x y')
p = Point(1, y=2)
print(p)
Point(x=1, y=2)
print(p[0], p.x)
(1, 1)
```

Range
-----
```python
<range> = range(stop)                      # I.e. range(to_exclusive).
<range> = range(start, stop)               # I.e. range(from_inclusive, to_exclusive).
<range> = range(start, stop, ±step)        # I.e. range(from_inclusive, to_exclusive, ±step).
```

```python
>>> [i for i in range(3)]
[0, 1, 2]
```
Enumerate
---------
```python
for i, el in enumerate(<coll>, start=0):   # Returns next element and its index on each pass.
    ...
```
Iterator
--------
```python
<iter> = iter(<collection>)                # `iter(<iter>)` возвращает немодифицированный итератор.
<iter> = iter(<function>, to_exclusive)    # Последовательность возвращаемых значений до «to_exclusive».
<el>   = next(<iter> [, default])          # Вызывает StopIteration или возвращает «default» в конце.
<list> = list(<iter>)                      # Возвращает список оставшихся элементов итератора.
```
### Itertools
```python
import itertools as it
```
```python
<iter> = it.count(start=0, step=1)         # Возвращает обновленное значение бесконечно. Принимает числа с плавающей точкой.
<iter> = it.repeat(<el> [, times])         # Возвращает элемент бесконечно или указанное количество раз.
<iter> = it.cycle(<collection>)            # Повторяет последовательность бесконечно.
```

```python
<iter> = it.chain(<coll>, <coll> [, ...])  # Очищает коллекции по порядку (образно).
<iter> = it.chain.from_iterable(<coll>)    # Очищает коллекции внутри коллекции по порядку.
```

```python
<iter> = it.islice(<coll>, to_exclusive)   # Возвращает только первые элементы «to_exclusive».
<iter> = it.islice(<coll>, from_inc, …)    # `to_exclusive, +step_size`. Индексы могут быть None.
```

Generator
---------

```python
def count(start, step):
    while True:
        yield start
        start += step
```

```python
>>> counter = count(10, 2)
>>> next(counter), next(counter), next(counter)
(10, 12, 14)
```

Type
----
```python
<type> = type(<el>)                          # Or: <el>.__class__
<bool> = isinstance(<el>, <type>)            # Or: issubclass(type(<el>), <type>)
```

```python
>>> type('a'), 'a'.__class__, str
(<class 'str'>, <class 'str'>, <class 'str'>)
```

#### Some types do not have built-in names, so they must be imported:
```python
from types import FunctionType, MethodType, LambdaType, GeneratorType, ModuleType
```

### Abstract Base Classes
**Каждый абстрактный базовый класс определяет набор виртуальных подклассов. Затем эти классы распознаются isinstance() и issubclass() как подклассы ABC, хотя на самом деле они таковыми не являются. ABC также может вручную решить, является ли определенный класс его виртуальным подклассом, обычно на основе того, какие методы реализовал класс. Например, Iterable ABC ищет метод iter(), в то время как Collection ABC ищет iter(), contains() и len().**

```python
>>> from collections.abc import Iterable, Collection, Sequence
>>> isinstance([1, 2, 3], Iterable)
True
```

```text
+------------------+------------+------------+------------+
|                  |  Iterable  | Collection |  Sequence  |
+------------------+------------+------------+------------+
| list, range, str |    yes     |    yes     |    yes     |
| dict, set        |    yes     |    yes     |            |
| iter             |    yes     |            |            |
+------------------+------------+------------+------------+
```

```python
>>> from numbers import Number, Complex, Real, Rational, Integral
>>> isinstance(123, Number)
True
```

```text
+--------------------+----------+----------+----------+----------+----------+
|                    |  Number  |  Complex |   Real   | Rational | Integral |
+--------------------+----------+----------+----------+----------+----------+
| int                |   yes    |   yes    |   yes    |   yes    |   yes    |
| fractions.Fraction |   yes    |   yes    |   yes    |   yes    |          |
| float              |   yes    |   yes    |   yes    |          |          |
| complex            |   yes    |   yes    |          |          |          |
| decimal.Decimal    |   yes    |          |          |          |          |
+--------------------+----------+----------+----------+----------+----------+
```
String
------
```python
<str>  = <str>.strip()                       # Удаляет все пробельные символы с обоих концов.
<str>  = <str>.strip('<chars>')              # Удаляет переданные символы. Также lstrip/rstrip().
```

```python
<list> = <str>.split()                       # Разделяет по одному или нескольким пробельным символам.
<list> = <str>.split(sep=None, maxsplit=-1)  # Разделение на 'sep' str максимум за 'maxsplit' раз.
<list> = <str>.splitlines(keepends=False)    # На [\n\r\f\v\x1c-\x1e\x85\u2028\u2029] и \r\n.
<str>  = <str>.join(<coll_of_strings>)       # Объединяет элементы, используя строку в качестве разделителя.
```

```python
<bool> = <sub_str> in <str>                  # Проверяет, содержит ли строка подстроку.
<bool> = <str>.startswith(<sub_str>)         # Передайте кортеж строк для нескольких вариантов.
<int>  = <str>.find(<sub_str>)               # Возвращает начальный индекс первого совпадения или -1.
<int>  = <str>.index(<sub_str>)              # То же самое, но при отсутствии совпадений выдает ValueError.
```

```python
<str>  = <str>.lower()                       # Изменяет регистр. Также верхний/заглавный/заголовок().
<str>  = <str>.replace(old, new [, count])   # Заменяет «старое» на «новое» не более 'count' раз.
<str>  = <str>.translate(<table>)            # Используйте `str.maketrans(<dict>)` для генерации таблицы.
```

```python
<str>  = chr(<int>)                          # Преобразует целое число в символ Unicode.
<int>  = ord(<str>)                          # Преобразует символ Unicode в целое число.
```

### Property Methods
```python
<bool> = <str>.isdecimal()                   # Checks for [0-9]. Also [०-९] and [٠-٩].
<bool> = <str>.isdigit()                     # Checks for [²³¹…] and isdecimal().
<bool> = <str>.isnumeric()                   # Checks for [¼½¾…], [零〇一…] and isdigit().
<bool> = <str>.isalnum()                     # Checks for [a-zA-Z…] and isnumeric().
<bool> = <str>.isprintable()                 # Checks for [ !#$%…] and isalnum().
<bool> = <str>.isspace()                     # Checks for [ \t\n\r\f\v\x1c-\x1f\x85\xa0…].
```

Regex
-----
**Functions for regular expression matching.**

```python
import re
<str> = re.sub(r'<regex>', new, text, count=0)  # Заменяет все вхождения на 'new'.
<list> = re.findall(r'<regex>', text)           # Возвращает все вхождения как строки.
<list> = re.split(r'<regex>', text, maxsplit=0) # Добавьте скобки вокруг regex, чтобы сохранить совпадения.
<Match> = re.search(r'<regex>', text)           # Первое вхождение шаблона или None.
<Match> = re.match(r'<regex>', text)            # Поиск только в начале текста.
<iter> = re.finditer(r'<regex>', text)          # Возвращает все вхождения как объекты Match.
```


### Match Object
```python
<str> = <Match>.group()                         # Возвращает все совпадение. Также group(0).
<str> = <Match>.group(1)                        # Возвращает часть внутри первых скобок.
<tuple> = <Match>.groups()                      # Возвращает все части в скобках.
<int> = <Match>.start()                         # Возвращает начальный индекс совпадения.
<int> = <Match>.end()                           # Возвращает эксклюзивный конечный индекс совпадения.
```

### Special Sequences
```python
'\d' == '[0-9]'                      # Также [०-९…]. Соответствует десятичному символу.
'\w' == '[a-zA-Z0-9_]'               # Также [ª²³…]. Соответствует буквенно-цифровому символу или _.
'\s' == '[ \t\n\r\f\v]'              # Также [\x1c-\x1f…]. Соответствует пробелу.
```

Format
------
```python
<str> = f'{<el_1>}, {<el_2>}'                 # Фигурные скобки также могут содержать выражения.
<str> = '{}, {}'.format(<el_1>, <el_2>)       # Или: '{0}, {a}'.format(<el_1>, a=<el_2>)
<str> = '%s, %s' % (<el_1>, <el_2>)           # Избыточное и неполноценное форматирование в стиле C.
```

### Example
```python
>>> Person = collections.namedtuple('Person', 'name height')
>>> person = Person('Jean-Luc', 187)
>>> f'{person.name} is {person.height / 100} meters tall.'
'Jean-Luc is 1.87 meters tall.'
```

### General Options
```python
{<el>:<10}                               # '<el>      '
{<el>:^10}                               # '   <el>   '
{<el>:>10}                               # '      <el>'
{<el>:.<10}                              # '<el>......'
{<el>:0}                                 # '<el>'
```

### Strings
```python
{'abcde':10}                             # 'abcde     '
{'abcde':10.3}                           # 'abc       '
{'abcde':.3}                             # 'abc'
{'abcde'!r:10}                           # "'abcde'   "
```

### Numbers
```python
{123456:10}                              # '    123456'
{123456:10,}                             # '   123,456'
{123456:10_}                             # '   123_456'
{123456:+10}                             # '   +123456'
{123456:=+10}                            # '+   123456'
{123456: }                               # ' 123456'
{-123456: }                              # '-123456'
```

### Floats
```python
{1.23456:10.3}                           # '      1.23'
{1.23456:10.3f}                          # '     1.235'
{1.23456:10.3e}                          # ' 1.235e+00'
{1.23456:10.3%}                          # '  123.456%'
```

#### Comparison of presentation types:
```text
+--------------+----------------+----------------+----------------+----------------+
|              |    {<float>}   |   {<float>:f}  |   {<float>:e}  |   {<float>:%}  |
+--------------+----------------+----------------+----------------+----------------+
|  0.000056789 |   '5.6789e-05' |    '0.000057'  | '5.678900e-05' |    '0.005679%' |
|  0.00056789  |   '0.00056789' |    '0.000568'  | '5.678900e-04' |    '0.056789%' |
|  0.0056789   |   '0.0056789'  |    '0.005679'  | '5.678900e-03' |    '0.567890%' |
|  0.056789    |   '0.056789'   |    '0.056789'  | '5.678900e-02' |    '5.678900%' |
|  0.56789     |   '0.56789'    |    '0.567890'  | '5.678900e-01' |   '56.789000%' |
|  5.6789      |   '5.6789'     |    '5.678900'  | '5.678900e+00' |  '567.890000%' |
| 56.789       |  '56.789'      |   '56.789000'  | '5.678900e+01' | '5678.900000%' |
+--------------+----------------+----------------+----------------+----------------+
```

```text
+--------------+----------------+----------------+----------------+----------------+
|              |  {<float>:.2}  |  {<float>:.2f} |  {<float>:.2e} |  {<float>:.2%} |
+--------------+----------------+----------------+----------------+----------------+
|  0.000056789 |    '5.7e-05'   |      '0.00'    |   '5.68e-05'   |      '0.01%'   |
|  0.00056789  |    '0.00057'   |      '0.00'    |   '5.68e-04'   |      '0.06%'   |
|  0.0056789   |    '0.0057'    |      '0.01'    |   '5.68e-03'   |      '0.57%'   |
|  0.056789    |    '0.057'     |      '0.06'    |   '5.68e-02'   |      '5.68%'   |
|  0.56789     |    '0.57'      |      '0.57'    |   '5.68e-01'   |     '56.79%'   |
|  5.6789      |    '5.7'       |      '5.68'    |   '5.68e+00'   |    '567.89%'   |
| 56.789       |    '5.7e+01'   |     '56.79'    |   '5.68e+01'   |   '5678.90%'   |
+--------------+----------------+----------------+----------------+----------------+
```

### Ints
```python
{90:c}                           # 'Z'. Символ Unicode со значением 90.
{90:b}                           # '1011010'. Двоичное представление целого числа.
{90:X}                           # '5A'. Шестнадцатеричное с заглавными буквами.
```
Numbers
-------
```python
<int>      = int(<float/str/bool>)           # Or: math.trunc(<float>)
<float>    = float(<int/str/bool>)           # Or: <int/float>e±<int>
<complex>  = complex(real=0, imag=0)         # Or: <int/float> ± <int/float>j
<Fraction> = fractions.Fraction(0, 1)        # Or: Fraction(numerator=0, denominator=1)
<Decimal>  = decimal.Decimal(<str/int>)      # Or: Decimal((sign, digits, exponent))
```

### Built-in Functions
```python
<num> = pow(<num>, <num>)                        # Или: <number> ** <number>
<num> = abs(<num>)                               # <float> = abs(<complex>)
<num> = round(<num> [, ±ndigits])                # Также math.floor/ceil(<number>).
<num> = min(<collection>)                        # Также max(<num>, <num> [, ...]).
<num> = sum(<collection>)                        # Также math.prod(<collection>).
```

### Math
```python
from math import pi, inf, nan, isnan              # `inf*0` и `nan+1` возвращают nan.
from math import sqrt, factorial                  # `sqrt(-1)` вызывает ValueError.
from math import sin, cos, tan                    # Также: asin, градусы, радианы.
from math import log, log10, log2                 # Log принимает основание в качестве второго аргумента.
```

### Statistics
```python
from statistics import mean, median, mode            # Мода возвращает наиболее распространенное значение.
from statistics import variance, stdev               # Также: pvariance, pstdev, quantiles.
```

### Random
```python
from random import random, randint, uniform  # Also: gauss, choice, shuffle, seed.
```

```python
<float> = random()                        # Возвращает float внутри [0, 1).
<num> = randint/uniform(a, b)             # Возвращает int/float внутри [a, b].
<float> = gauss(mean, stdev)              # Также треугольный(low, high, mode).
<el> = choice(<sequence>)                 # Сохраняет его нетронутым. Также sample(pop, k).
shuffle(<list>)                           # Перемешивает список на месте.
```

### Hexadecimal Numbers
```python
<int> = ±0x<hex>                             # Or: ±0b<bin>
<int> = int('±<hex>', 16)                    # Or: int('±<bin>', 2)
<int> = int('±0x<hex>', 0)                   # Or: int('±0b<bin>', 0)
<str> = hex(<int>)                           # Returns '[-]0x<hex>'. Also bin().
```

### Bitwise Operators
```python
<int> = <int> & <int>                        # And (0b1100 & 0b1010 == 0b1000).
<int> = <int> | <int>                        # Or  (0b1100 | 0b1010 == 0b1110).
<int> = <int> ^ <int>                        # Xor (0b1100 ^ 0b1010 == 0b0110).
<int> = <int> << n_bits                      # Left shift. Use >> for right.
<int> = ~<int>                               # Not. Also -<int> - 1.
```
Combinatorics
-------------
```python
import itertools as it
```

```python
>>> list(it.product('abc', repeat=2))        #   a  b  c
[('a', 'a'), ('a', 'b'), ('a', 'c'),         # a x  x  x
 ('b', 'a'), ('b', 'b'), ('b', 'c'),         # b x  x  x
 ('c', 'a'), ('c', 'b'), ('c', 'c')]         # c x  x  x
```

```python
>>> list(it.permutations('abc', 2))          #   a  b  c
[('a', 'b'), ('a', 'c'),                     # a .  x  x
 ('b', 'a'), ('b', 'c'),                     # b x  .  x
 ('c', 'a'), ('c', 'b')]                     # c x  x  .
```

```python
>>> list(it.combinations('abc', 2))          #   a  b  c
[('a', 'b'), ('a', 'c'),                     # a .  x  x
 ('b', 'c')                                  # b .  .  x
]                                            # c .  .  .
```

Datetime
--------

```python
# $ pip3 install python-dateutil
from datetime import date, time, datetime, timedelta, timezone
import zoneinfo, dateutil.tz
```

```python
<D> = date(год, месяц, день)                         # Принимает только допустимые даты от 1 до 9999 г. н. э.
<T> = time(час=0, минута=0, секунда=0)               # Также: `микросекунда=0, tzinfo=None, fold=0`.
<DT> = datetime(год, месяц, день, час=0)             # Также: `минута=0, секунда=0, микросекунда=0, …`.
<TD> = timedelta(недели=0, дни=0, часы=0)            # Также: `минуты=0, секунды=0, микросекунды=0`.
```

### Now
```python
<D/DTn> = D/DT.today()                             # Текущая локальная дата или наивное DT. Также DT.now().
<DTa> = DT.now(<tzinfo>)                           # Осведомленное DT из текущего времени в переданном часовом поясе.
```

### Timezone
```python
<tzinfo> = timezone.utc                           # Лондон без летнего времени (DST).
<tzinfo> = timezone(<timedelta>)                  # Часовой пояс с фиксированным смещением от UTC.
<tzinfo> = dateutil.tz.tzlocal()                  # Локальный часовой пояс с динамическим смещением от UTC.
<tzinfo> = zoneinfo.ZoneInfo('<iana_key>')        # Зона 'Continent/City_Name' с динамическим смещением.
<DTa> = <DT>.astimezone([<tzinfo>])               # Преобразует DT в переданный или локальный фиксированный пояс.
<Ta/DTa> = <T/DT>.replace(tzinfo=<tzinfo>)        # Изменяет часовой пояс объекта без преобразования.
```

### Encode
```python
<D/T/DT> = D/T/DT.fromisoformat(<str>)            # Объект из строки ISO. Вызывает ValueError.
<DT> = DT.strptime(<str>, '<format>')             # Дата и время из пользовательской строки. См. Формат.
<D/DTn> = D/DT.fromordinal(<int>)                 # D/DT из дней с григорианского Нового года 1.
<DTn> = DT.fromtimestamp(<float>)                 # Локальное наивное DT из секунд с начала эпохи.
<DTa> = DT.fromtimestamp(<float>, <tz>)           # Знающее дату и время из секунд с начала эпохи.
```

### Decode
```python
<str> = <D/T/DT>.isoformat(sep='T')                # Также `timespec='auto/hours/minutes/seconds/…'`.
<str> = <D/T/DT>.strftime('<format>')              # Пользовательское строковое представление объекта.
<int> = <D/DT>.toordinal()                         # Дни с 1-го григорианского Нового года, игнорируя время и tz.
<float> = <DTn>.timestamp()                        # Секунды с начала эпохи, из локального наивного DT.
<float> = <DTa>.timestamp()                        # Секунды с начала эпохи, из известного datetime.
```

### Format
```python
>>> dt = datetime.strptime('2025-08-14 23:39:00.00 +0200', '%Y-%m-%d %H:%M:%S.%f %z')
>>> dt.strftime("%dth of %B '%y (%a), %I:%M %p %Z")
"14th of August '25 (Thu), 11:39 PM UTC+02:00"
```

### Arithmetics
```python
<bool> = <D/T/DTn> > <D/T/DTn>                            # Игнорирует скачки времени (атрибут fold). Также ==.
<bool> = <DTa> > <DTa>                                    # Игнорирует скачки времени, если они разделяют объект tzinfo.
<TD> = <D/DTn> - <D/DTn>                                  # Игнорирует скачки. Преобразуйте в UTC для получения фактической разницы.
<TD> = <DTa> - <DTa>                                      # Игнорирует скачки, если они разделяют объект tzinfo.
<D/DT> = <D/DT> ± <TD>                                    # Возвращаемая дата и время могут попадать в пропущенный час.
<TD> = <TD> * <float>                                     # Также `<TD> = abs(<TD>)`, `<TD> = <TD> ± <TD>`.
<float> = <TD> / <TD>                                     # Также `(<int>, <TD>) = divmod(<TD>, <TD>)`.
```

Function
--------
```python
def <func_name>(<nondefault_args>): ...                  # E.g. `def func(x, y): ...`.
def <func_name>(<default_args>): ...                     # E.g. `def func(x=0, y=0): ...`.
def <func_name>(<nondefault_args>, <default_args>): ...  # E.g. `def func(x, y=0): ...`.
```

### Function Call

```python
<obj> = <function>(<positional_args>)                    # E.g. `func(0, 0)`.
<obj> = <function>(<keyword_args>)                       # E.g. `func(x=0, y=0)`.
<obj> = <function>(<positional_args>, <keyword_args>)    # E.g. `func(0, y=0)`.
```

Splat Operator
--------------
```python
args, kwargs = (1, 2), {'z': 3}
func(*args, **kwargs)
```

#### Is the same as:
```python
func(1, 2, z=3)
```

### Inside Function Definition
```python
def add(*a):
    return sum(a)
```

```python
>>> add(1, 2, 3)
6
```

#### Allowed compositions of arguments and the ways they can be called:
```text
+---------------------------+--------------+--------------+----------------+
|                           |  func(1, 2)  | func(1, y=2) | func(x=1, y=2) |
+---------------------------+--------------+--------------+----------------+
| func(x, *args, **kwargs): |     yes      |     yes      |      yes       |
| func(*args, y, **kwargs): |              |     yes      |      yes       |
| func(*, x, **kwargs):     |              |              |      yes       |
+---------------------------+--------------+--------------+----------------+
```

### Other Uses
```python
<list>  = [*<collection> [, ...]]  # Or: list(<coll>) [+ ...]
<tuple> = (*<collection>, [...])   # Or: tuple(<coll>) [+ ...]
<set>   = {*<collection> [, ...]}  # Or: set(<coll>) [| ...]
<dict>  = {**<dict> [, ...]}       # Or: <dict> | ...
```

```python
head, *body, tail = <collection> # Head или tail можно опустить.
```

Inline
------
### Lambda
```python
<func> = lambda: <return_value>                         # Функция с одним оператором.
<func> = lambda <arg_1>, <arg_2>: <return_value>        # Также допускает аргументы по умолчанию.
```

### Comprehensions
```python
<list> = [i+1 for i in range(10)]                   # Or: [1, 2, ..., 10]
<iter> = (i for i in range(10) if i > 5)            # Or: iter([6, 7, 8, 9])
<set>  = {i+5 for i in range(10)}                   # Or: {5, 6, ..., 14}
<dict> = {i: i*2 for i in range(10)}                # Or: {0: 0, 1: 2, ..., 9: 18}
```

```python
>>> [l+r для l в 'abc' для r в 'abc']               # Внутренний цикл находится с правой стороны.['aa', 'ab', 'ac', ..., 'cc']
```

### Map, Filter, Reduce
```python
from functools import reduce
```

```python
<iter> = map(lambda x: x + 1, range(10))            # Or: iter([1, 2, ..., 10])
<iter> = filter(lambda x: x > 5, range(10))         # Or: iter([6, 7, 8, 9])
<obj>  = reduce(lambda out, x: out + x, range(10))  # Or: 45
```

### Any, All
```python
<bool> = any(<collection>)                   # Является ли `bool(<el>)` ​​Истиной для любого el?
values = [0, False, None, '', 5]  
print(any(values))  # True (потому что 5 является Истиной)

<bool> = all(<collection>)                   # Истина для всех? Также Истина, если пусто.
values = [1, True, 'hello']  
print(all(values))  # True (все элементы Истинны)
values = [1, False, 'hello']  
print(all(values))  # False (так как `False` присутствует)
empty_list = []  
print(all(empty_list))  # True (пустая коллекция считается полностью Истинной)
```

### Conditional Expression
```python
<obj> = <exp> if <condition> else <exp>             # Оценивается только одно выражение.
```

```python
>>> [i if i else 'zero' for i in (0, 1, 2, 3)]      # `any([0, '', [], None]) == False`
['zero', 1, 2, 3]
```

### And, Or
```python
<obj> = <exp> и <exp> [и ...]                        # Возвращает первый ложный или последний операнд.
<obj> = <exp> или <exp> [или ...]                    # Возвращает первый истинный или последний операнд.
```

### Walrus Operator
```python
>>> [i for a in '0123' if (i := int(a)) > 0]         # Присваивает переменной в середине предложения.[1, 2, 3]
```

### Named Tuple, Enum, Dataclass
```python
from collections import namedtuple
Point = namedtuple('Point', 'x y')                                   # Создает подкласс кортежа.
point = Point(0, 0)                                                  # Возвращает его экземпляр.

from enum import Enum
Direction = Enum('Direction', 'N E S W')                             # Создает подкласс Enum.
direction = Direction.N                                              # Возвращает его член.

from dataclasses import make_dataclass
Player = make_dataclass('Player', ['loc', 'dir'])                    # Создает класс.
player = Player(point, direction)                                    # Возвращает его экземпляр.
```


Imports
-------

```python
import <module>            # Imports a built-in or '<module>.py'.
import <package>           # Imports a built-in or '<package>/__init__.py'.
import <package>.<module>  # Imports a built-in or '<package>/<module>.py'.
```

Closure
-------

```python
def get_multiplier(a):
    def out(b):
        return a * b
    return out
```

```python
>>> multiply_by_3 = get_multiplier(3)
>>> multiply_by_3(10)
30
```

### Partial
```python
from functools import partial
<function> = partial(<function> [, <arg_1> [, ...]])
```

```python
>>> def multiply(a, b):
...     return a * b
>>> multiply_by_3 = partial(multiply, 3)
>>> multiply_by_3(10)
30
```
### Timeit — измерение времени выполнения небольшого блока кода
```python
import timeit
from functools import partial

def recur(n):
    if n == 0:
        return 1
    else:
        return n * recur(n - 1)

def fork(n):
    total = 1
    for i in range(1, n + 1):
        total *= i
    return total

# Фиксируем аргумент для функций
r1 = timeit.timeit(partial(recur, 900), number=1000)
r2 = timeit.timeit(partial(fork, 900), number=1000)

print("%.5f" % r1)
print("%.5f" % r2)
```
### cProfile — детальное профилирование функций
```python
import cProfile

def test_function():
    x = [i**2 for i in range(10000)]

cProfile.run('test_function()')
```
### Non-Local

```python
def get_counter():
    i = 0
    def out():
        nonlocal i
        i += 1
        return i
    return out
```

```python
>>> counter = get_counter()
>>> counter(), counter(), counter()
(1, 2, 3)
```

Decorator
---------
```python
def decorator(param):
    def wrapper(func):
        def inner(*args):
            return func(*args) * param
        return inner
    return wrapper

@decorator_name
def function_that_gets_passed_to_decorator():
    ...
```
Декоратор из класса – реализовать __call__():
```python
class Decorator:
    def __call__(self, func):
        def wrapper(*args):
            return func(*args)
        return wrapper
Вызов декоратора без @ – decorated_function = decorator(original_function).
```
Фабрика декораторов. Функция, возвращающая декоратор, например для управления правами
```python
def decorator_factory(prefix):
    def decorator(func):
        def wrapper(*args, **kwargs):
            print(f"{prefix} Вызов функции {func.__name__}")
            return func(*args, **kwargs)
        return wrapper
    return decorator
@decorator_factory("LOG:")
def say_hello(name):
    print(f"Привет, {name}!")
say_hello("Алекс")
```
### Debugger Example

```python
from functools import wraps

def my_decorator(func):
    def wrapper(*args, **kwargs):
        print("До вызова функции")
        return func(*args, **kwargs)
    return wrapper

@my_decorator
def greet():
    """Функция приветствия"""
    print("Привет, мир!")

print(greet.__name__)  # Выведет: wrapper (а должен быть greet)
print(greet.__doc__)   # Выведет: None (документация потерялась)

Исправленный вариант с wraps:
python
def my_decorator(func):
    @wraps(func)  # Сохраняем оригинальные метаданные
    def wrapper(*args, **kwargs):
        print("До вызова функции")
        return func(*args, **kwargs)
    return wrapper

@my_decorator
def greet():
    """Функция приветствия"""
    print("Привет, мир!")

print(greet.__name__)  # Выведет: greet
print(greet.__doc__)   # Выведет: Функция приветствия
```

### Cache, lru_cache

```python
from functools import cache, lru_cache

@lru_cache
def fib(n):
    return n if n < 2 else fib(n-2) + fib(n-1)
@cache
def fib(n):
    return n if n < 2 else fib(n-2) + fib(n-1)
```
* **Потенциальная проблема с кэшем заключается в том, что он может расти бесконечно. Чтобы очистить сохраненные значения, запустите `'<func>.cache_clear()'` или используйте вместо этого декоратор `'@lru_cache(maxsize=<int>)'`.**
* **Интерпретатор CPython ограничивает глубину рекурсии до 3000 по умолчанию. Чтобы увеличить ее, запустите `'sys.setrecursionlimit(<int>)'`.**

### Parametrized Decorator
```python
from functools import wraps

def debug(print_result=False):
    def decorator(func):
        @wraps(func)
        def out(*args, **kwargs):
            result = func(*args, **kwargs)
            print(func.__name__, result if print_result else '')
            return result
        return out
    return decorator

@debug(print_result=True)
def add(x, y):
    return x + y
```

Class
-----

```python
class MyClass:
    def __init__(self, a):
        self.a = a
    def __str__(self):
        return str(self.a)
    def __repr__(self):
        class_name = self.__class__.__name__
        return f'{class_name}({self.a!r})'

    @classmethod
    def get_class_name(cls):
        return cls.__name__
```

```python
>>> obj = MyClass(1)
>>> obj.a, str(obj), repr(obj)
(1, '1', 'MyClass(1)')
```

#### Expressions that call the str() method:
```python
print(<obj>)
f'{<obj>}'
logging.warning(<obj>)
csv.writer(<file>).writerow([<obj>])
raise Exception(<obj>)
```

#### Expressions that call the repr() method:
```python
print/str/repr([<obj>])
print/str/repr({<obj>: <obj>})
f'{<obj>!r}'
Z = make_dataclass('Z', ['a']); print/str/repr(Z(<obj>))
>>> <obj>
```

### Subclass

```python
class Person:
    def __init__(self, name):
        self.name = name
    def __repr__(self):
        return f'Person({self.name!r})'
    def __lt__(self, other):
        return self.name < other.name

class Employee(Person):
    def __init__(self, name, staff_num):
        super().__init__(name)
        self.staff_num = staff_num
    def __repr__(self):
        return f'Employee({self.name!r}, {self.staff_num})'
```

```python
>>> people = {Person('Ann'), Employee('Bob', 0)}
>>> sorted(people)
[Person('Ann'), Employee('Bob', 0)]
```

### Type Annotations

```python
from collections import abc

<name>: <type> [| ...] [= <obj>]
<name>: list/set/abc.Iterable/abc.Sequence[<type>] [= <obj>]
<name>: dict/tuple[<type>, ...] [= <obj>]
```

### Dataclass
```python
from dataclasses import dataclass, field, make_dataclass

@dataclass(order=False, frozen=False)
class <class_name>:
    <attr_name>: <type>
    <attr_name>: <type> = <default_value>
    <attr_name>: list/dict/set = field(default_factory=list/dict/set)
```

```python
P = make_dataclass('P', ['x', 'y'])
P = make_dataclass('P', [('x', float), ('y', float)])
P = make_dataclass('P', [('x', float, 0), ('y', float, 0)])
```

### Property
```python
class Person:
    @property
    def name(self):
        return ' '.join(self._name)

    @name.setter
    def name(self, value):
        self._name = value.split()
```

```python
>>> person = Person()
>>> person.name = '\t Guido  van Rossum \n'
>>> person.name
'Guido van Rossum'
```

### Slots
```python
class MyClassWithSlots:
    __slots__ = ['a']
    def __init__(self):
        self.a = 1
```

### Copy
```python
from copy import copy, deepcopy
<object> = copy/deepcopy(<object>)
```

Duck Types
----------
### Comparable

```python
class MyComparable:
    def __init__(self, a):
        self.a = a
    def __eq__(self, other):
        if isinstance(other, type(self)):
            return self.a == other.a
        return NotImplemented
```

### Hashable

```python
class MyHashable:
    def __init__(self, a):
        self._a = a
    @property
    def a(self):
        return self._a
    def __eq__(self, other):
        if isinstance(other, type(self)):
            return self.a == other.a
        return NotImplemented
    def __hash__(self):
        return hash(self.a)
```

### Sortable

```python
from functools import total_ordering

@total_ordering
class MySortable:
    def __init__(self, a):
        self.a = a
    def __eq__(self, other):
        if isinstance(other, type(self)):
            return self.a == other.a
        return NotImplemented
    def __lt__(self, other):
        if isinstance(other, type(self)):
            return self.a < other.a
        return NotImplemented
```

### Iterator
```python
class Counter:
    def __init__(self):
        self.i = 0
    def __next__(self):
        self.i += 1
        return self.i
    def __iter__(self):
        return self
```

```python
>>> counter = Counter()
>>> next(counter), next(counter), next(counter)
(1, 2, 3)
```

#### Python has many different iterator objects:

### Callable
```python
class Counter:
    def __init__(self):
        self.i = 0
    def __call__(self):
        self.i += 1
        return self.i
```

```python
>>> counter = Counter()
>>> counter(), counter(), counter()
(1, 2, 3)
```

### Context Manager
```python
class MyOpen:
    def __init__(self, filename):
        self.filename = filename
    def __enter__(self):
        self.file = open(self.filename)
        return self.file
    def __exit__(self, exc_type, exception, traceback):
        self.file.close()
```

```python
>>> with open('test.txt', 'w') as file:
...     file.write('Hello World!')
>>> with MyOpen('test.txt') as file:
...     print(file.read())
Hello World!
```


Iterable Duck Types
-------------------
### Iterable
```python
class MyIterable:
    def __init__(self, a):
        self.a = a
    def __iter__(self):
        return iter(self.a)
    def __contains__(self, el):
        return el in self.a
```

```python
>>> obj = MyIterable([1, 2, 3])
>>> [el for el in obj]
[1, 2, 3]
>>> 1 in obj
True
```

### Collection
```python
class MyCollection:
    def __init__(self, a):
        self.a = a
    def __iter__(self):
        return iter(self.a)
    def __contains__(self, el):
        return el in self.a
    def __len__(self):
        return len(self.a)
```

### Sequence
```python
class MySequence:
    def __init__(self, a):
        self.a = a
    def __iter__(self):
        return iter(self.a)
    def __contains__(self, el):
        return el in self.a
    def __len__(self):
        return len(self.a)
    def __getitem__(self, i):
        return self.a[i]
    def __reversed__(self):
        return reversed(self.a)
```

### ABC Sequence
```python
from collections import abc

class MyAbcSequence(abc.Sequence):
    def __init__(self, a):
        self.a = a
    def __len__(self):
        return len(self.a)
    def __getitem__(self, i):
        return self.a[i]
```

#### Table of required and automatically available special methods:
```text
+------------+------------+------------+------------+--------------+
|            |  Iterable  | Collection |  Sequence  | abc.Sequence |
+------------+------------+------------+------------+--------------+
| iter()     |    REQ     |    REQ     |    Yes     |     Yes      |
| contains() |    Yes     |    Yes     |    Yes     |     Yes      |
| len()      |            |    REQ     |    REQ     |     REQ      |
| getitem()  |            |            |    REQ     |     REQ      |
| reversed() |            |            |    Yes     |     Yes      |
| index()    |            |            |            |     Yes      |
| count()    |            |            |            |     Yes      |
+------------+------------+------------+------------+--------------+
```
Accessify — это библиотека для Python, которая добавляет поддержку модификаторов доступа (private, protected) и интерфейсов
```python
pip install accessify
```
```python
from accessify import protected, private

class User:
    _name = "Alex"
    __age=30
    
u = User()
print(u._name)
print(u._User__age)

class User1:
    _name = "Alex"
    __age=30
    @protected
    def _get_name(self):
        return self._name
    @private
    def __get_age(self):
        return self.__age
    
u = User1()
print(u._get_name())
# print(u.__get_age())
print(u._User1__get_age())
```
Enum
----
```python
from enum import Enum, auto
```

```python
class <enum_name>(Enum):
<member_name> = auto()                  # Приращение последнего числового значения или 1.
<member_name> = <value>                 # Значения не обязательно должны быть хешируемыми.
<member_name> = <el_1>, <el_2>          # Значения могут быть коллекциями (это кортеж).
```

```python
<member> = <enum>.<member_name>           # Возвращает члена. Вызывает AttributeError.
<member> = <enum>['<member_name>']        # Возвращает члена. Вызывает KeyError.
<member> = <enum>(<value>)                # Возвращает члена. Вызывает ValueError.
<str> = <member>.name                     # Возвращает имя члена.
<obj> = <member>.value                    # Возвращает значение члена.
```

```python
<list> = list(<enum>)                     # Возвращает элементы перечисления.
<list> = [a.name for a in <enum>]         # Возвращает имена элементов перечисления.
<list> = [a.value for a in <enum>]        # Возвращает значения элементов перечисления.
```

```python
<enum> = type(<member>)                   # Возвращает перечисление члена.
<iter> = itertools.cycle(<enum>)          # Возвращает бесконечный итератор членов.
<member> = random.choice(list(<enum>))    # Возвращает случайного члена.
```

### Inline
```python
Cutlery = Enum('Cutlery', 'FORK KNIFE SPOON')
Cutlery = Enum('Cutlery', ['FORK', 'KNIFE', 'SPOON'])
Cutlery = Enum('Cutlery', {'FORK': 1, 'KNIFE': 2, 'SPOON': 3})
```

#### User-defined functions cannot be values, so they must be wrapped:
```python
from functools import partial
LogicOp = Enum('LogicOp', {'AND': partial(lambda l, r: l and r),
                           'OR':  partial(lambda l, r: l or r)})
```


Exceptions
----------
```python
try:
    <code>
except <exception>:
    <code>
```

### Complex Example
```python
try:
    <code_1>
except <exception_a>:
    <code_2_a>
except <exception_b>:
    <code_2_b>
else:
    <code_2_c>
finally:
    <code_3>
```
### Catching Exceptions
```python
except <exception>: ...
except <exception> as <name>: ...
except (<exception>, [...]): ...
except (<exception>, [...]) as <name>: ...
```
### Raising Exceptions
```python
raise <exception>
raise <exception>()
raise <exception>(<obj> [, ...])
```

#### Re-raising caught exception:
```python
except <exception> [as <name>]:
    ...
    raise
```

### Exception Object
```python
arguments = <name>.args
exc_type  = <name>.__class__
filename  = <name>.__traceback__.tb_frame.f_code.co_filename
func_name = <name>.__traceback__.tb_frame.f_code.co_name
line      = linecache.getline(filename, <name>.__traceback__.tb_lineno)
trace_str = ''.join(traceback.format_tb(<name>.__traceback__))
error_msg = ''.join(traceback.format_exception(type(<name>), <name>, <name>.__traceback__))
```

### Built-in Exceptions
```text
BaseException
 +-- SystemExit                   # Вызывается функцией sys.exit().
 +-- KeyboardInterrupt            # Возникает, когда пользователь нажимает клавишу прерывания (ctrl-c).
 +-- Exception                    # Исключения, определяемые пользователем, должны быть производными от этого класса.
      +-- ArithmeticError         # Базовый класс для арифметических ошибок, таких как ZeroDivisionError.
      +-- AssertionError          # Вызывается `assert <exp>`, если выражение возвращает ложное значение.
      +-- AttributeError          # Возникает, когда у объекта нет запрошенного атрибута/метода.
      +-- EOFError                # Вызывается функцией input() при достижении конца файла.
      +-- LookupError             # Базовый класс для ошибок, когда коллекция не может найти элемент.
      |    +-- IndexError         # Возникает, когда индекс последовательности выходит за пределы допустимого диапазона.
      |    +-- KeyError           # Возникает, если отсутствует ключ словаря или элемент набора.
      +-- MemoryError             # Недостаточно памяти. Может быть слишком поздно начинать удалять переменные.
      +-- NameError               # Возникает при использовании несуществующего имени (переменной/функции/класса).
      |    +-- UnboundLocalError  # Возникает, когда локальное имя используется до его определения.
      +-- OSError                 # Ошибки, такие как FileExistsError/TimeoutError (см. #Open).
      |    +-- ConnectionError    # Ошибки, такие как BrokenPipeError/ConnectionAbortedError.
      +-- RuntimeError            # Возникает из-за ошибок, не попадающих в другие категории.
      |    +-- NotImplementedEr…  # Может быть вызвано абстрактными методами или незавершенным кодом.
      |    +-- RecursionError     # Возникает при превышении максимальной глубины рекурсии (по умолчанию 3 КБ).
      +-- StopIteration           # Возникает, когда в next() передается пустой итератор.
      +-- TypeError               # Когда в функцию передается аргумент неправильного типа.
      +-- ValueError              # Когда аргумент имеет правильный тип, но неподходящее значение.
```

#### Collections and their exceptions:
```text
+-----------+------------+------------+------------+
|           |    List    |    Set     |    Dict    |
+-----------+------------+------------+------------+
| getitem() | IndexError |            |  KeyError  |
| pop()     | IndexError |  KeyError  |  KeyError  |
| remove()  | ValueError |  KeyError  |            |
| index()   | ValueError |            |            |
+-----------+------------+------------+------------+
```

#### Useful built-in exceptions:
```python
raise TypeError('Argument is of the wrong type!')
raise ValueError('Argument has the right type but an inappropriate value!')
raise RuntimeError('I am too lazy to define my own exception!')
```

### User-defined Exceptions
```python
class MyError(Exception): pass
class MyInputError(MyError): pass
```


Exit
----
```python
import sys
sys.exit()      # Выход с кодом выхода 0 (успешно).
sys.exit(<int>) # Выход с переданным кодом выхода.
sys.exit(<obj>) # Выводит на stderr и выход с 1.
```


Print
-----
```python
print(<el_1>, ..., sep=' ', end='\n', file=sys.stdout, flush=False)
```

### Pretty Print
```python
from pprint import pprint
pprint(<collection>, width=80, depth=None, compact=False, sort_dicts=True)
```

Input
-----
```python
<str> = input()
```

Command Line Arguments
----------------------
```python
import sys
scripts_path = sys.argv[0]
arguments    = sys.argv[1:]
```

### Argument Parser
```python
from argparse import ArgumentParser, FileType
p = ArgumentParser(description=<str>)                                     # Возвращает парсер.
p.add_argument('-<short_name>', '--<name>', action='store_true')          # Флаг (по умолчанию False).
p.add_argument('-<short_name>', '--<name>', type=<type>)                  # Опция (по умолчанию None).
p.add_argument('<name>', type=<type>, nargs=1)                            # Обязательный первый аргумент.
p.add_argument('<name>', type=<type>, nargs='+')                          # Обязательные оставшиеся аргументы.
p.add_argument('<name>', type=<type>, nargs='?/*')                        # Необязательный аргумент/ы.
args = p.parse_args()                                                     # Выход при ошибке синтаксического анализа.
<obj> = args.<name>                                                       # Возвращает `<type>(<arg>)`.
```

Open
----
```python
<file> = open(<path>, mode='r', encoding=None, newline=None)
```
* **`'encoding=None' ` означает, что используется кодировка по умолчанию, которая зависит от платформы. Лучше всего использовать `'encoding="utf-8"'`, когда это возможно.**
* **`'newline=None'`   означает, что все различные комбинации конца строки преобразуются в '\n' при чтении, а при записи все символы '\n' преобразуются в разделитель строк по умолчанию в системе.**
* **`'newline=""'`     означает, что преобразования не выполняются, но ввод по-прежнему разбивается на фрагменты с помощью readline() и readlines() для каждого '\n', '\r' и '\r\n'.**

### Modes
* **`'r'`  - Read. Used by default.**
* **`'w'`  - Write. Deletes existing contents.**
* **`'x'`  - Write or fail if the file already exists.**
* **`'a'`  - Append. Creates new file if it doesn't exist.**
* **`'w+'` - Read and write. Deletes existing contents.**
* **`'r+'` - Read and write from the start.**
* **`'a+'` - Read and write from the end.**
* **`'b'`  - Binary mode (`'rb'`, `'wb'`, `'xb'`, …).**

### Exceptions
* **`'FileNotFoundError'` can be raised when reading with `'r'` or `'r+'`.**
* **`'FileExistsError'` can be raised when writing with `'x'`.**
* **`'IsADirectoryError'` and `'PermissionError'` can be raised by any.**
* **`'OSError'` is the parent class of all listed exceptions.**

### File Object
```python
<file>.seek(0)                    # Перемещает в начало файла.
<file>.seek(offset)               # Перемещает на 'offset' символов/байтов от начала.
<file>.seek(0, 2)                 # Перемещает в конец файла.
<bin_file>.seek(±offset, origin)  # Origin: 0 начало, 1 текущая позиция, 2 конец.
```

```python
<str/bytes> = <file>.read(size=-1)    # Читает 'size' символов/байтов или до EOF.
<str/bytes> = <file>.readline()       # Возвращает строку или пустую строку/байты по EOF.
<list> = <file>.readlines()           # Возвращает список оставшихся строк.
<str/bytes> = next(<file>)            # Возвращает строку с использованием буфера. Не смешивайте.
```

```python
<file>.write(<str/bytes>)        # Записывает строку или объект байтов.
<file>.writelines(<collection>)  # Записывает коллекцию строк или объектов байтов.
<file>.flush()                   # Очищает буфер записи. Запускается каждые 4096/8192 Б.
<file>.close()                   # Закрывает файл после очистки буфера записи.
```

### Read Text from File
```python
def read_file(filename):
    with open(filename, encoding='utf-8') as file:
        return file.readlines()
```

### Write Text to File
```python
def write_to_file(filename, text):
    with open(filename, 'w', encoding='utf-8') as file:
        file.write(text)
```
Paths
-----
```python
import os, glob
from pathlib import Path
```

```python
<str> = os.getcwd()                 # Возвращает рабочий каталог. Начинается как $PWD оболочки.
<str> = os.path.join(<path>, ...)   # Объединяет два или более компонентов имени пути.
<str> = os.path.realpath(<path>)    # Разрешает символические ссылки и вызывает path.abspath().
```

```python
<str> = os.path.basename(<path>)    # Возвращает конечный компонент пути.
<str> = os.path.dirname(<path>)     # Возвращает путь без конечного компонента.
<tup.> = os.path.splitext(<path>)   # Разделяет по последнему периоду конечного компонента.
```

```python
<list> = os.listdir(path='.')       # Возвращает имена файлов, расположенных по пути.
<list> = glob.glob('<pattern>')     # Возвращает пути, соответствующие шаблону подстановочных знаков.
```

```python
<bool> = os.path.exists(<path>)     # Or: <Path>.exists()
<bool> = os.path.isfile(<path>)     # Or: <DirEntry/Path>.is_file()
<bool> = os.path.isdir(<path>)      # Or: <DirEntry/Path>.is_dir()
```

```python
<stat> = os.stat(<path>)            # Or: <DirEntry/Path>.stat()
<num>  = <stat>.st_mtime/st_size/…  # Modification time, size in bytes, etc.
```

### DirEntry

```python
<iter> = os.scandir(path='.')   # Возвращает объекты DirEntry, расположенные по пути.
<str> = <DirEntry>.path         # Возвращает весь путь в виде строки.
<str> = <DirEntry>.name         # Возвращает конечный компонент в виде строки.
<file> = open(<DirEntry>)       # Открывает файл и возвращает его файловый объект.
```

### Path Object
```python
<Path> = Path(<path> [, ...])       # Принимает строки, объекты Paths и DirEntry.
<Path> = <path> / <path> [/ ...]    # Первый или второй путь должен быть объектом Path.
<Path> = <Path>.resolve()           # Возвращает абсолютный путь с разрешенными символическими ссылками.
```

```python
<Path> = Path()                   # Возвращает относительный CWD. Также Path('.').
<Path> = Path.cwd()               # Возвращает абсолютный CWD. Также Path().resolve().
<Path> = Path.home()              # Возвращает домашний каталог пользователя (абсолютный).
<Path> = Path(__file__).resolve() # Возвращает путь к модулю, если CWD не был изменен.
```

```python
<Path> = <Path>.parent       # Возвращает Path без конечного компонента.
<str> = <Path>.name          # Возвращает конечный компонент в виде строки.
<str> = <Path>.suffix        # Возвращает последнее расширение имени, например, '.py'.
<str> = <Path>.stem          # Возвращает имя без последнего расширения.
<tup.> = <Path>.parts        # Возвращает все компоненты в виде строк.
```

```python
<iter> = <Path>.iterdir()         # Возвращает содержимое каталога как объекты Path.
<iter> = <Path>.glob('<pattern>') # Возвращает Paths, соответствующие шаблону подстановочных знаков.
```

```python
<str> = str(<Path>)       # Возвращает путь как str. Также <Path>.as_uri().
<file> = open(<Path>)     # Также <Path>.read/write_text/bytes(<args>).
```


OS Commands
-----------
```python
import os, shutil, subprocess
```

```python
os.chdir(<path>)                # Изменяет текущий рабочий каталог (CWD).
os.mkdir(<path>, mode=0o777)    # Создает каталог. Права доступа указаны в восьмеричном формате.
os.makedirs(<path>, mode=0o777) # Создает все каталоги пути. Также `exist_ok=False`.
```

```python
shutil.copy(from, to)         # Копирует файл. 'to' может существовать или быть каталогом.
shutil.copy2(from, to)        # Также копирует время создания и изменения.
shutil.copytree(from, to)     # Копирует каталог. 'to' не должен существовать.
```

```python
os.rename(from, to)         # Переименовывает/перемещает файл или каталог.
os.replace(from, to)        # То же самое, но перезаписывает файл 'to' даже в Windows.
shutil.move(from, to)       # Rename(), который перемещает в 'to', если это каталог.
```

```python
os.remove(<path>)         # Удаляет файл.
os.rmdir(<path>)          # Удаляет пустой каталог.
shutil.rmtree(<path>)     # Удаляет каталог.
```

### Shell Commands
```python
<pipe> = os.popen('<commands>') # Выполняет команды в sh/cmd. Возвращает объединенный stdout.
<str> = <pipe>.read(size=-1) # Читает символы 'size' или до EOF. Также readline/s().
<int> = <pipe>.close() # Возвращает None, если последняя команда завершилась с кодом возврата 0.
```

#### Sends '1 + 1' to the basic calculator and captures its output:
```python
>>> subprocess.run('bc', input='1 + 1\n', capture_output=True, text=True)
CompletedProcess(args='bc', returncode=0, stdout='2\n', stderr='')
```

#### Sends test.in to the basic calculator running in standard mode and saves its output to test.out:
```python
>>> from shlex import split
>>> os.popen('echo 1 + 1 > test.in')
>>> subprocess.run(split('bc -s'), stdin=open('test.in'), stdout=open('test.out', 'w'))
CompletedProcess(args=['bc', '-s'], returncode=0)
>>> open('test.out').read()
'2\n'
```


JSON
----
**Text file format for storing collections of strings and numbers.**

```python
import json
<str>  = json.dumps(<list/dict>)    # Converts collection to JSON string.
<coll> = json.loads(<str>)          # Converts JSON string to collection.
```

### Read Collection from JSON File
```python
def read_json_file(filename):
    with open(filename, encoding='utf-8') as file:
        return json.load(file)
```

### Write Collection to JSON File
```python
def write_to_json_file(filename, collection):
    with open(filename, 'w', encoding='utf-8') as file:
        json.dump(collection, file, ensure_ascii=False, indent=2)
```


Pickle
------
**Binary file format for storing Python objects.**

```python
import pickle
<bytes>  = pickle.dumps(<object>)   # Converts object to bytes object.
<object> = pickle.loads(<bytes>)    # Converts bytes object to object.
```

### Read Object from Pickle File
```python
def read_pickle_file(filename):
    with open(filename, 'rb') as file:
        return pickle.load(file)
```

### Write Object to Pickle File
```python
def write_to_pickle_file(filename, an_object):
    with open(filename, 'wb') as file:
        pickle.dump(an_object, file)
```


CSV
---
**Text file format for storing spreadsheets.**

```python
import csv
```

### Read
```python
<reader> = csv.reader(<file>)       # Also: `dialect='excel', delimiter=','`.
<list>   = next(<reader>)           # Returns next row as a list of strings.
<list>   = list(<reader>)           # Returns a list of remaining rows.
```

### Write
```python
<writer> = csv.writer(<file>)       # Also: `dialect='excel', delimiter=','`.
<writer>.writerow(<collection>)     # Encodes objects using `str(<el>)`.
<writer>.writerows(<coll_of_coll>)  # Appends multiple rows.
```

### Dialects
```text
+------------------+--------------+--------------+--------------+
|                  |     excel    |   excel-tab  |     unix     |
+------------------+--------------+--------------+--------------+
| delimiter        |       ','    |      '\t'    |       ','    |
| lineterminator   |    '\r\n'    |    '\r\n'    |      '\n'    |
| quotechar        |       '"'    |       '"'    |       '"'    |
| escapechar       |      None    |      None    |      None    |
| doublequote      |      True    |      True    |      True    |
| quoting          |         0    |         0    |         1    |
| skipinitialspace |     False    |     False    |     False    |
+------------------+--------------+--------------+--------------+
```

### Read Rows from CSV File
```python
def read_csv_file(filename, **csv_params):
    with open(filename, encoding='utf-8', newline='') as file:
        return list(csv.reader(file, **csv_params))
```

### Write Rows to CSV File
```python
def write_to_csv_file(filename, rows, mode='w', **csv_params):
    with open(filename, mode, encoding='utf-8', newline='') as file:
        writer = csv.writer(file, **csv_params)
        writer.writerows(rows)
```


SQLite
------
```python
import sqlite3
<conn> = sqlite3.connect(<path>)               # Opens existing or new file. Also ':memory:'.
<conn>.close()                                 # Closes connection. Discards uncommitted data.
```

### Read
```python
<cursor> = <conn>.execute('<query>')           # Can raise a subclass of sqlite3.Error.
<tuple>  = <cursor>.fetchone()                 # Returns next row. Also next(<cursor>).
<list>   = <cursor>.fetchall()                 # Returns remaining rows. Also list(<cursor>).
```

### Write
```python
<conn>.execute('<query>')                      # Can raise a subclass of sqlite3.Error.
<conn>.commit()                                # Saves all changes since the last commit.
<conn>.rollback()                              # Discards all changes since the last commit.
```

#### Or:
```python
with <conn>:                                   # Exits the block with commit() or rollback(),
    <conn>.execute('<query>')                  # depending on whether any exception occurred.
```

### Placeholders
```python
<conn>.execute('<query>', <list/tuple>)        # Replaces every question mark with an item.
<conn>.execute('<query>', <dict/namedtuple>)   # Replaces every :<key> with value.
<conn>.executemany('<query>', <coll_of_coll>)  # Runs execute() multiple times.
```

### Example
**Values are not actually saved in this example because `'conn.commit()'` is omitted!**
```python
>>> conn = sqlite3.connect('test.db')
>>> conn.execute('CREATE TABLE person (person_id INTEGER PRIMARY KEY, name, height)')
>>> conn.execute('INSERT INTO person VALUES (NULL, ?, ?)', ('Jean-Luc', 187)).lastrowid
1
>>> conn.execute('SELECT * FROM person').fetchall()
[(1, 'Jean-Luc', 187)]
```

### SQLAlchemy
**Library for interacting with various DB systems via SQL, method chaining, or ORM.**
```python
# $ pip3 install sqlalchemy
from sqlalchemy import create_engine, text
<engine> = create_engine('<url>')              # Url: 'dialect://user:password@host/dbname'.
<conn>   = <engine>.connect()                  # Creates a connection. Also <conn>.close().
<cursor> = <conn>.execute(text('<query>'), …)  # `<dict>`. Replaces every :<key> with value.
with <conn>.begin(): ...                       # Exits the block with commit or rollback.
```

```text
+-----------------+--------------+----------------------------------+
| Dialect         | pip3 install |           Dependencies           |
+-----------------+--------------+----------------------------------+
| mysql           | mysqlclient  | www.pypi.org/project/mysqlclient |
| postgresql      | psycopg2     | www.pypi.org/project/psycopg2    |
| mssql           | pyodbc       | www.pypi.org/project/pyodbc      |
| oracle+oracledb | oracledb     | www.pypi.org/project/oracledb    |
+-----------------+--------------+----------------------------------+
```


Bytes
-----
**A bytes object is an immutable sequence of single bytes. Mutable version is called bytearray.**

```python
<bytes> = b'<str>'                       # Only accepts ASCII characters and \x00-\xff.
<int>   = <bytes>[index]                 # Returns an int in range from 0 to 255.
<bytes> = <bytes>[<slice>]               # Returns bytes even if it has only one element.
<bytes> = <bytes>.join(<coll_of_bytes>)  # Joins elements using bytes as a separator.
```

### Encode
```python
<bytes> = bytes(<coll_of_ints>)          # Ints must be in range from 0 to 255.
<bytes> = bytes(<str>, 'utf-8')          # Encodes the string. Also <str>.encode().
<bytes> = bytes.fromhex('<hex>')         # Hex pairs can be separated by whitespaces.
<bytes> = <int>.to_bytes(n_bytes, …)     # `byteorder='big/little', signed=False`.
```

### Decode
```python
<list>  = list(<bytes>)                  # Returns ints in range from 0 to 255.
<str>   = str(<bytes>, 'utf-8')          # Returns a string. Also <bytes>.decode().
<str>   = <bytes>.hex()                  # Returns hex pairs. Accepts `sep=<str>`.
<int>   = int.from_bytes(<bytes>, …)     # `byteorder='big/little', signed=False`.
```

### Read Bytes from File
```python
def read_bytes(filename):
    with open(filename, 'rb') as file:
        return file.read()
```

### Write Bytes to File
```python
def write_bytes(filename, bytes_obj):
    with open(filename, 'wb') as file:
        file.write(bytes_obj)
```


Struct
------

```python
from struct import pack, unpack

# Запакуем данные в формат: int, float, 5-символьную строку
binary_data = pack('if5s', 100, 3.14, b'world')

# Распакуем обратно
original_values = unpack('if5s', binary_data)
print(original_values)  # (100, 3.14, b'world')
```
Числовые типы
Формат	               Описание	                          Размер (байт)
c	               Один символ	                                1
b	             signed char (целое, -128 до 127)           	1
B	             unsigned char (целое, 0 до 255)	            1
?	             bool (логическое значение)	                    1
h	             short (signed, -32,768 до 32,767)	            2
H	             unsigned short (0 до 65,535)	                2
i	             int (signed, -2,147,483,648 до 2,147,483,647)	4
I	             unsigned int (0 до 4,294,967,295)	            4
q	             long long (signed)                         	8
Q	             unsigned long long                         	8
f	             float (число с плавающей точкой)	            4
d	             double (число с плавающей точкой)	            8
Другие форматы
s — строка, например 5s означает 5 символов (b'hello').
p — строка переменной длины с префиксом длины (например, pack('10p', b'hello')).
x — байт-заполнитель (пропускает байт).

```python
>>> pack('>hhl', 1, 2, 3)
b'\x00\x01\x00\x02\x00\x00\x00\x03'
>>> unpack('>hhl', b'\x00\x01\x00\x02\x00\x00\x00\x03')
(1, 2, 3)
```

Array
-----

```python
from array import array
```
Использует меньше памяти, чем список (list).
Позволяет работать с большими массивами чисел.
Поддерживает методы, похожие на список (append, remove, pop и др.).
```python
from array import array
# Создаем массив целых чисел ('i' означает int)
arr = array('i', [1, 2, 3, 4, 5])
# Выводим элементы
print(arr)  # array('i', [1, 2, 3, 4, 5])
# Добавляем элемент
arr.append(6)
print(arr)  # array('i', [1, 2, 3, 4, 5, 6])
# Доступ к элементам
print(arr[2])  # 3
# Изменяем значение
arr[2] = 10
print(arr)  # array('i', [1, 2, 10, 4, 5, 6])
# Удаляем элемент
arr.remove(4)
print(arr)  # array('i', [1, 2, 10, 5, 6])
```

```python
<bytes> = bytes(<array>)    # Возвращает копию памяти массива.
<file>.write(<array>)       # Записывает память массива в двоичный файл.
```


Memory View
-----------
```python
<mview> = memoryview(<bytes/bytearray/array>)        # Неизменяемый, если переданы байты, в противном случае изменяемый.
<obj> = <mview>[index]                               # Возвращает int или float. Bytes, если формат 'c'.
<mview> = <mview>[<slice>]                           # Возвращает memoryview с переупорядоченными элементами.
<mview> = <mview>.cast('<typecode>')                 # Работает только между B/b/c и другими типами.
<mview>.release()                                    # Освобождает буфер памяти базового объекта.
```

```python
<bytes> = bytes(<mview>)                 # Возвращает новый объект bytes. Также bytearray().
<bytes> = <bytes>.join(<coll_of_mviews>) # Объединяет memoryviews, используя bytes в качестве разделителя.
<array> = array('<typecode>', <mview>)   # Рассматривает memoryview как последовательность чисел.
<file>.write(<mview>)                    # Записывает `bytes(<mview>)` в двоичный файл.
```

```python
<list> = list(<mview>)        # Возвращает список целых чисел, чисел с плавающей точкой или байтов.
<str> = str(<mview>, 'utf-8') # Рассматривает memoryview как объект байтов.
<str> = <mview>.hex()         # Возвращает шестнадцатеричные пары. Принимает `sep=<str>`.
```


Deque
-----
**List with efficient appends and pops from either side.**

```python
from collections import deque
```

```python
<deque> = deque(<collection>)    # Используйте `maxlen=<int>` для установки ограничения размера.
<deque>.appendleft(<el>)         # Противоположный элемент отбрасывается, если заполнен.
<deque>.extendleft(<collection>) # Переданная коллекция переворачивается.
<deque>.rotate(n=1)              # Последний элемент становится первым.
<el> = <deque>.popleft()         # Вызывает IndexError, если deque пуст.
```


Operator
--------
```python
import operator as op
```

```python
<bool> = op.not_(<obj>)                                        # or, and, not (or/and missing)
<bool> = op.eq/ne/lt/ge/is_/is_not/contains(<obj>, <obj>)      # ==, !=, <, >=, is, is not, in
<obj>  = op.or_/xor/and_(<int/set>, <int/set>)                 # |, ^, &
<int>  = op.lshift/rshift(<int>, <int>)                        # <<, >>
<obj>  = op.add/sub/mul/truediv/floordiv/mod(<obj>, <obj>)     # +, -, *, /, //, %
<num>  = op.neg/invert(<num>)                                  # -, ~
<num>  = op.pow(<num>, <num>)                                  # **
<func> = op.itemgetter/attrgetter/methodcaller(<obj> [, ...])  # [index/key], .name, .name([…])
```

```python
elementwise_sum  = map(op.add, list_a, list_b)
sorted_by_second = sorted(<coll>, key=op.itemgetter(1))
sorted_by_both   = sorted(<coll>, key=op.itemgetter(1, 0))
first_element    = op.methodcaller('pop', 0)(<list>)
```

Match Statement
---------------

```python
match <object/expression>:
    case <pattern> [if <condition>]:
        <code>
    ...
```

### Patterns
```python
<value_pattern> = 1/'abc'/True/None/math.pi            # Соответствует литералу или имени с точкой.
<class_pattern> = <type>()                             # Соответствует любому объекту этого типа (или ABC).
<wildcard_patt> = _                                    # Соответствует любому объекту. Полезно в последнем случае.
<capture_pattern> = <name>                             # Соответствует любому объекту и привязывает его к имени.
<as_pattern> = <pattern> as <name>                     # Связывает соответствие с именем. Также <type>(<name>).
<or_pattern> = <pattern> | <pattern> [| ...]           # Соответствует любому из шаблонов.
<sequence_patt> = [<pattern>, ...]                     # Соответствует последовательности с соответствующими элементами.
<mapping_patt> = {<value_pattern>: <patt>, ...}        # Соответствует словарю с соответствующими элементами.
<class_pattern> = <type>(<attr_name>=<patt>, ...)      # Сопоставляет объект с соответствующими атрибутами.
```

### Example
```python
>>> from pathlib import Path
>>> match Path('/home/gto/python-cheatsheet/README.md'):
...     case Path(
...         parts=['/', 'home', user, *_]
...     ) as p if p.name.lower().startswith('readme') and p.is_file():
...         print(f'{p.name} is a readme file that belongs to user {user}.')
README.md is a readme file that belongs to user gto.
```


Logging
-------
```python
import logging as log
```

```python
log.basicConfig(filename=<path>, level='DEBUG')         # Настраивает корневой регистратор (см. Настройка).
log.debug/info/warning/error/critical(<str>)            # Отправляет сообщение корневому регистратору.
<Logger> = log.getLogger(__name__)                      # Возвращает регистратор, названный по имени модуля.
<Logger>.<level>(<str>)                                 # Отправляет сообщение регистратору.
<Logger>.exception(<str>)                               # Error(), который добавляет перехваченное исключение.
```

### Setup
```python
log.basicConfig(
    filename=None,                               # Регистрирует в stderr или добавляет в файл.
    format='%(levelname)s:%(name)s:%(message)s', # Добавляет '%(asctime)s' для локальной даты и времени.
    level=log.WARNING,                           # Отбрасывает сообщения с более низким приоритетом.
    handlers=[log.StreamHandler(sys.stderr)]     # Использует FileHandler, если задано filename.
)
```

```python
<Formatter> = log.Formatter('<format>')       # Создает Formatter.
<Handler> = log.FileHandler(<path>, mode='a') # Создает Handler. Также `encoding=None`.
<Handler>.setFormatter(<Formatter>)           # Добавляет Formatter к Handler.
<Handler>.setLevel(<int/str>)                 # Обрабатывает все сообщения по умолчанию.
<Logger>.addHandler(<Handler>)                # Добавляет Handler к Logger.
<Logger>.setLevel(<int/str>)                  # Что отправляется обработчикам его/предков.
<Logger>.propagate = <bool>                   # Отключает обработчики предков, если False.
```

#### Creates a logger that writes all messages to a file and sends them to the root's handler that prints warnings or higher:
```python
>>> logger = log.getLogger('my_module')
>>> handler = log.FileHandler('test.log', encoding='utf-8')
>>> handler.setFormatter(log.Formatter('%(asctime)s %(levelname)s:%(name)s:%(message)s'))
>>> logger.addHandler(handler)
>>> logger.setLevel('DEBUG')
>>> log.basicConfig()
>>> log.root.handlers[0].setLevel('WARNING')
>>> logger.critical('Running out of disk space.')
CRITICAL:my_module:Running out of disk space.
>>> print(open('test.log').read())
2023-02-07 23:21:01,430 CRITICAL:my_module:Running out of disk space.
```


Introspection
-------------
```python
<list> = dir()        # Локальные имена переменных, функций, классов и модулей.
<dict> = vars()       # Dict локальных имен и их объектов. Также locals().
<dict> = globals()    # Dict глобальных имен и их объектов, например __builtin__.
```

```python
<list> = dir(<obj>)                # Возвращает имена атрибутов объекта (включая методы).
<dict> = vars(<obj>)               # Возвращает словарь записываемых атрибутов. Также <obj>.__dict__.
<bool> = hasattr(<obj>, '<name>')  # Проверяет, обладает ли объект атрибутом с переданным именем.
value = getattr(<obj>, '<name>')   # Возвращает атрибут объекта или вызывает AttributeError.
setattr(<obj>, '<name>', value)    # Устанавливает атрибут. Работает только с объектами с атрибутом __dict__.
delattr(<obj>, '<name>')           # Удаляет атрибут из __dict__. Также `del <obj>.<name>`.
```

```python
<Sig> = inspect.signature(<func>)  # Возвращает объект Signature переданной функции.
<dict> = <Sig>.parameters          # Возвращает словарь параметров. Также <Sig>.return_annotation.
<memb> = <Param>.kind              # Возвращает член ParameterKind (Parameter.KEYWORD_ONLY, …).
<type> = <Param>.annotation        # Возвращает Parameter.empty, если отсутствует. Также <Param>.default.
```


Threading
---------
```python
from threading import Thread, Lock, RLock, Semaphore, Event, Barrier
from concurrent.futures import ThreadPoolExecutor, as_completed
```

### Thread
```python
<Thread> = Thread(target=<function>)           # Use `args=<collection>` to set the arguments.
<Thread>.start()                               # Starts the thread. Also <Thread>.is_alive().
<Thread>.join()                                # Waits for the thread to finish executing.
```
* **Use `'kwargs=<dict>'` to pass keyword arguments to the function.**
* **Use `'daemon=True'`, or the program won't be able to exit while the thread is alive.**

### Lock
```python
<lock> = Lock/RLock()                          # RLock can only be released by acquirer.
<lock>.acquire()                               # Waits for the lock to be available.
<lock>.release()                               # Makes the lock available again.
```

#### Or:
```python
with <lock>:                                   # Enters the block by calling acquire() and
    ...                                        # exits it with release(), even on error.
```

### Semaphore, Event, Barrier
```python
<Semaphore> = Semaphore(value=1)               # Lock that can be acquired by 'value' threads.
<Event>     = Event()                          # Method wait() blocks until set() is called.
<Barrier>   = Barrier(n_times)                 # Wait() blocks until it's called n times.
```

### Queue
```python
<Queue> = queue.Queue(maxsize=0)               # A thread-safe first-in-first-out queue.
<Queue>.put(<el>)                              # Blocks until queue stops being full.
<Queue>.put_nowait(<el>)                       # Raises queue.Full exception if full.
<el> = <Queue>.get()                           # Blocks until queue stops being empty.
<el> = <Queue>.get_nowait()                    # Raises queue.Empty exception if empty.
```

### Thread Pool Executor
```python
<Exec> = ThreadPoolExecutor(max_workers=None)  # Or: `with ThreadPoolExecutor() as <name>: ...`
<iter> = <Exec>.map(<func>, <args_1>, ...)     # Multithreaded and non-lazy map(). Keeps order.
<Futr> = <Exec>.submit(<func>, <arg_1>, ...)   # Creates a thread and returns its Future obj.
<Exec>.shutdown()                              # Waits for all submitted threads to finish.
```

```python
<bool> = <Future>.done()                       # Checks if the thread has finished executing.
<obj>  = <Future>.result(timeout=None)         # Waits for thread to finish and returns result.
<bool> = <Future>.cancel()                     # Cancels or returns False if running/finished.
<iter> = as_completed(<coll_of_Futures>)       # `next(<iter>)` returns next completed Future.
```
* **Map() and as\_completed() also accept 'timeout'. It causes futures.TimeoutError when next() is called/blocking. Map() times from original call and as_completed() from first call to next(). As\_completed() fails if next() is called too late, even if all threads are done.**
* **Exceptions that happen inside threads are raised when map iterator's next() or Future's result() are called. Future's exception() method returns exception object or None.**
* **ProcessPoolExecutor provides true parallelism but: everything sent to/from workers must be [pickable](#pickle), queues must be sent using executor's 'initargs' and 'initializer' parameters, and executor should only be reachable via `'if __name__ == "__main__": ...'`.**


Coroutines
----------
* **Coroutines have a lot in common with threads, but unlike threads, they only give up control when they call another coroutine and they don’t use as much memory.**
* **Coroutine definition starts with `'async'` and its call with `'await'`.**
* **Use `'asyncio.run(<coroutine>)'` to start the first/main coroutine.**

```python
import asyncio as aio
```

```python
<coro> = <async_function>(<args>)          # Creates a coroutine by calling async def function.
<obj>  = await <coroutine>                 # Starts the coroutine and returns its result.
<task> = aio.create_task(<coroutine>)      # Schedules the coroutine for execution.
<obj>  = await <task>                      # Returns coroutine's result. Also <task>.cancel().
```

```python
<coro> = aio.gather(<coro/task>, ...)      # Schedules coros. Returns list of results on await.
<coro> = aio.wait(<tasks>, return_when=…)  # `'ALL/FIRST_COMPLETED'`. Returns (done, pending).
<iter> = aio.as_completed(<coros/tasks>)   # Iter of coros that return next result on await.
```

#### Runs a terminal game where you control an asterisk that must avoid numbers:
```python
import asyncio, collections, curses, curses.textpad, enum, random

P = collections.namedtuple('P', 'x y')     # Position
D = enum.Enum('D', 'n e s w')              # Direction
W, H = 15, 7                               # Width, Height

def main(screen):
    curses.curs_set(0)                     # Makes cursor invisible.
    screen.nodelay(True)                   # Makes getch() non-blocking.
    asyncio.run(main_coroutine(screen))    # Starts running asyncio code.

async def main_coroutine(screen):
    moves = asyncio.Queue()
    state = {'*': P(0, 0)} | {id_: P(W//2, H//2) for id_ in range(10)}
    ai    = [random_controller(id_, moves) for id_ in range(10)]
    mvc   = [human_controller(screen, moves), model(moves, state), view(state, screen)]
    tasks = [asyncio.create_task(coro) for coro in ai + mvc]
    await asyncio.wait(tasks, return_when=asyncio.FIRST_COMPLETED)

async def random_controller(id_, moves):
    while True:
        d = random.choice(list(D))
        moves.put_nowait((id_, d))
        await asyncio.sleep(random.triangular(0.01, 0.65))

async def human_controller(screen, moves):
    while True:
        key_mappings = {258: D.s, 259: D.n, 260: D.w, 261: D.e}
        if d := key_mappings.get(screen.getch()):
            moves.put_nowait(('*', d))
        await asyncio.sleep(0.005)

async def model(moves, state):
    while state['*'] not in (state[id_] for id_ in range(10)):
        id_, d = await moves.get()
        deltas = {D.n: P(0, -1), D.e: P(1, 0), D.s: P(0, 1), D.w: P(-1, 0)}
        state[id_] = P((state[id_].x + deltas[d].x) % W, (state[id_].y + deltas[d].y) % H)

async def view(state, screen):
    offset = P(curses.COLS//2 - W//2, curses.LINES//2 - H//2)
    while True:
        screen.erase()
        curses.textpad.rectangle(screen, offset.y-1, offset.x-1, offset.y+H, offset.x+W)
        for id_, p in state.items():
            screen.addstr(offset.y + (p.y - state['*'].y + H//2) % H,
                          offset.x + (p.x - state['*'].x + W//2) % W, str(id_))
        screen.refresh()
        await asyncio.sleep(0.005)

if __name__ == '__main__':
    curses.wrapper(main)
```
<br>


Libraries
=========

Progress Bar
------------
```python
# $ pip3 install tqdm
>>> import tqdm, time
>>> for el in tqdm.tqdm([1, 2, 3], desc='Processing'):
...     time.sleep(1)
Processing: 100%|████████████████████| 3/3 [00:03<00:00,  1.00s/it]
```


Plot
----
```python
# $ pip3 install matplotlib
import matplotlib.pyplot as plt

plt.plot/bar/scatter(x_data, y_data [, label=<str>])  # Also plt.plot(y_data).
plt.legend()                                          # Adds a legend.
plt.title/xlabel/ylabel(<str>)                        # Adds a title or label.
plt.show()                                            # Also plt.savefig(<path>).
plt.clf()                                             # Clears the plot.
```


Table
-----
#### Prints a CSV spreadsheet to the console:
```python
# $ pip3 install tabulate
import csv, tabulate
with open('test.csv', encoding='utf-8', newline='') as file:
    rows = list(csv.reader(file))
print(tabulate.tabulate(rows, headers='firstrow'))
```


Console App
-----------
#### Runs a basic file explorer in the console:
```python
# $ pip3 install windows-curses
import curses, os
from curses import A_REVERSE, KEY_UP, KEY_DOWN, KEY_LEFT, KEY_RIGHT

def main(screen):
    ch, first, selected, paths = 0, 0, 0, os.listdir()
    while ch != ord('q'):
        height, width = screen.getmaxyx()
        screen.erase()
        for y, filename in enumerate(paths[first : first+height]):
            color = A_REVERSE if filename == paths[selected] else 0
            screen.addnstr(y, 0, filename, width-1, color)
        ch = screen.getch()
        selected -= (ch == KEY_UP) and (selected > 0)
        selected += (ch == KEY_DOWN) and (selected < len(paths)-1)
        first -= (first > selected)
        first += (first < selected-(height-1))
        if ch in [KEY_LEFT, KEY_RIGHT, ord('\n')]:
            new_dir = '..' if ch == KEY_LEFT else paths[selected]
            if os.path.isdir(new_dir):
                os.chdir(new_dir)
                first, selected, paths = 0, 0, os.listdir()

if __name__ == '__main__':
    curses.wrapper(main)
```


GUI App
-------
#### A weight converter GUI application:

```python
# $ pip3 install PySimpleGUI
import PySimpleGUI as sg

text_box = sg.Input(default_text='100', enable_events=True, key='QUANTITY')
dropdown = sg.InputCombo(['g', 'kg', 't'], 'kg', readonly=True, enable_events=True, k='UNIT')
label    = sg.Text('100 kg is 220.462 lbs.', key='OUTPUT')
button   = sg.Button('Close')
window   = sg.Window('Weight Converter', [[text_box, dropdown], [label], [button]])

while True:
    event, values = window.read()
    if event in [sg.WIN_CLOSED, 'Close']:
        break
    try:
        quantity = float(values['QUANTITY'])
    except ValueError:
        continue
    unit = values['UNIT']
    factors = {'g': 0.001, 'kg': 1, 't': 1000}
    lbs = quantity * factors[unit] / 0.45359237
    window['OUTPUT'].update(value=f'{quantity} {unit} is {lbs:g} lbs.')
window.close()
```


Scraping
--------
#### Scrapes Python's URL and logo from its Wikipedia page:
```python
# $ pip3 install requests beautifulsoup4
import requests, bs4, os

response   = requests.get('https://en.wikipedia.org/wiki/Python_(programming_language)')
document   = bs4.BeautifulSoup(response.text, 'html.parser')
table      = document.find('table', class_='infobox vevent')
python_url = table.find('th', text='Website').next_sibling.a['href']
logo_url   = table.find('img')['src']
filename   = os.path.basename(logo_url)
with open(filename, 'wb') as file:
    file.write(requests.get(f'https:{logo_url}').content)
print(f'{python_url}, file://{os.path.abspath(filename)}')
```

### Selenium
**Library for scraping websites with dynamic content.**
```python
# $ pip3 install selenium
from selenium import webdriver

<WebDrv> = webdriver.Chrome/Firefox/Safari/Edge()     # Opens a browser. Also <WebDrv>.quit().
<WebDrv>.get('<url>')                                 # Also <WebDrv>.implicitly_wait(seconds).
<str>  = <WebDrv>.page_source                         # Returns HTML of fully rendered page.
<El>   = <WebDrv/El>.find_element('css selector', …)  # '<tag>#<id>.<class>[<attr>="<val>"]…'.
<list> = <WebDrv/El>.find_elements('xpath', …)        # '//<tag>[@<attr>="<val>"]…'. See XPath.
<str>  = <El>.get_attribute(<str>)                    # Property if exists. Also <El>.text.
<El>.click/clear()                                    # Also <El>.send_keys(<str>).
```

#### XPath — also available in lxml, Scrapy, and browser's console via `'$x("<xpath>")'`:
```python
<xpath>     = //<element>[/ or // <element>]          # /<child>, //<descendant>, /../<sibling>
<xpath>     = //<element>/following::<element>        # Next element. Also preceding/parent/…
<element>   = <tag><conditions><index>                # `<tag> = */a/…`, `<index> = [1/2/…]`.
<condition> = [<sub_cond> [and/or <sub_cond>]]        # For negation use `not(<sub_cond>)`.
<sub_cond>  = @<attr>[="<val>"]                       # `text()=`, `.=` match (complete) text.
<sub_cond>  = contains(@<attr>, "<val>")              # Is <val> a substring of attr's value?
<sub_cond>  = [//]<element>                           # Has matching child? Descendant if //.
```


Web App
-------
**Flask is a micro web framework/server. If you just want to open a html file in a web browser use `'webbrowser.open(<path>)'` instead.**
```python
# $ pip3 install flask
import flask as fl
```

```python
app = fl.Flask(__name__)                   # Returns the app object. Put at the top.
app.run(host=None, port=None, debug=None)  # Or: $ flask --app FILE run [--ARG[=VAL]]…
```
* **Starts the app at `'http://localhost:5000'`. Use `'host="0.0.0.0"'` to run externally.**
* **Install a WSGI server like [Waitress](https://flask.palletsprojects.com/en/latest/deploying/waitress/) and a HTTP server such as [Nginx](https://flask.palletsprojects.com/en/latest/deploying/nginx/) for better security.**
* **Debug mode restarts the app whenever script changes and displays errors in the browser.**

### Serving Files
```python
@app.route('/img/<path:filename>')
def serve_file(filename):
    return fl.send_from_directory('DIRNAME', filename)
```

### Serving HTML
```python
@app.route('/<sport>')
def serve_html(sport):
    return fl.render_template_string('<h1>{{title}}</h1>', title=sport)
```
* **`'fl.render_template(filename, <kwargs>)'` renders a file located in 'templates' dir.**
* **`'fl.abort(<int>)'` returns error code and `'return fl.redirect(<url>)'` redirects.**
* **`'fl.request.args[<str>]'` returns parameter from query string (URL part right of '?').**
* **`'fl.session[<str>] = <obj>'` stores session data. It requires secret key to be set at the startup with `'app.secret_key = <str>'`.**

### Serving JSON
```python
@app.post('/<sport>/odds')
def serve_json(sport):
    team = fl.request.form['team']
    return {'team': team, 'odds': [2.09, 3.74, 3.68]}
```

#### Starts the app in its own thread and queries its REST API:
```python
# $ pip3 install requests
>>> import threading, requests
>>> threading.Thread(target=app.run, daemon=True).start()
>>> url = 'http://localhost:5000/football/odds'
>>> response = requests.post(url, data={'team': 'arsenal f.c.'})
>>> response.json()
{'team': 'arsenal f.c.', 'odds': [2.09, 3.74, 3.68]}
```


Profiling
---------

```python
from time import perf_counter
start_time = perf_counter()
...
duration_in_seconds = perf_counter() - start_time
```

### Timing a Snippet
```python
>>> from timeit import timeit
>>> timeit('list(range(10000))', number=1000, globals=globals(), setup='pass')
0.19373
```

### Profiling by Line
```text
$ pip3 install line_profiler
$ echo '@profile
def main():
    a = list(range(10000))
    b = set(range(10000))
main()' > test.py
$ kernprof -lv test.py
Line #      Hits         Time  Per Hit   % Time  Line Contents
==============================================================
     1                                           @profile
     2                                           def main():
     3         1        253.4    253.4     32.2      a = list(range(10000))
     4         1        534.1    534.1     67.8      b = set(range(10000))
```

### Call and Flame Graphs
```bash
$ apt/brew install graphviz && pip3 install gprof2dot snakeviz  # Or download installer.
$ tail --lines=+2 test.py > test.py                             # Removes first line.
$ python3 -m cProfile -o test.prof test.py                      # Runs built-in profiler.
$ gprof2dot --format=pstats test.prof | dot -T png -o test.png  # Generates call graph.
$ xdg-open/open test.png                                        # Displays call graph.
$ snakeviz test.prof                                            # Displays flame graph.
```

### Sampling and Memory Profilers
```text
+--------------+------------+-------------------------------+-------+------+
| pip3 install |   Target   |          How to run           | Lines | Live |
+--------------+------------+-------------------------------+-------+------+
| pyinstrument |    CPU     | pyinstrument test.py          |  No   | No   |
| py-spy       |    CPU     | py-spy top -- python3 test.py |  No   | Yes  |
| scalene      | CPU+Memory | scalene test.py               |  Yes  | No   |
| memray       |   Memory   | memray run --live test.py     |  Yes  | Yes  |
+--------------+------------+-------------------------------+-------+------+
```


NumPy
-----
**Array manipulation mini-language. It can run up to one hundred times faster than the equivalent Python code. An even faster alternative that runs on a GPU is called CuPy.**

```python
# $ pip3 install numpy
import numpy as np
```

```python
<array> = np.array(<list/list_of_lists/…>)              # Returns a 1d/2d/… NumPy array.
<array> = np.zeros/ones/empty(<shape>)                  # Also np.full(<shape>, <el>).
<array> = np.arange(from_inc, to_exc, ±step)            # Also np.linspace(start, stop, len).
<array> = np.random.randint(from_inc, to_exc, <shape>)  # Also np.random.random(<shape>).
```

```python
<view>  = <array>.reshape(<shape>)                      # Also `<array>.shape = <shape>`.
<array> = <array>.flatten()                             # Also `<view> = <array>.ravel()`.
<view>  = <array>.transpose()                           # Or: <array>.T
```

```python
<array> = np.copy/abs/sqrt/log/int64(<array>)           # Returns new array of the same shape.
<array> = <array>.sum/max/mean/argmax/all(axis)         # Aggregates specified dimension.
<array> = np.apply_along_axis(<func>, axis, <array>)    # Func can return a scalar or array.
```

```python
<array> = np.concatenate(<list_of_arrays>, axis=0)      # Links arrays along first axis (rows).
<array> = np.vstack/column_stack(<list_of_arrays>)      # Treats 1d arrays as rows or columns.
<array> = np.tile/repeat(<array>, <int/list> [, axis])  # Tiles array or repeats its elements.
```
* **Shape is a tuple of dimension sizes. A 100x50 RGB image has shape (50, 100, 3).**
* **Axis is an index of a dimension. Leftmost dimension has index 0. Summing the RGB image along axis 2 will return a greyscale image with shape (50, 100).**

### Indexing
```perl
<el>       = <2d>[row_index, col_index]                 # Or: <3d>[<int>, <int>, <int>]
<1d_view>  = <2d>[row_index]                            # Or: <3d>[<int>, <int>, <slice>]
<1d_view>  = <2d>[:, col_index]                         # Or: <3d>[<int>, <slice>, <int>]
<2d_view>  = <2d>[from:to_row_i, from:to_col_i]         # Or: <3d>[<int>, <slice>, <slice>]
```

```perl
<1d_array> = <2d>[row_indices, col_indices]             # Or: <3d>[<int/1d>, <1d>, <1d>]
<2d_array> = <2d>[row_indices]                          # Or: <3d>[<int/1d>, <1d>, <slice>]
<2d_array> = <2d>[:, col_indices]                       # Or: <3d>[<int/1d>, <slice>, <1d>]
<2d_array> = <2d>[np.ix_(row_indices, col_indices)]     # Or: <3d>[<int/1d/2d>, <2d>, <2d>]
```

```perl
<2d_bools> = <2d> > <el/1d/2d>                          # 1d object must have size of a row.
<1/2d_arr> = <2d>[<2d/1d_bools>]                        # 1d_bools must have size of a column.
```
* **`':'` returns a slice of all dimension's indices. Omitted dimensions default to `':'`.**
* **Python converts `'obj[i, j]'` to `'obj[(i, j)]'`. This makes `'<2d>[row_i, col_i]'` and `'<2d>[row_indices]'` indistinguishable to NumPy if tuple of two indices is passed!**
* **`'ix_([1, 2], [3, 4])'` returns `'[[1], [2]]'` and `'[[3, 4]]'`. Due to broadcasting rules, this is the same as using `'[[1, 1], [2, 2]]'` and `'[[3, 4], [3, 4]]'`.**
* **Any value that is broadcastable to the indexed shape can be assigned to the selection.**

### Broadcasting
**A set of rules by which NumPy functions operate on arrays of different shapes.**
```python
left  = np.array([0.1,  0.6,  0.8])                     # `left.shape  == (3,)`
right = np.array([[0.1], [0.6], [0.8]])                 # `right.shape == (3, 1)`
```

#### 1. If array shapes differ in length, left-pad the shorter shape with ones:
```python
left  = np.array([[0.1,  0.6,  0.8]])                   # `left.shape  == (1, 3)`
right = np.array([[0.1], [0.6], [0.8]])                 # `right.shape == (3, 1)`
```

#### 2. If any dimensions differ in size, expand the ones that have size 1 by duplicating their elements:
```python
left  = np.array([[0.1,  0.6,  0.8],                    # `left.shape  == (3, 3)`
                  [0.1,  0.6,  0.8],
                  [0.1,  0.6,  0.8]])

right = np.array([[0.1,  0.1,  0.1],                    # `right.shape == (3, 3)`
                  [0.6,  0.6,  0.6],
                  [0.8,  0.8,  0.8]])
```

### Example
#### For each point returns index of its nearest point (`[0.1, 0.6, 0.8] => [1, 2, 1]`):

```python
>>> print(points := np.array([0.1, 0.6, 0.8]))
[0.1  0.6  0.8]
>>> print(wrapped_points := points.reshape(3, 1))
[[0.1]
 [0.6]
 [0.8]]
>>> print(deltas := points - wrapped_points)
[[ 0.   0.5  0.7]
 [-0.5  0.   0.2]
 [-0.7 -0.2  0. ]]
>>> deltas[range(3), range(3)] = np.inf
>>> print(distances := np.abs(deltas))
[[inf  0.5  0.7]
 [0.5  inf  0.2]
 [0.7  0.2  inf]]
>>> print(distances.argmin(axis=1))
[1 2 1]
```


Image
-----
```python
# $ pip3 install pillow
from PIL import Image
```

```python
<Image> = Image.new('<mode>', (width, height))  # Creates new image. Also `color=<int/tuple>`.
<Image> = Image.open(<path>)                    # Identifies format based on file's contents.
<Image> = <Image>.convert('<mode>')             # Converts image to the new mode (see Modes).
<Image>.save(<path>)                            # Selects format based on extension (PNG/JPG…).
<Image>.show()                                  # Displays image in default preview app.
```

```python
<int/tup> = <Image>.getpixel((x, y))            # Returns pixel's value (its color).
<ImgCore> = <Image>.getdata()                   # Returns a flattened view of pixel values.
<Image>.putpixel((x, y), <int/tuple>)           # Updates pixel's value. Clips passed int/s.
<Image>.putdata(<list/ImgCore>)                 # Updates pixels with a copy of the sequence.
<Image>.paste(<Image>, (x, y))                  # Draws passed image at the specified location.
```

```python
<Image> = <Image>.filter(<Filter>)              # Use ImageFilter.<name>(<args>) for Filter.
<Image> = <Enhance>.enhance(<float>)            # Use ImageEnhance.<name>(<Image>) for Enhance.
```

```python
<array> = np.array(<Image>)                     # Creates a 2d/3d NumPy array from the image.
<Image> = Image.fromarray(np.uint8(<array>))    # Use <array>.clip(0, 255) to clip the values.
```

### Modes
* **`'L'` - Lightness (greyscale image). Each pixel is an int between 0 and 255.**
* **`'RGB'` - Red, green, blue (true color image). Each pixel is a tuple of three ints.**
* **`'RGBA'` - RGB with alpha. Low alpha (i.e. forth int) makes pixel more transparent.**
* **`'HSV'` - Hue, saturation, value. Three ints representing color in HSV color space.**


### Examples
#### Creates a PNG image of a rainbow gradient:
```python
WIDTH, HEIGHT = 100, 100
n_pixels = WIDTH * HEIGHT
hues = (255 * i/n_pixels for i in range(n_pixels))
img = Image.new('HSV', (WIDTH, HEIGHT))
img.putdata([(int(h), 255, 255) for h in hues])
img.convert('RGB').save('test.png')
```

#### Adds noise to the PNG image and displays it:
```python
from random import randint
add_noise = lambda value: max(0, min(255, value + randint(-20, 20)))
img = Image.open('test.png').convert('HSV')
img.putdata([(add_noise(h), s, v) for h, s, v in img.getdata()])
img.show()
```

### Image Draw
```python
from PIL import ImageDraw
<Draw> = ImageDraw.Draw(<Image>)                # Object for adding 2D graphics to the image.
<Draw>.point((x, y))                            # Draws a point. Also `fill=<int/tuple/str>`.
<Draw>.line((x1, y1, x2, y2 [, ...]))           # For anti-aliasing use <Image>.resize((w, h)).
<Draw>.arc((x1, y1, x2, y2), deg1, deg2)        # Draws in clockwise dir. Also pieslice().
<Draw>.rectangle((x1, y1, x2, y2))              # Also rounded_rectangle(), regular_polygon().
<Draw>.polygon((x1, y1, x2, y2, ...))           # Last point gets connected to the first one.
<Draw>.ellipse((x1, y1, x2, y2))                # To rotate use <Image>.rotate(anticlock_deg).
<Draw>.text((x, y), <str>, font=<Font>)         # `<Font> = ImageFont.truetype(<path>, size)`.
```
* **Use `'fill=<color>'` to set the primary color.**
* **Use `'width=<int>'` to set the width of lines or contours.**
* **Use `'outline=<color>'` to set the color of the contours.**
* **Color can be an int, tuple, `'#rrggbb[aa]'` or a color name.**


Animation
---------
#### Creates a GIF of a bouncing ball:
```python
# $ pip3 install imageio
from PIL import Image, ImageDraw
import imageio

WIDTH, HEIGHT, R = 126, 126, 10
frames = []
for velocity in range(1, 16):
    y = sum(range(velocity))
    frame = Image.new('L', (WIDTH, HEIGHT))
    draw = ImageDraw.Draw(frame)
    draw.ellipse((WIDTH/2-R, y, WIDTH/2+R, y+R*2), fill='white')
    frames.append(frame)
frames += reversed(frames[1:-1])
imageio.mimsave('test.gif', frames, duration=0.03)
```


Audio
-----
```python
import wave
```

```python
<Wave>  = wave.open('<path>')         # Opens the WAV file for reading.
<int>   = <Wave>.getframerate()       # Returns number of frames per second.
<int>   = <Wave>.getnchannels()       # Returns number of samples per frame.
<int>   = <Wave>.getsampwidth()       # Returns number of bytes per sample.
<tuple> = <Wave>.getparams()          # Returns namedtuple of all parameters.
<bytes> = <Wave>.readframes(nframes)  # Returns all frames if -1 is passed.
```

```python
<Wave> = wave.open('<path>', 'wb')    # Creates/truncates a file for writing.
<Wave>.setframerate(<int>)            # Pass 44100 for CD, 48000 for video.
<Wave>.setnchannels(<int>)            # Pass 1 for mono, 2 for stereo.
<Wave>.setsampwidth(<int>)            # Pass 2 for CD, 3 for hi-res sound.
<Wave>.setparams(<tuple>)             # Tuple must contain all parameters.
<Wave>.writeframes(<bytes>)           # Appends frames to the file.
```
* **Bytes object contains a sequence of frames, each consisting of one or more samples.**
* **In a stereo signal, the first sample of a frame belongs to the left channel.**
* **Each sample consists of one or more bytes that, when converted to an integer, indicate the displacement of a speaker membrane at a given moment.**
* **If sample width is one byte, then the integer should be encoded unsigned. For all other sizes, the integer should be encoded signed with little-endian byte order.**

### Sample Values
```text
+-----------+-----------+------+-----------+
| sampwidth |    min    | zero |    max    |
+-----------+-----------+------+-----------+
|     1     |         0 |  128 |       255 |
|     2     |    -32768 |    0 |     32767 |
|     3     |  -8388608 |    0 |   8388607 |
+-----------+-----------+------+-----------+
```

### Read Float Samples from WAV File
```python
def read_wav_file(filename):
    def get_int(bytes_obj):
        an_int = int.from_bytes(bytes_obj, 'little', signed=(p.sampwidth != 1))
        return an_int - 128 * (p.sampwidth == 1)
    with wave.open(filename) as file:
        p = file.getparams()
        frames = file.readframes(-1)
    bytes_samples = (frames[i : i + p.sampwidth] for i in range(0, len(frames), p.sampwidth))
    return [get_int(b) / pow(2, (p.sampwidth * 8) - 1) for b in bytes_samples], p
```

### Write Float Samples to WAV File
```python
def write_to_wav_file(filename, samples_f, p=None, nchannels=1, sampwidth=2, framerate=44100):
    def get_bytes(a_float):
        a_float = max(-1, min(1 - 2e-16, a_float))
        a_float += (p.sampwidth == 1)
        a_float *= pow(2, (p.sampwidth * 8) - 1)
        return int(a_float).to_bytes(p.sampwidth, 'little', signed=(p.sampwidth != 1))
    if p is None:
        p = wave._wave_params(nchannels, sampwidth, framerate, 0, 'NONE', 'not compressed')
    with wave.open(filename, 'wb') as file:
        file.setparams(p)
        file.writeframes(b''.join(get_bytes(f) for f in samples_f))
```

### Examples
#### Saves a 440 Hz sine wave to a mono WAV file:
```python
from math import pi, sin
samples_f = (sin(i * 2 * pi * 440 / 44100) for i in range(100_000))
write_to_wav_file('test.wav', samples_f)
```

#### Adds noise to the WAV file:
```python
from random import uniform
samples_f, params = read_wav_file('test.wav')
samples_f = (f + uniform(-0.05, 0.05) for f in samples_f)
write_to_wav_file('test.wav', samples_f, p=params)
```

#### Plays the WAV file:
```python
# $ pip3 install simpleaudio
from simpleaudio import play_buffer
with wave.open('test.wav') as file:
    frames, p = file.readframes(-1), file.getparams()
    play_buffer(frames, p.nchannels, p.sampwidth, p.framerate).wait_done()
```

### Text to Speech
```python
# $ pip3 install pyttsx3
import pyttsx3
engine = pyttsx3.init()
engine.say('Sally sells seashells by the seashore.')
engine.runAndWait()
```


Synthesizer
-----------
#### Plays Popcorn by Gershon Kingsley:
```python
# $ pip3 install simpleaudio
import itertools as it, math, array, simpleaudio

def play_notes(notes, bpm=132, f=44100):
    get_pause   = lambda n_beats: it.repeat(0, int(n_beats * 60/bpm * f))
    sin_f       = lambda i, hz: math.sin(i * 2 * math.pi * hz / f)
    get_wave    = lambda hz, n_beats: (sin_f(i, hz) for i in range(int(n_beats * 60/bpm * f)))
    get_hz      = lambda note: 440 * 2 ** ((int(note[:2]) - 69) / 12)
    get_nbeats  = lambda note: 1/2 if '♩' in note else 1/4 if '♪' in note else 1
    get_samples = lambda n: get_wave(get_hz(n), get_nbeats(n)) if n else get_pause(1/4)
    samples_f   = it.chain.from_iterable(get_samples(n) for n in notes.split(','))
    samples_i   = array.array('h', (int(fl * 5000) for fl in samples_f))
    simpleaudio.play_buffer(samples_i, 1, 2, f).wait_done()

play_notes('83♩,81♪,,83♪,,78♪,,74♪,,78♪,,71♪,,,,83♪,,81♪,,83♪,,78♪,,74♪,,78♪,,71♪,,,,'
           '83♩,85♪,,86♪,,85♪,,86♪,,83♪,,85♩,83♪,,85♪,,81♪,,83♪,,81♪,,83♪,,79♪,,83♪,,,,')
```


Pygame
------
#### Opes a window and draws a square that can be moved with arrow keys:
```python
# $ pip3 install pygame
import pygame as pg

pg.init()
screen = pg.display.set_mode((500, 500))
rect = pg.Rect(240, 240, 20, 20)
while not pg.event.get(pg.QUIT):
    deltas = {pg.K_UP: (0, -1), pg.K_RIGHT: (1, 0), pg.K_DOWN: (0, 1), pg.K_LEFT: (-1, 0)}
    for event in pg.event.get(pg.KEYDOWN):
        x, y = deltas.get(event.key, (0, 0))
        rect = rect.move((x*20, y*20))
    screen.fill(pg.Color('black'))
    pg.draw.rect(screen, pg.Color('white'), rect)
    pg.display.flip()
pg.quit()
```

### Rect
**Object for storing rectangular coordinates.**
```python
<Rect> = pg.Rect(x, y, width, height)           # Creates Rect object. Truncates passed floats.
<int>  = <Rect>.x/y/centerx/centery/…           # `top/right/bottom/left`. Allows assignments.
<tup.> = <Rect>.topleft/center/…                # `topright/bottomright/bottomleft`. Same.
<Rect> = <Rect>.move((delta_x, delta_y))        # Use move_ip() to move in-place.
```

```python
<bool> = <Rect>.collidepoint((x, y))            # Checks if rectangle contains the point.
<bool> = <Rect>.colliderect(<Rect>)             # Checks if the two rectangles overlap.
<int>  = <Rect>.collidelist(<list_of_Rect>)     # Returns index of first colliding Rect or -1.
<list> = <Rect>.collidelistall(<list_of_Rect>)  # Returns indices of all colliding rectangles.
```

### Surface
**Object for representing images.**
```python
<Surf> = pg.display.set_mode((width, height))   # Opens new window and returns its surface.
<Surf> = pg.Surface((width, height))            # New RGB surface. RGBA if `flags=pg.SRCALPHA`.
<Surf> = pg.image.load(<path/file>)             # Loads the image. Format depends on source.
<Surf> = pg.surfarray.make_surface(<np_array>)  # Also `<np_arr> = surfarray.pixels3d(<Surf>)`.
<Surf> = <Surf>.subsurface(<Rect>)              # Creates a new surface from the cutout.
```

```python
<Surf>.fill(color)                              # Pass tuple of ints or pg.Color('<name/hex>').
<Surf>.set_at((x, y), color)                    # Updates pixel. Also <Surf>.get_at((x, y)).
<Surf>.blit(<Surf>, (x, y))                     # Draws passed surface at specified location.
```

```python
from pygame.transform import scale, ...
<Surf> = scale(<Surf>, (width, height))         # Returns scaled surface.
<Surf> = rotate(<Surf>, anticlock_degrees)      # Returns rotated and scaled surface.
<Surf> = flip(<Surf>, x_bool, y_bool)           # Returns flipped surface.
```

```python
from pygame.draw import line, ...
line(<Surf>, color, (x1, y1), (x2, y2), width)  # Draws a line to the surface.
arc(<Surf>, color, <Rect>, from_rad, to_rad)    # Also ellipse(<Surf>, color, <Rect>, width=0).
rect(<Surf>, color, <Rect>, width=0)            # Also polygon(<Surf>, color, points, width=0).
```

```python
<Font> = pg.font.Font(<path/file>, size)        # Loads TTF file. Pass None for default font.
<Surf> = <Font>.render(text, antialias, color)  # Accepts background color as fourth argument.
```

### Sound
```python
<Sound> = pg.mixer.Sound(<path/file/bytes>)     # WAV file or bytes/array of signed shorts.
<Sound>.play/stop()                             # Also set_volume(<float>) and fadeout(msec).
```

### Basic Mario Brothers Example
```python
import collections, dataclasses, enum, io, itertools as it, pygame as pg, urllib.request
from random import randint

P = collections.namedtuple('P', 'x y')          # Position
D = enum.Enum('D', 'n e s w')                   # Direction
W, H, MAX_S = 50, 50, P(5, 10)                  # Width, Height, Max speed

def main():
    def get_screen():
        pg.init()
        return pg.display.set_mode((W*16, H*16))
    def get_images():
        url = 'https://gto76.github.io/python-cheatsheet/web/mario_bros.png'
        img = pg.image.load(io.BytesIO(urllib.request.urlopen(url).read()))
        return [img.subsurface(get_rect(x, 0)) for x in range(img.get_width() // 16)]
    def get_mario():
        Mario = dataclasses.make_dataclass('Mario', 'rect spd facing_left frame_cycle'.split())
        return Mario(get_rect(1, 1), P(0, 0), False, it.cycle(range(3)))
    def get_tiles():
        border = [(x, y) for x in range(W) for y in range(H) if x in [0, W-1] or y in [0, H-1]]
        platforms = [(randint(1, W-2), randint(2, H-2)) for _ in range(W*H // 10)]
        return [get_rect(x, y) for x, y in border + platforms]
    def get_rect(x, y):
        return pg.Rect(x*16, y*16, 16, 16)
    run(get_screen(), get_images(), get_mario(), get_tiles())

def run(screen, images, mario, tiles):
    clock = pg.time.Clock()
    pressed = set()
    while not pg.event.get(pg.QUIT):
        clock.tick(28)
        pressed |= {e.key for e in pg.event.get(pg.KEYDOWN)}
        pressed -= {e.key for e in pg.event.get(pg.KEYUP)}
        update_speed(mario, tiles, pressed)
        update_position(mario, tiles)
        draw(screen, images, mario, tiles)

def update_speed(mario, tiles, pressed):
    x, y = mario.spd
    x += 2 * ((pg.K_RIGHT in pressed) - (pg.K_LEFT in pressed))
    x += (x < 0) - (x > 0)
    y += 1 if D.s not in get_boundaries(mario.rect, tiles) else (pg.K_UP in pressed) * -10
    mario.spd = P(x=max(-MAX_S.x, min(MAX_S.x, x)), y=max(-MAX_S.y, min(MAX_S.y, y)))

def update_position(mario, tiles):
    x, y = mario.rect.topleft
    n_steps = max(abs(s) for s in mario.spd)
    for _ in range(n_steps):
        mario.spd = stop_on_collision(mario.spd, get_boundaries(mario.rect, tiles))
        x, y = x + (mario.spd.x / n_steps), y + (mario.spd.y / n_steps)
        mario.rect.topleft = x, y

def get_boundaries(rect, tiles):
    deltas = {D.n: P(0, -1), D.e: P(1, 0), D.s: P(0, 1), D.w: P(-1, 0)}
    return {d for d, delta in deltas.items() if rect.move(delta).collidelist(tiles) != -1}

def stop_on_collision(spd, bounds):
    return P(x=0 if (D.w in bounds and spd.x < 0) or (D.e in bounds and spd.x > 0) else spd.x,
             y=0 if (D.n in bounds and spd.y < 0) or (D.s in bounds and spd.y > 0) else spd.y)

def draw(screen, images, mario, tiles):
    screen.fill((85, 168, 255))
    mario.facing_left = mario.spd.x < 0 if mario.spd.x else mario.facing_left
    is_airborne = D.s not in get_boundaries(mario.rect, tiles)
    image_index = 4 if is_airborne else next(mario.frame_cycle) if mario.spd.x else 6
    screen.blit(images[image_index + (mario.facing_left * 9)], mario.rect)
    for t in tiles:
        is_border = t.x in [0, (W-1)*16] or t.y in [0, (H-1)*16]
        screen.blit(images[18 if is_border else 19], t)
    pg.display.flip()

if __name__ == '__main__':
    main()
```


Pandas
------
**Data analysis library. For examples see [Plotly](#plotly).**

```python
# $ pip3 install pandas matplotlib
import pandas as pd, matplotlib.pyplot as plt
```

### Series
**Ordered dictionary with a name.**

```python
>>> s = pd.Series([1, 2], index=['x', 'y'], name='a'); s
x    1
y    2
Name: a, dtype: int64
```

```python
<S>  = pd.Series(<list>)                       # Uses list's indices for 'index'.
<S>  = pd.Series(<dict>)                       # Uses dictionary's keys for 'index'.
```

```python
<el> = <S>.loc[key]                            # Or: <S>.iloc[i]
<S>  = <S>.loc[coll_of_keys]                   # Or: <S>.iloc[coll_of_i]
<S>  = <S>.loc[from_key : to_key_inc]          # Or: <S>.iloc[from_i : to_i_exc]
```

```python
<el> = <S>[key/i]                              # Or: <S>.<key>
<S>  = <S>[coll_of_keys/coll_of_i]             # Or: <S>[key/i : key/i]
<S>  = <S>[<S_of_bools>]                       # Or: <S>.loc/iloc[<S_of_bools>]
```

```python
<S>  = <S> > <el/S>                            # Returns S of bools. For logic use &, |, ~.
<S>  = <S> + <el/S>                            # Items with non-matching keys get value NaN.
```

```python
<S>  = <S>.head/describe/sort_values()         # Also <S>.unique/value_counts/round/dropna().
<S>  = <S>.str.strip/lower/contains/replace()  # Also split().str[i] or split(expand=True).
<S>  = <S>.dt.year/month/day/hour              # Use pd.to_datetime(<S>) to get S of datetimes.
<S>  = <S>.dt.to_period('y/m/d/h')             # Quantizes datetimes into Period objects.
```

```python
<S>.plot.line/area/bar/pie/hist()              # Generates a plot. Accepts `title=<str>`.
plt.show()                                     # Displays the plot. Also plt.savefig(<path>).
```
* **Use `'print(<S>.to_string())'` to print a Series that has more than 60 items.**
* **Use `'<S>.index'` to get collection of keys and `'<S>.index = <coll>'` to update them.**
* **Only pass a list or Series to loc/iloc because `'obj[x, y]'` is converted to `'obj[(x, y)]'` and `'<S>.loc[key_1, key_2]'` is how you retrieve a value from a multi-indexed Series.**
* **Pandas uses NumPy types like `'np.int64'`. Series is converted to `'float64'` if we assign np.nan to any item. Use `'<S>.astype(<str/type>)'` to get converted Series.**

#### Series — Aggregate, Transform, Map:
```python
<el> = <S>.sum/max/mean/std/idxmax/count()     # Or: <S>.agg(lambda <S>: <el>)
<S>  = <S>.rank/diff/cumsum/ffill/interpol…()  # Or: <S>.agg/transform(lambda <S>: <S>)
<S>  = <S>.isna/fillna/isin([<el/coll>])       # Or: <S>.agg/transform/map(lambda <el>: <el>)
```

```text
+--------------+-------------+-------------+---------------+
|              |    'sum'    |   ['sum']   | {'s': 'sum'}  |
+--------------+-------------+-------------+---------------+
| s.apply(…)   |      3      |    sum  3   |     s  3      |
| s.agg(…)     |             |             |               |
+--------------+-------------+-------------+---------------+
```

```text
+--------------+-------------+-------------+---------------+
|              |    'rank'   |   ['rank']  | {'r': 'rank'} |
+--------------+-------------+-------------+---------------+
| s.apply(…)   |             |      rank   |               |
| s.agg(…)     |    x  1.0   |   x   1.0   |   r  x  1.0   |
|              |    y  2.0   |   y   2.0   |      y  2.0   |
+--------------+-------------+-------------+---------------+
```

### DataFrame
**Table with labeled rows and columns.**

```python
>>> df = pd.DataFrame([[1, 2], [3, 4]], index=['a', 'b'], columns=['x', 'y']); df
   x  y
a  1  2
b  3  4
```

```python
<DF>   = pd.DataFrame(<list_of_rows>)          # Rows can be either lists, dicts or series.
<DF>   = pd.DataFrame(<dict_of_columns>)       # Columns can be either lists, dicts or series.
```

```python
<el>   = <DF>.loc[row_key, col_key]            # Or: <DF>.iloc[row_i, col_i]
<S/DF> = <DF>.loc[row_key/s]                   # Or: <DF>.iloc[row_i/s]
<S/DF> = <DF>.loc[:, col_key/s]                # Or: <DF>.iloc[:, col_i/s]
<DF>   = <DF>.loc[row_bools, col_bools]        # Or: <DF>.iloc[row_bools, col_bools]
```

```python
<S/DF> = <DF>[col_key/s]                       # Or: <DF>.<col_key>
<DF>   = <DF>[<S_of_bools>]                    # Filters rows. For example `df[df.x > 1]`.
<DF>   = <DF>[<DF_of_bools>]                   # Assigns NaN to items that are False in bools.
```

```python
<DF>   = <DF> > <el/S/DF>                      # Returns DF of bools. Treats series as a row.
<DF>   = <DF> + <el/S/DF>                      # Items with non-matching keys get value NaN.
```

```python
<DF>   = <DF>.set_index(col_key)               # Replaces row keys with column's values.
<DF>   = <DF>.reset_index(drop=False)          # Drops or moves row keys to column named index.
<DF>   = <DF>.sort_index(ascending=True)       # Sorts rows by row keys. Use `axis=1` for cols.
<DF>   = <DF>.sort_values(col_key/s)           # Sorts rows by passed column/s. Also `axis=1`.
```

```python
<DF>   = <DF>.head/tail/sample(<int>)          # Returns first, last, or random n rows.
<DF>   = <DF>.describe()                       # Describes columns. Also info(), corr(), shape.
<DF>   = <DF>.query('<query>')                 # Filters rows. For example `df.query('x > 1')`.
```

```python
<DF>.plot.line/area/bar/scatter(x=col_key, …)  # `y=col_key/s`. Also hist/box(column/by=col_k).
plt.show()                                     # Displays the plot. Also plt.savefig(<path>).
```

#### DataFrame — Merge, Join, Concat:
```python
>>> df_2 = pd.DataFrame([[4, 5], [6, 7]], index=['b', 'c'], columns=['y', 'z']); df_2
   y  z
b  4  5
c  6  7
```

```text
+-----------------------+---------------+------------+------------+---------------------------+
|                       |    'outer'    |   'inner'  |   'left'   |       Description         |
+-----------------------+---------------+------------+------------+---------------------------+
| df.merge(df_2,        |    x   y   z  | x   y   z  | x   y   z  | Merges on column if 'on'  |
|          on='y',      | 0  1   2   .  | 3   4   5  | 1   2   .  | or 'left_on/right_on' are |
|          how=…)       | 1  3   4   5  |            | 3   4   5  | set, else on shared cols. |
|                       | 2  .   6   7  |            |            | Uses 'inner' by default.  |
+-----------------------+---------------+------------+------------+---------------------------+
| df.join(df_2,         |    x yl yr  z |            | x yl yr  z | Merges on row keys.       |
|         lsuffix='l',  | a  1  2  .  . | x yl yr  z | 1  2  .  . | Uses 'left' by default.   |
|         rsuffix='r',  | b  3  4  4  5 | 3  4  4  5 | 3  4  4  5 | If Series is passed, it   |
|         how=…)        | c  .  .  6  7 |            |            | is treated as a column.   |
+-----------------------+---------------+------------+------------+---------------------------+
| pd.concat([df, df_2], |    x   y   z  |     y      |            | Adds rows at the bottom.  |
|           axis=0,     | a  1   2   .  |     2      |            | Uses 'outer' by default.  |
|           join=…)     | b  3   4   .  |     4      |            | A Series is treated as a  |
|                       | b  .   4   5  |     4      |            | column. To add a row use  |
|                       | c  .   6   7  |     6      |            | pd.concat([df, DF([s])]). |
+-----------------------+---------------+------------+------------+---------------------------+
| pd.concat([df, df_2], |    x  y  y  z |            |            | Adds columns at the       |
|           axis=1,     | a  1  2  .  . | x  y  y  z |            | right end. Uses 'outer'   |
|           join=…)     | b  3  4  4  5 | 3  4  4  5 |            | by default. A Series is   |
|                       | c  .  .  6  7 |            |            | treated as a column.      |
+-----------------------+---------------+------------+------------+---------------------------+
```

#### DataFrame — Aggregate, Transform, Map:
```python
<S>  = <DF>.sum/max/mean/std/idxmax/count()    # Or: <DF>.apply/agg(lambda <S>: <el>)
<DF> = <DF>.rank/diff/cumsum/ffill/interpo…()  # Or: <DF>.apply/agg/transform(lambda <S>: <S>)
<DF> = <DF>.isna/fillna/isin([<el/coll>])      # Or: <DF>.applymap(lambda <el>: <el>)
```

```text
+-----------------+---------------+---------------+---------------+
|                 |     'sum'     |    ['sum']    | {'x': 'sum'}  |
+-----------------+---------------+---------------+---------------+
| df.apply(…)     |      x  4     |        x  y   |     x  4      |
| df.agg(…)       |      y  6     |   sum  4  6   |               |
+-----------------+---------------+---------------+---------------+
```

```text
+-----------------+---------------+---------------+---------------+
|                 |     'rank'    |    ['rank']   | {'x': 'rank'} |
+-----------------+---------------+---------------+---------------+
| df.apply(…)     |               |       x    y  |               |
| df.agg(…)       |       x    y  |    rank rank  |         x     |
| df.transform(…) |  a  1.0  1.0  |  a  1.0  1.0  |    a  1.0     |
|                 |  b  2.0  2.0  |  b  2.0  2.0  |    b  2.0     |
+-----------------+---------------+---------------+---------------+
```
* **Listed methods process the columns unless they receive `'axis=1'`. Exceptions to this rule are `'<DF>.dropna()'`, `'<DF>.drop(row_key/s)'` and `'<DF>.rename(<dict/func>)'`.**
* **Fifth result's columns are indexed with a multi-index. This means we need a tuple of column keys to specify a column: `'<DF>.loc[row_key, (col_key_1, col_key_2)]'`.**

### Multi-Index
```python
<DF> = <DF>.loc[row_key_1]                     # Or: <DF>.xs(row_key_1)
<DF> = <DF>.loc[:, (slice(None), col_key_2)]   # Or: <DF>.xs(col_key_2, axis=1, level=1)
<DF> = <DF>.set_index(col_keys)                # Creates index from cols. Also `append=False`.
<DF> = <DF>.pivot_table(index=col_key/s)       # `columns=key/s, values=key/s, aggfunc='mean'`.
<S>  = <DF>.stack/unstack(level=-1)            # Combines col keys with row keys or vice versa.
```

### File Formats
```python
<S/DF> = pd.read_json/pickle(<path/url/file>)  # Also io.StringIO(<str>), io.BytesIO(<bytes>).
<DF>   = pd.read_csv/excel(<path/url/file>)    # Also `header/index_col/dtype/usecols/…=<obj>`.
<list> = pd.read_html(<path/url/file>)         # Raises ImportError if webpage has zero tables.
<S/DF> = pd.read_parquet/feather/hdf(<path…>)  # Function read_hdf() accepts `key=<s/df_name>`.
<DF>   = pd.read_sql('<table/query>', <conn>)  # Pass SQLite3/Alchemy connection. See #SQLite.
```

```python
<DF>.to_json/csv/html/latex/parquet(<path>)    # Returns a string/bytes if path is omitted.
<DF>.to_pickle/excel/feather/hdf(<path>)       # Method to_hdf() requires `key=<s/df_name>`.
<DF>.to_sql('<table_name>', <connection>)      # Also `if_exists='fail/replace/append'`.
```
* **`'$ pip3 install "pandas[excel]" odfpy lxml pyarrow'` installs dependencies.**
* **Csv functions use the same dialect as standard library's csv module (e.g. `'sep=","'`).**
* **Read\_csv() only parses dates of columns that are listed in 'parse\_dates'. It automatically tries to detect the format, but it can be helped with 'date\_format' or 'dayfirst' arguments.**
* **We get a dataframe with DatetimeIndex if 'parse_dates' argument includes 'index\_col'. Its `'resample("y/m/d/h")'` method returns Resampler object that is similar to GroupBy.**

### GroupBy
**Object that groups together rows of a dataframe based on the value of the passed column.**

```python
<GB> = <DF>.groupby(col_key/s)                 # Splits DF into groups based on passed column.
<DF> = <GB>.apply/filter(<func>)               # Filter drops a group if func returns False.
<DF> = <GB>.get_group(<el>)                    # Selects a group by grouping column's value.
<S>  = <GB>.size()                             # S of group sizes. Same keys as get_group().
<GB> = <GB>[col_key]                           # Single column GB. All operations return S.
```

```python
<DF> = <GB>.sum/max/mean/std/idxmax/count()    # Or: <GB>.agg(lambda <S>: <el>)
<DF> = <GB>.rank/diff/cumsum/ffill()           # Or: <GB>.transform(lambda <S>: <S>)
<DF> = <GB>.fillna(<el>)                       # Or: <GB>.transform(lambda <S>: <S>)
```

#### Divides rows into groups and sums their columns. Result has a named index that creates column `'z'` on reset_index():
```python
>>> df = pd.DataFrame([[1, 2, 3], [4, 5, 6], [7, 8, 6]], list('abc'), list('xyz'))
>>> gb = df.groupby('z'); gb.apply(print)
   x  y  z
a  1  2  3
   x  y  z
b  4  5  6
c  7  8  6
>>> gb.sum()
    x   y
z
3   1   2
6  11  13
```

### Rolling
**Object for rolling window calculations.**

```python
<RS/RDF/RGB> = <S/DF/GB>.rolling(win_size)     # Also: `min_periods=None, center=False`.
<RS/RDF/RGB> = <RDF/RGB>[col_key/s]            # Or: <RDF/RGB>.<col_key>
<S/DF>       = <R>.mean/sum/max()              # Or: <R>.apply/agg(<agg_func/str>)
```


Plotly
------
```python
# $ pip3 install plotly kaleido pandas
import plotly.express as px, pandas as pd
```

```python
<Fig> = px.line(<DF>, x=col_key, y=col_key)           # Or: px.line(x=<list>, y=<list>)
<Fig>.update_layout(margin=dict(t=0, r=0, b=0, l=0))  # Also `paper_bgcolor='rgb(0, 0, 0)'`.
<Fig>.write_html/json/image('<path>')                 # `<Fig>.show()` displays the plot.
```

```python
<Fig> = px.area/bar/box(<DF>, x=col_key, y=col_key)   # Also `color=col_key`.
<Fig> = px.scatter(<DF>, x=col_key, y=col_key)        # Also `color/size/symbol=col_key`.
<Fig> = px.scatter_3d(<DF>, x=col_key, y=col_key, …)  # `z=col_key`. Also color/size/symbol.
<Fig> = px.histogram(<DF>, x=col_key)                 # Also `nbins=<int>`.
```

#### Displays a line chart of total coronavirus deaths per million grouped by continent:

![Covid Deaths](web/covid_deaths.png)
<div id="2a950764-39fc-416d-97fe-0a6226a3095f" class="plotly-graph-div" style="height:312px; width:914px;"></div>

```python
covid = pd.read_csv('https://raw.githubusercontent.com/owid/covid-19-data/8dde8ca49b'
                    '6e648c17dd420b2726ca0779402651/public/data/owid-covid-data.csv',
                    usecols=['iso_code', 'date', 'population', 'total_deaths'])
continents = pd.read_csv('https://gto76.github.io/python-cheatsheet/web/continents.csv',
                         usecols=['Three_Letter_Country_Code', 'Continent_Name'])
df = pd.merge(covid, continents, left_on='iso_code', right_on='Three_Letter_Country_Code')
df = df.groupby(['Continent_Name', 'date']).sum().reset_index()
df['Total Deaths per Million'] = df.total_deaths * 1e6 / df.population
df = df[df.date > '2020-03-14']
df = df.rename({'date': 'Date', 'Continent_Name': 'Continent'}, axis='columns')
px.line(df, x='Date', y='Total Deaths per Million', color='Continent').show()
```

#### Displays a multi-axis line chart of total coronavirus cases and changes in prices of Bitcoin, Dow Jones and gold:

![Covid Cases](web/covid_cases.png)
<div id="e23ccacc-a456-478b-b467-7282a2165921" class="plotly-graph-div" style="height:285px; width:935px;"></div>

```python
# $ pip3 install pandas lxml selenium plotly
import pandas as pd, selenium.webdriver, io, plotly.graph_objects as go

def main():
    covid, (bitcoin, gold, dow) = get_covid_cases(), get_tickers()
    df = wrangle_data(covid, bitcoin, gold, dow)
    display_data(df)

def get_covid_cases():
    url = 'https://covid.ourworldindata.org/data/owid-covid-data.csv'
    df = pd.read_csv(url, parse_dates=['date'])
    df = df[df.location == 'World']
    s = df.set_index('date').total_cases
    return s.rename('Total Cases')

def get_tickers():
    with selenium.webdriver.Chrome() as driver:
        symbols = {'Bitcoin': 'BTC-USD', 'Gold': 'GC=F', 'Dow Jones': '%5EDJI'}
        for name, symbol in symbols.items():
            yield get_ticker(driver, name, symbol)

def get_ticker(driver, name, symbol):
    url = f'https://finance.yahoo.com/quote/{symbol}/history/'
    driver.get(url + '?period1=1579651200&period2=9999999999')
    if buttons := driver.find_elements('xpath', '//button[@name="reject"]'):
        buttons[0].click()
    html = io.StringIO(driver.page_source)
    dataframes = pd.read_html(html, parse_dates=['Date'])
    s = dataframes[0].set_index('Date').Open
    return s.rename(name)

def wrangle_data(covid, bitcoin, gold, dow):
    df = pd.concat([bitcoin, gold, dow], axis=1)  # Creates table by joining columns on dates.
    df = df.sort_index().interpolate()            # Sorts rows by date and interpolates NaN-s.
    df = df.loc['2020-02-23':'2021-12-20']        # Keeps rows between specified dates.
    df = (df / df.iloc[0]) * 100                  # Calculates percentages relative to day 1.
    df = df.join(covid)                           # Adds column with covid cases.
    return df.sort_values(df.index[-1], axis=1)   # Sorts columns by last day's value.

def display_data(df):
    figure = go.Figure()
    for col_name in reversed(df.columns):
        yaxis = 'y1' if col_name == 'Total Cases' else 'y2'
        trace = go.Scatter(x=df.index, y=df[col_name], yaxis=yaxis, name=col_name)
        figure.add_trace(trace)
    figure.update_layout(
        width=944,
        height=423,
        yaxis1=dict(title='Total Cases', rangemode='tozero'),
        yaxis2=dict(title='%', rangemode='tozero', overlaying='y', side='right'),
        colorway=['#EF553B', '#636EFA', '#00CC96', '#FFA152'],
        legend=dict(x=1.08)
    )
    figure.show()

if __name__ == '__main__':
    main()
```


Appendix
--------
### Cython
**Library that compiles Python-like code into C.**

```python
# $ pip3 install cython
import pyximport; pyximport.install()  # Module that runs imported Cython scripts.
import <cython_script>                 # Script must be saved with '.pyx' extension.
<cython_script>.main()                 # Main() isn't automatically executed.
```

#### Definitions:
* **All `'cdef'` definitions are optional, but they contribute to the speed-up.**
* **Also supports C pointers (via `'*'` and `'&'`), structs, unions and enums.**

```python
cdef <ctype/type> <var_name> [= <obj>]
cdef <ctype>[n_elements] <var_name> [= <coll_of_nums>]
cdef <ctype/type/void> <func_name>(<ctype/type> <arg_name>): ...
```

```python
cdef class <class_name>:
    cdef public <ctype/type> <attr_name>
    def __init__(self, <ctype/type> <arg_name>):
        self.<attr_name> = <arg_name>
```

### Virtual Environments
**System for installing libraries directly into project's directory.**

```perl
$ python3 -m venv NAME      # Creates virtual environment in current directory.
$ source NAME/bin/activate  # Activates it. On Windows run `NAME\Scripts\activate`.
$ pip3 install LIBRARY      # Installs the library into active environment.
$ python3 FILE              # Runs the script in active environment. Also `./FILE`.
$ deactivate                # Deactivates the active virtual environment.
```

### Basic Script Template
**Run the script with `'$ python3 FILE'` or `'$ chmod u+x FILE; ./FILE'`. To automatically start the debugger when uncaught exception occurs run `'$ python3 -m pdb -cc FILE'`.**
```python
#!/usr/bin/env python3
#
# Usage: .py
#

from sys import argv, exit
from collections import defaultdict, namedtuple
from dataclasses import make_dataclass
from enum import Enum
import functools as ft, itertools as it, operator as op, re


def main():
    pass


###
##  UTIL
#

def read_file(filename):
    with open(filename, encoding='utf-8') as file:
        return file.readlines()


if __name__ == '__main__':
    main()
```


Index
-----
* **Ctrl+F / ⌘F is usually sufficient.**
* **Searching `'#<title>'` on the [webpage](https://gto76.github.io/python-cheatsheet/) will limit the search to the titles.**
* **Click on the title's `'🔗'` to get a link to its section.**
