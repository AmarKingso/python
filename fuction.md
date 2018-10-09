python的第一次学习笔记，关于函数，主要关于参数类型

# Fuction
- 定义
```
def func_name():
  func_body
```
          
## Paramenter
  - 普通参数
  - 默认参数
  - 关键词参数
  - 收集参数

### 普通参数
None

### 默认参数
参数带默认值，调用时可缺省，同C

### 关键词参数
- 不像前两种调用时要按照形参顺序，在调用函数时可用关键词调用
- 举例
```
def func(name="None", age=0, gender="unknow"): #定义函数
  pass
    
func(gender="male", age=18, name="amar")  #调用函数
```
### 收集参数
- 普通收集参数
  - 格式
  ```
  def func(*args): #定义函数
    pass

  func(a,b,c...)  #调用函数
  ```
  \*args相当于一个tuple，调用时使用的实参会被装入其中

  - 举例
  ```
  def func(*agrs):
    print(type(agrs))
    for i in agrs:
      print(i)

  func("amar", 18, "male", "sysu")
  ```
  运行结果为  
  <class 'tuple'>  
  amar  
  18  
  male  
  sysu  

**初学易错：定义函数时忘记加":"**

- 关键字收集参数
  - 格式
  ```
  def func(**kwargs): #定义参数
    pass
   
  func(a=value1, b=value2, .....)   #调用参数
  ```
  \*\*kwargs实际为dict，调用时也按dict方式调用
  - 举例
  ```
  def func(**kwagrs):
	print(type(kwagrs))
	for i,j in kwagrs.items():
		print(i," : ",j)

  func(name="amar", age=18, gender="male", university="sysu")
  ```
  运行结果为  
  <class 'dict'>  
  name  :  amar  
  age  :  18  
  gender  :  male  
  university  :  sysu  
  
**上述两种函数都可以缺省**

- 解包问题  
  假设有一列表
  ```
  l = ["amar", 18, "male", "sysu"]
  ```
  若调用上述普通收集参数例子中的函数，形如
  ```
  func(l)
  ```
  得到的结果为  
  ["amar", 18, "male", "sysu"]
  如果想将列表中的元素分开扔进去，就要用下列形式调用：
  ```
  func(*l)
  ```
  
  关键词收集参数同理，不过要两个“*”号
  
### 混合使用各种参数的顺序
- 先写普通，再普通收集（tuple），再关键词，再关键词收集（dict）  
举例
```
def func(hobby, *args, address="xxx", **kwargs):
  pass
```

## 函数文档
- 用法  
定义函数的第一行使用一对三引号，中间书写函数说明  

- 查看方法  
```
help(func)

#or

func.__doc__
```

- 举例
```
def func(hobby1, *agrs, hobby2="swim"):
    '''
    这里是函数的帮助文档
    '''
    print(type(agrs))
    print("我的爱好是{0}和{1}".format(hobby1,hobby2))
    for i in agrs:
    print(i)

help(func)
print("#" * 30)
print(func.__doc__)
```
得到结果  
Help on function func in module __main__:  
func(hobby1, \*agrs, hobby2='swim')  
    这里是函数的帮助文档  
##############################  
	这里是函数的帮助文档  
