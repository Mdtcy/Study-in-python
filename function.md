- ***函数***

  ```python
  #定义一个函数
  def my_fbs(x):
      if x>0:
          return x
      else:
          return -x
  #如果函数没有返回值，函数执行完也会返回一个None，可以将return None 简写为return

  #定义一个空函数，pass作为一个占位符，用于在没想好函数里怎么写时让代码可以执行
  def kk():
      pass

  #pass还可以用在其他语句里
  if k>0:
      pass

  #python里函数可以返回多个值，实际上返回的是一个tuple，多个变量可接收一个tuple，按对应位置进行赋值
  a=(1,2,3)
  b,c,d=a

  ##默认参数
  def power(x,n=2):
      s=1
      while n>0:
         s=s*x
         n=n-1
      return s
  power(5) #25
  power(5,3) #125

  #多个默认参数，如果不按默认顺序的话要指明参数
  def enroll(name, gender=7,city='hongkon'):
      print('name:', name,'gender',gender,'city',city)
  enroll('mike',6,'shantou')
  enroll('mike',city='shantou')

  #默认参数必须是不可变对象，因为默认参数也是一个变量，在定义函数时就会给它创建一个对象，如果后面改变了传入的默认参数，那默认参数也会随之改变
  #可以像下面这样来实现使默认参数为一个list又不会修改默认参数
  def add_end(L=None):
      if L is None:
          L = []
      L.append('END')
      return L

  ##可变参数，定义可变参数和定义一个list或tuple参数相比，仅仅在参数前面加了一个*号。在函数内部，参数numbers接收到的是一个tuple
  def call(*n):
      sum=0
      for j in n:
          sum=sum+j*j
      return sum
  print(call(1,2,3,4))

  #如果已经有一个list或者tuple，可以在调用时在list名前加一个*，这样就可以将list中的元素当成可变参数传进去
  a=[1,2,3]
  print(call(*a))

  ##关键字参数
  #可变参数允许你传入0个或任意个参数，这些可变参数在函数调用时自动组装为一个tuple。而关键字参数允许你传入0个或任意个含参数名的参数，这些关键字参数在函数内部自动组装为一个dict。
  def person(name, age, **kw):
      print('name:', name, 'age:', age, 'other:', kw)
  person('mike',24,city='hongkon')

  #和可变参数类似，也可以先组装出一个dict，然后，把该dict转换为关键字参数传进去
  extra={'city':'shantou','job':'teacher'}
  person('mike',24,**extra) #全部传入
  person('Jack', 24, city=extra['city']) #传入单个

  ##命名关键字参数，如果要限制关键字参数的名字，就可以用命名关键字参数
  def person(name, age, *, city, job):
      print(name, age, city, job)
  #和关键字参数**kw不同，命名关键字参数需要一个特殊分隔符*，*后面的参数被视为命名关键字参数。
  调用方式如下：
  person('Jack', 24, city='Beijing', job='Engineer')


  ```

- ***小结***

  ​

  Python的函数具有非常灵活的参数形态，既可以实现简单的调用，又可以传入非常复杂的参数。

  默认参数一定要用不可变对象，如果是可变对象，程序运行时会有逻辑错误！

  要注意定义可变参数和关键字参数的语法：

  `*args`是可变参数，args接收的是一个tuple；

  `**kw`是关键字参数，kw接收的是一个dict。

  以及调用函数时如何传入可变参数和关键字参数的语法：

  可变参数既可以直接传入：`func(1, 2, 3)`，又可以先组装list或tuple，再通过`*args`传入：`func(*(1, 2, 3))`；

  关键字参数既可以直接传入：`func(a=1, b=2)`，又可以先组装dict，再通过`**kw`传入：`func(**{'a': 1, 'b': 2})`。

  使用`*args`和`**kw`是Python的习惯写法，当然也可以用其他参数名，但最好使用习惯用法。

  命名的关键字参数是为了限制调用者可以传 入的参数名，同时可以提供默认值。

  定义命名的关键字参数在没有可变参数的情况下不要忘了写分隔符`*`，否则定义的将是位置参数。