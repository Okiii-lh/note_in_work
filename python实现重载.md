<center><h1>
  python 实现重载
  </h1></center>

### 简介

在python语法中，方法也是attribute，方法名就是key，所以在python中一个方法名只对应一个方法体，若写多个方法体而都是用同一个方法名，则会产生覆盖效果。

### 重载面向的场景

1. 参数类型不同
2. 参数数量不同

### 参数类型不同

python无法在语法上实现这种重载，只能在代码逻辑上实现

```python
def Aa(a=1, b=1):
	if type(a) == int and type(b) == float:
		print(1)
	elif type(a) == float and type(b) == int:
		print(2)
Aa(1, 1.0)
Aa(1.0, 1)
```

### 参数数量不同

针对参数数量不同，可以使用默认参数来实现，即给参数默认值，这样在接受参数时，就不会报错

```python
def Aa(a=1, b=1):
print(2)
# 无参数版本
Aa()
# 一个参数版本
Aa(1)
# 两个参数版本
Aa(1, 2)
```

 





