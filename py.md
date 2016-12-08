```python
#py是一门动态语言（变量本身类型不固定的语言）
kk=100
kk='Hello world!'
print(kk)

#除法
print(10/3)
print(10//3)

    #缩进代表代码块
j=1000
if j>100:
    j+1
    print(j)
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

name=input()#输入
print('hello ',name)
```

