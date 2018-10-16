# 引言  
关于python中的list,dict,set,tuple的一些小知识点

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

#多重循环内涵
b = [10,20,30]
c = [n*m for m in a for n in b]
#c为a与b中各元素相乘
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

- 声明  
```
t = () #创建空元组
t = (value,) #创建有一个元素的元组，","不可省，否则为int类型，括号可以省
t = (value1,value2,...) #多个元素，括号可以省
t = tuple(list) #类型转化
```  
  
  
**小知识点**  
python中交换两个变量的快捷写法
```
a=1
b=3

a,b = b,a
```

# set
- 声明  
```
a = set()
#or
a = {value1,value2,...}#如果block内不写值，则a为dict
```

- 要点  
  - 内涵（与list一致）
  - 无序（所以无分片、索引）
  - 内部只能放可哈希数据（tuple,dict）
  - 函数
    - 添加元素，add
    - 删除元素，discard（无值不报错）,remove（无值报错）
    - 其余与list基本一致
  - 集合函数
    - intersection
    - difference（可以直接两个set相减）
    - union
    - issubset
    - issuperset
   
  - frozen set  
  不可被更改的集合
  ```
  s = frozenset()
  ```
  
# dict
- 声明
```
a = {}
a = {key1:value1,key2:value2,...}
a = dict(key1=value1,key2=value,...)
```

- 要点
  - 无序序列（无分片、索引）
  - key必须是可哈希值，value无所谓
  - 函数  
  del:del dict_name(key)  
  items()  
  keys()  
  values()  
  get(key，value = None) ：有key返回对应value，无则返回默认的value
  fromkeys(list_name,value)
  - 生成式（类似list的内涵）
  ```
  d = {"a":1,"b":2,"c":3}
  d1 = {k:v for k,v in d.items() (if....)}
  ```
