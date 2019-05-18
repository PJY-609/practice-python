### data structure in python

* string type

  ```python
  # 通过len函数计算字符串的长度
  print(len(str1))  # 13
  # 获得字符串首字母大写的拷贝
  print(str1.capitalize())  # Hello, world!
  # 获得字符串变大写后的拷贝
  print(str1.upper())  # HELLO, WORLD!
  # 从字符串中查找子串所在位置
  print(str1.find('or'))  # 8
  print(str1.find('shit'))  # -1
  # 与find类似但找不到子串时会引发异常
  # print(str1.index('or'))
  # print(str1.index('shit'))
  # 检查字符串是否以指定的字符串开头
  print(str1.startswith('He'))  # False
  print(str1.startswith('hel'))  # True
  # 检查字符串是否以指定的字符串结尾
  print(str1.endswith('!'))  # True
  # 将字符串以指定的宽度居中并在两侧填充指定的字符
  print(str1.center(50, '*'))
  # 将字符串以指定的宽度靠右放置左侧填充指定的字符
  print(str1.rjust(50, ' '))
  str2 = 'abc123456'
  # 从字符串中取出指定位置的字符(下标运算)
  print(str2[2])  # c
  # 字符串切片(从指定的开始索引到指定的结束索引)
  print(str2[2:5])  # c12
  print(str2[2:])  # c123456
  print(str2[2::2])  # c246
  print(str2[::2])  # ac246
  print(str2[::-1])  # 654321cba
  print(str2[-3:-1])  # 45
  # 检查字符串是否由数字构成
  print(str2.isdigit())  # False
  # 检查字符串是否以字母构成
  print(str2.isalpha())  # False
  # 检查字符串是否以数字和字母构成
  print(str2.isalnum())  # True
  str3 = '  jackfrued@126.com '
  print(str3)
  # 获得字符串修剪左右两侧空格的拷贝
  print(str3.strip())
  ```

* list

  ```python
  list2 = ['hello'] * 5
  print(list2) # ['hello', 'hello', 'hello', 'hello', 'hello']
  # 下标(索引)运算
  print(list1[-1])
  print(list1[-3])
  # 添加元素
  list1.insert(1, 400)
  list1 += [1000, 2000]
  # 删除元素
  list1.remove(3)
  del list1[0]
  # 清空列表元素
  list1.clear()
  ```

  ```python
  list2 = sorted(list1)
  ```

* **```f = [x - 2 for x in range(1, 1000)]```**

* set 

  ```python
  set1.add(4)
  set2.update([11, 12])
  set2.discard(5)
  # remove的元素如果不存在会引发KeyError
  set2.remove(4)
  # 遍历集合容器
  for elem in set2:
      print(elem ** 2, end=' ')
  print(set3.pop())
  
  # 集合的交集、并集、差集、对称差运算
  print(set1 & set2)
  # print(set1.intersection(set2))
  print(set1 | set2)
  # print(set1.union(set2))
  print(set1 - set2)
  # print(set1.difference(set2))
  print(set1 ^ set2)
  # print(set1.symmetric_difference(set2))
  # 判断子集和超集
  print(set2 <= set1)
  # print(set2.issubset(set1))
  print(set3 <= set1)
  # print(set3.issubset(set1))
  print(set1 >= set2)
  # print(set1.issuperset(set2))
  print(set1 >= set3)
  # print(set1.issuperset(set3))
  ```

* dictionary

  ```python
  for elem in scores:
      print('%s\t--->\t%d' % (elem, scores[elem]))
  # 更新字典中的元素
  scores.update(冷面=67, 方启鹤=85)
  
  print(scores.get('武则天'))
  # get方法也是通过键获取对应的值但是可以设置默认值
  print(scores.get('武则天', 60))
  # 删除字典中的元素
  print(scores.popitem())
  print(scores.pop('骆昊', 100))
  # 清空字典
  scores.clear()
  ```

  ```python 
   keys() / values() / items() / setdefault()
  ```

  