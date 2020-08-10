<center><h1>
  raise方法
  </h1></center>

### 简介

python中通过raise方法来显示的引发异常，可以在必要的时候使用raise手动抛出异常，一旦执行了raise语句，方法体中在raise后面的语句将不再继续执行

### 语法

raise [exceptionName [(reason)]]

[]内容为可选参数

exceptionName：异常的类型参数标准异常中的一种

reason：异常描述，自定义字符串类型

```python
key = None

if key is None:
    raise NameError("shengmingcuowu")
```

### 用法

raise语句通常与try...except语句结合使用

```python
try:
    a = input("输入一个数字")
    if not a.isdigit():
        raise ValueError("输入必须是数字")
except ValueError as e:
    print("引发异常", repr(e))
```

### repr()

repr() 函数将对象转化为供解释器读取的形式。返回一个对象的 string 格式。