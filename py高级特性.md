

```python
#切片 相当于substring
a=[1,2,3,4,5]
str='hello'
print(str[0:3]) 输出 hel
print(a[1:3]) #输出 [2,3]
print(a[:5:2]) #输出 [1,3,5]

#迭代(iteration) for循环遍历list或tuple 
#迭代dic，默认是迭代key，调用a.item可以迭代key和value，下面这种的输出结果是  （key,value）
a={1:'das','da':'hello'}
for j in a.items():
    print(j)

#另一种，输出结果是  key value
a={1:'das','da':'hello'}
for j,v in a.items():
    print(j,v)

#通过enumerate函数将索引和元素一起输出
a={'a','b','c'}
for i,v in enumerate(a):
    print(i,v)
#输出结果
0 A
1 B
2 C

#在python中同时引用两个变量是很正常的，当然，也可单独将这三个list输出
a=[[1,2],[3,4],[4,5]]
for j,v in a:
    print(j,v)
#输出结果
1 2
3 4
4 5

#列表生成式

#生成list [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
list(range(1, 11))

#生成[1x1, 2x2, 3x3, ..., 10x10]
[x * x for x in range(1, 11)]

#可加入判断语句
L = ['Hello', 'World', 16, 'Apple',None]
a=[s.lower for s in L if isinstance(s,str)]
print(a)
#输出结果：['hello', 'world', 'apple']

#两层循环，生成全排列
[m + n for m in 'ABC' for n in 'XYZ']
输出结果：['AX', 'AY', 'AZ', 'BX', 'BY', 'BZ', 'CX', 'CY', 'CZ']
#到了三层循环就比较少用了

#生成器（generator），保存的是算法而不是数据本身(打印的话会出来存储的地址)，语法与列表生成式相比只需把[]换成()，可用g.next()调用g的下一个，但是通常都用for循环
g=(x*x for x in range(1,11))
for n in g:
    print(n)

#函数式生成器，针对于相对复杂的算法
#一个生成斐波拉契数列的函数
def fib (max):
    a,b,n=0,1,0
    while n<max:
        print(b)
        a,b = b,a + b #这句相当于同时赋值，无先后顺序，是未改变之前的a,b
        
        n=n+1
    return

#只需将print(b)变成yield b
def fib (max):
    a,b,n=0,1,0
    while n<max:
        yield b
        a,b = b,a + b
        n=n+1
    return
for g in fib(6):
    print(g)
#杨辉三角
def fib():
   l=[1]
   yield l
   while True:
      l.append(0)
      l=[l[i]+l[i-1] for i in range(l.__len__())]
      yield l
n=0
for x in fib():
   print(x)
   n=n+1
   if n==10:
      break
#函数是顺序执行，遇到return语句或者最后一行函数语句就返回。而变成generator的函数，在每次调用next()的时候执行，遇到yield语句返回，再次执行时从上次返回的yield语句处继续执行。yield时返回值

```

- 凡是可作用于`for`循环的对象都是`Iterable`类型；
- 凡是可作用于`next()`函数的对象都是`Iterator`类型，它们表示一个惰性计算的序列；
- 集合数据类型如`list`、`dict`、`str`等是`Iterable`但不是`Iterator`，不过可以通过`iter()`函数获得一个`Iterator`对象。
- Python的`for`循环本质上就是通过不断调用`next()`函数实现的
- 可用`isinstance([],Iterator)` ` isinstance([],Iterable)` 判断是可迭代对象（iterable）还是迭代器（iterator） 



