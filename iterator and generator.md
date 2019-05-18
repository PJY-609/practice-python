### iterator and generator

* **iterator**

  ```python
  >>>list=[1,2,3,4]
  >>> it = iter(list)    # 创建迭代器对象
  >>> print (next(it))   # 输出迭代器的下一个元素
  1
  >>> print (next(it))
  2
  ```

  ```python
  list=[1,2,3,4]
  it = iter(list)    # 创建迭代器对象
  for x in it:
      print (x, end=" ")
  ```

  **```__init__```** and **```__next__```**

  ```python
  class Fib(object):
      """迭代器"""
      
      def __init__(self, num):
          self.num = num
          self.a, self.b = 0, 1
          self.idx = 0
     
      def __iter__(self):
          return self
  
      def __next__(self):
          if self.idx < self.num:
              self.a, self.b = self.b, self.a + self.b
              self.idx += 1
              return self.a
          raise StopIteration()
  ```

* **generator**

  ```python
  def fib(num):
      """生成器"""
      a, b = 0, 1
      for _ in range(num):
          a, b = b, a + b
          yield a
  ```

  