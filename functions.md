### functions

* **```*args```**

  ```python 
  def add(*args):
      total = 0
      for val in args:
          total += val
      return total
  ```

* **```if __name__ == '__main__':```**

* **```global```** but avoid using global variables

  ```python
  def foo():
      b = 'hello'
  
      def bar():  # in Python you can define functins inside of a function 
          c = True
          print(a)
          print(b)
          print(c)
  
      bar()
      # print(c)  # NameError: name 'c' is not defined
  
  
  if __name__ == '__main__':
      a = 100
      # print(b)  # NameError: name 'b' is not defined
      foo()
  ```

  ```python
  def foo():
      a = 200
      print(a)  # 200
  
  
  if __name__ == '__main__':
      a = 100
      foo()
      print(a)  # 100
  ```

  ```python
  def foo():
      global a
      a = 200
      print(a)  # 200
  
  
  if __name__ == '__main__':
      a = 100
      foo()
      print(a)  # 200
  ```

  