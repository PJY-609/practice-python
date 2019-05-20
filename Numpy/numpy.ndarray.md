### ```numpy.ndarray```

***

#### data type

* ```ndarray.dtype```

  

***

#### other attributes

* ```ndarray.flat```

  

***

#### array conversion

* ```ndarray.tolist()```

* ```ndarray.astype()```

* ```ndarray.fill()```

* ```ndarray.copy()``` and ```ndarray.view()```

  ```python
  a = np.arange(6)
  b = a.view()
  b.shape = 3, 2
  print(b)
  print(a)
  a[1] = 0
  print(a)
  print(b)
  ```

  > ```python
  > [[0 1]
  >  [2 3]
  >  [4 5]]
  >  
  > [0 1 2 3 4 5]
  >  
  > [0 0 2 3 4 5]
  >  
  > [[0 0]
  >  [2 3]
  >  [4 5]]
  > ```

  

  应用：当需要对输入图像三个通道进行相同的处理时，使用cv2.split和cv2.merge是相当浪费资源的，因为任何一个通道的数据对处理来说都是一样的，我们可以用view来将其转换为一维矩阵后再做处理，这要不需要额外的内存开销和时间开销。

  代码如下：

  ```python
  def createFlatView(array):
      """Return a 1D view of an array of any dimensionality."""
      flatView = array.view()
      flatView.shape = array.size
      return flatView
  ```

  

  使用切片创建视图修改数据会影响到原始数组：

  ```python
  arr = np.arange(12)
  print ('我们的数组：')
  print (arr)
  print ('创建切片：')
  a=arr[3:]
  b=arr[3:]
  a[1]=123
  b[2]=234
  print(arr)
  print(id(a),id(b),id(arr[3:]))
  ```

  > ```python
  > 我们的数组：
  > [ 0  1  2  3  4  5  6  7  8  9 10 11]
  > 创建切片：
  > [  0   1   2   3 123 234   6   7   8   9  10  11]
  > 4545878416 4545878496 4545878576
  > ```

  

  与```list```的区别：

  <img src='list.png' style='zoom:70%'>

  

***

#### shape manipulation

* ```ndarray.flatten()```

* ```ndarray.ravel()```

* ```ndarray.squeeze()```

  ```python
  a = np.arange(6).reshape(6, 1)
  print(a)
  b = a.squeeze()
  print(b)
  ```

  > ```python
  > [[0]
  > [1]
  > [2]
  > [3]
  > [4]
  > [5]]
  > 
  > [0 1 2 3 4 5]
  > ```

  

***

#### item selection and manipulation

* ```ndarray.argsort()```

  ```python
  a = np.random.randn(1, 6)
  a.argsort()
  b = np.array([a[0][i] for i in a.argsort()])
  ```

  

***

#### calculation

* ```ndarray.all()```

* ```ndarray.any()```

  ```python
  >>> np.any([[True, False], [False, False]], axis=0)
  array([ True, False])
  ```

  

