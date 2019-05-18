### headpq, itertools and collections

* **headpq**

  ```python
  import heapq
  
  list1 = [34, 25, 12, 99, 87, 63, 58, 78, 88, 92]
  list2 = [
      {'name': 'IBM', 'shares': 100, 'price': 91.1},
      {'name': 'AAPL', 'shares': 50, 'price': 543.22},
      {'name': 'FB', 'shares': 200, 'price': 21.09},
      {'name': 'HPQ', 'shares': 35, 'price': 31.75},
      {'name': 'YHOO', 'shares': 45, 'price': 16.35},
      {'name': 'ACME', 'shares': 75, 'price': 115.65}
  ]
  print(heapq.nlargest(3, list1))
  print(heapq.nsmallest(3, list1))
  print(heapq.nlargest(2, list2, key=lambda x: x['price']))
  print(heapq.nlargest(2, list2, key=lambda x: x['shares']))
  ```

  >```python
  >[99, 92, 88]
  >[12, 25, 34]
  >[{'name': 'AAPL', 'shares': 50, 'price': 543.22}, {'name': 'ACME', 'shares': 75, 'price': 115.65}]
  >[{'name': 'FB', 'shares': 200, 'price': 21.09}, {'name': 'IBM', 'shares': 100, 'price': 91.1}]
  >```

* **itertools**

  ```python
  import itertools
  
  itertools.permutations('ABCD')
  itertools.combinations('ABCDE', 3)
  itertools.product('ABCD', '123')
  print([x for x in iter1])
  print([x for x in iter2])
  print([x for x in iter3])
  ```

  > ```python
  > [('A', 'B', 'C', 'D'), ('A', 'B', 'D', 'C'), ('A', 'C', 'B', 'D'), ('A', 'C', 'D', 'B'), ('A', 'D', 'B', 'C'), ('A', 'D', 'C', 'B'), ('B', 'A', 'C', 'D'), ('B', 'A', 'D', 'C'), ('B', 'C', 'A', 'D'), ('B', 'C', 'D', 'A'), ('B', 'D', 'A', 'C'), ('B', 'D', 'C', 'A'), ('C', 'A', 'B', 'D'), ('C', 'A', 'D', 'B'), ('C', 'B', 'A', 'D'), ('C', 'B', 'D', 'A'), ('C', 'D', 'A', 'B'), ('C', 'D', 'B', 'A'), ('D', 'A', 'B', 'C'), ('D', 'A', 'C', 'B'), ('D', 'B', 'A', 'C'), ('D', 'B', 'C', 'A'), ('D', 'C', 'A', 'B'), ('D', 'C', 'B', 'A')]
  > [('A', 'B', 'C'), ('A', 'B', 'D'), ('A', 'B', 'E'), ('A', 'C', 'D'), ('A', 'C', 'E'), ('A', 'D', 'E'), ('B', 'C', 'D'), ('B', 'C', 'E'), ('B', 'D', 'E'), ('C', 'D', 'E')]
  > [('A', '1'), ('A', '2'), ('A', '3'), ('B', '1'), ('B', '2'), ('B', '3'), ('C', '1'), ('C', '2'), ('C', '3'), ('D', '1'), ('D', '2'), ('D', '3')]
  > ```

  ```python
  >>> import itertools
  >>> cs = itertools.cycle('ABC') # 注意字符串也是序列的一种
  >>> for c in cs:
  ...     print c
  ...
  'A'
  'B'
  'C'
  'A'
  'B'
  'C'
  ...
  ```

  ```python
  >>> ns = itertools.repeat('A', 10)
  >>> for n in ns:
  ...     print n
  ...
  打印10次'A'
  ```

  ```python
  >>> natuals = itertools.count(1)
  >>> ns = itertools.takewhile(lambda x: x <= 10, natuals)
  >>> for n in ns:
  ...     print n
  ...
  打印出1到10
  ```

  ```python
  for c in itertools.chain('ABC', 'XYZ'):
      print c
  ```

  > ```python
  > 'A' 'B' 'C' 'X' 'Y' 'Z'
  > ```

  ```python
  >>> for key, group in itertools.groupby('AAABBBCCAAA'):
  ...     print key, list(group) # 为什么这里要用list()函数呢？
  ...
  A ['A', 'A', 'A']
  B ['B', 'B', 'B']
  C ['C', 'C']
  A ['A', 'A', 'A']
  ```

  ```python
  >>> for key, group in itertools.groupby('AaaBBbcCAAa', lambda c: c.upper()):
  ...     print key, list(group)
  ...
  A ['A', 'a', 'a']
  B ['B', 'B', 'b']
  C ['c', 'C']
  A ['A', 'A', 'a']
  ```

  ```python
  >>> for x in itertools.imap(lambda x, y: x * y, [10, 20, 30], itertools.count(1)):
  ...     print x
  ...
  10
  40
  90
  ```

* **collections**

  ```python
  >>> from collections import namedtuple
  >>> Point = namedtuple('Point', ['x', 'y'])
  >>> p = Point(1, 2)
  >>> p.x
  1
  >>> p.y
  2
  ```

  ```python
  >>> from collections import deque
  >>> q = deque(['a', 'b', 'c'])
  >>> q.append('x')
  >>> q.appendleft('y')
  >>> q
  deque(['y', 'a', 'b', 'c', 'x'])
  ```

  ```python
  >>> from collections import defaultdict
  >>> dd = defaultdict(lambda: 'N/A')
  >>> dd['key1'] = 'abc'
  >>> dd['key1'] # key1存在
  'abc'
  >>> dd['key2'] # key2不存在，返回默认值
  'N/A'
  ```

  ```python
  >>> from collections import OrderedDict
  >>> d = dict([('a', 1), ('b', 2), ('c', 3)])
  >>> d # dict的Key是无序的
  {'a': 1, 'c': 3, 'b': 2}
  >>> od = OrderedDict([('a', 1), ('b', 2), ('c', 3)])
  >>> od # OrderedDict的Key是有序的
  OrderedDict([('a', 1), ('b', 2), ('c', 3)])
  ```

  ```python
  >>> od = OrderedDict()
  >>> od['z'] = 1
  >>> od['y'] = 2
  >>> od['x'] = 3
  >>> od.keys() # 按照插入的Key的顺序返回
  ['z', 'y', 'x']
  ```

  ```python
  >>> from collections import Counter
  >>> c = Counter()
  >>> for ch in 'programming':
  ...     c[ch] = c[ch] + 1
  ...
  >>> c
  Counter({'g': 2, 'm': 2, 'r': 2, 'a': 1, 'i': 1, 'o': 1, 'n': 1, 'p': 1})
  ```

  