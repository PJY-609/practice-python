### list comprehension

```python
variable = [out_exp_res for out_exp in input_list if out_exp == 2]
```

```python
prices = {
    'AAPL': 191.88,
    'GOOG': 1186.96,
    'IBM': 149.24,
    'ORCL': 48.44,
    'ACN': 166.89,
    'FB': 208.09,
    'SYMC': 21.29
}
# 用股票价格大于100元的股票构造一个新的字典
prices2 = {key: value for key, value in prices.items() if value > 100}
```

```python
names = ['张三', '赵四', '马五', '黄六']
courses = ['语文', '数学', '英语']
scores = [[None] * len(courses) for _ in range(len(names))]
for row, name in enumerate(names):
    for col, course in enumerate(courses):
        scores[row][col] = float(input(f'请输入{name}的{course}成绩: '))
        print(scores)
```

***

### ```map()``` and ```filter()```

map(f, S) 等价于

```python
[ f(x) for x in S ]
```

而 filter(P, S) 等价于

```python
[ x for x in S if P(x) ]
```

***

### ```lambda```

```python
items1 = list(map(lambda x: x ** 2, filter(lambda x: x % 2, range(1, 10))))
items2 = [x ** 2 for x in range(1, 10) if x % 2]
```

```python
map(lambda x: x + 1, S)
[ x + 1 for x in S ]
```