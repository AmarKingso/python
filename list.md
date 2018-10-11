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

**To be continue**
