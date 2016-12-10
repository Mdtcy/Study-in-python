```python
#py是一门动态语言（变量本身类型不固定的语言）
kk=100
kk='Hello world!'
print(kk)

#可以将一个函数名作为右值，相当于给这个函数起一个别名 
a=fbs
a(-1)

#输入
name=input(‘可在这输入提示性语句’)
print(name)
#input()返回的是字符串，如果要输入数字与其他数字进行比较，需要强制类型转换
kk=int(input())

#for in
kk[1,2,3,A]
for k in kk :
    print(k);
    
#range(n) 生成一个从0开始到n-1的序列，可通过list()转换成list
jj=list(range(101))
sum=0
for j in jj:
    sum=sum+j
print(sum)
#while
uu=1
sum=0
while uu<=100:
    sum=sum+uu
    uu=uu+1
print(sum)
#break和continue在python中同样适用

#除法
print(10/3)
print(10//3)

 #缩进代表代码块
 #if else后要加冒号
 #elif 代表else if
j=1000
if j==100:
    j+1
elif j==1000:
     j+2
else:
     j+3
print("I\'m \"Jack\"")

#r''内的字符串不转义
print('\\\t\\')
print(r'\\\t\\')

#如果字符串内部有很多换行，用\n写在一行里不好阅读，为了简化，Python允许用'''...'''的格式表示多行内容
print("""line1
line2
line3""")
#多行字符串'''...'''还可以在前面加上r使用
print(r"""\t
\\
\t""")
      
#and or not
if not False:
    print(100+1)
```

- ***list与tuple***

  ``` python
  #list中的元素可以不同，甚至可以是一个新的list
  a=[1,2,'hello',[1,2]]

  #可以像数组一样操作list中的list
  a[3][1]=3

  #返回list中的元素个数
  len(a)

  #添加到末尾
  a.append();

  #插入到指定位置
  a.insert(1,'hello')

  #删除末尾元素
  a.pop();

  #删除指定位置
  a.pop[1]

  #tuple与list十分类似，但是一旦初始化就不可以再改变
  b=(1,2,'hello',[A,B,C],(1,2,3))

  #但是tuple中的list中的元素却可以改变，因为tuple只是直接指向的不变
  b[3][2]=b
  ```

- *dic与set*

  ```python
  #dic相当于map，键值存储,空间换时间，hash算法，key必须是不可变的，如字符串和整数，list不可以
  d={1:5,'mike':4}
  d[1]=67
  print(d[1])

  #可用get方法确保取得值时不发生错误，如果key不存在，则返回默认值none，或者可以自己设置一个默认值
  d.get(2)
  d.get(2,-3)

  #删除键
  d.pop('mike')

  #set与dic类似，存储一组不带值的key，key同样得是不可变对象
  #初始化时得传入一组list到set()中，其中的重复元素会被自动过滤
  s=set([1,2,'mike'，2])

  #添加key
  s.add('mk')

  #删除key
  s.remove(2)

  #set相当于数学意义上无序和无重复的一组集合，因此两个set可以做交集并集
  s1=set([1,2,3])
  s2=set([2,3,4])
  s1&s2 #交集
  s1|s2 #并集
  ```

- ***再议不可变对象***

  ```python
  a='abc'
  a.replace('a','A')
  b=a.replace('a','A')
  print(a)
  print(b)
  #结果 abc Abc

  #可以将a指向新的字符串
  a='kkk'

  #a实际上是一个变量，指向一个真正的字符串对象'abc',符串的replace方法时，实际上时返回了一个新创建的字符串
  #所以，对于不变对象来说，调用对象自身的任意方法，也不会改变该对象自身的内容。相反，这些方法会创建新的对象并返回，这样，就保证了不可变对象本身永远是不可变的。
  ```

  ![0.jpg](C:\Users\tktet\Desktop\0.jpg.png)


