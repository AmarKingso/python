# 引言  
关于python中的list,dict,set的一些小知识点

# list  
- 创建方式
```
a = [value1, value2, ....]
#or
a = [i for i in range(value1, value2)] #list内涵
#or
a = list(range(value1, value2)) #用list函数将数据转化为list类型
```

- list遍历  
用for循环,eg:
```
a = [1,2,3,4,5]
for i in a:
  print(i)

#嵌套列表的遍历（特定）
a = [[1,2,3],[4,5,6],[7,8,9]]
for i,j,k in a:
  print(i,j,k)

'''
结果为：
123
456
789
'''
```

- list内涵(list content)  
复制列表可用如下方式：
```
a = [1,2,3,4,5]
b = [i for i in a]

#如果只想取a中的奇数，可用如下方式
b = [i for i in a if i%2 == 1]

#如果想使b中元素都为a的十倍
b = [i*10 for i in a]
```

- list分片  
  - 格式[:]  
  - 举例
  ```
  a = [1,2,3,4,5]
  b = [:] #b与a内容一致
  b = [1:3] #b为a的1到2号元素(不包含3号)
  b = [1:4:2] #1到3号元素，步长为2
  b = [-3:-1] #倒数第3号元素到倒数第2号，b=[3,4]
  b = [-1:-3:-1] #倒数第1到倒数第2，b=[5,4]
  ```

- list运算  
两列表相加，相当于将两个列表连接在一起整合成一个列表  
列表乘法，如:
```
a = [1,2,3]
b = a * 2
#b为[1,2,3,1,2,3]
```

- list中的函数  
len()  
max() and min()  
list()  
append(value)  
insert(index,value)  
pop()  
remove(value) #删除list中所有value,没有则报错  
count(value) #list中value出现的次数  
clear()  
extend(list)  
copy() #浅拷贝  

- 浅拷贝例子  
```
a = [1,2,3,[4,5,6]]
b = a.copy()
#a与b的id不同，但是a[3]与b[3]的id相同
```

# tuple  
- 定义  
可看成不可更改的list,操作基本与list一致

- 创建  
```
t = () #创建空元组
t = (value,) #创建有一个元素的元组，","不可省，否则为int类型，括号可以省
t = (value1,value2,...) #多个元素，括号可以省
t = tuple(list) #类型转化
```
