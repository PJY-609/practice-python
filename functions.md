### functions

* **```*args``` and `**kwargs`**

  ```python 
  def fun_var_args(farg, *args):
    print "arg:", farg
    for value in args:
        print "another arg:", value
  fun_var_args(1, "two", 3) # *args may contain list
  ```
  > arg: 1
  another arg: two
  another arg: 3
  
  ```python
  def fun_var_args_call(arg1, arg2, arg3):
    print "arg1:", arg1
    print "arg2:", arg2
    print "arg3:", arg3
 
  args = ["two", 3] #list
 
  fun_var_args_call(1, *args)
  ```
  > arg1: 1
  arg2: two
  arg3: 3
  
  ```python
  def fun_var_kwargs(farg, **kwargs):
    print "arg:", farg
    for key in kwargs:
        print "another keyword arg: %s: %s" % (key, kwargs[key])
  
  fun_var_kwargs(farg=1, myarg2="two", myarg3=3) # myarg2 and myarg3 are keys， **kwargs can be dictionary
  ```
  > arg: 1
  another keyword arg: myarg2: two
  another keyword arg: myarg3: 3
  
  ```python
  
  def fun_var_args_call(arg1, arg2, arg3):
    print "arg1:", arg1
    print "arg2:", arg2
    print "arg3:", arg3
 
  kwargs = {"arg3": 3, "arg2": "two"} # dictionary
  ```
  > arg1: 1
  arg2:"two"
  arg3:3
  
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

  
