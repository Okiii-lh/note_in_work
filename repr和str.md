<center><h1>
  repr函数和str函数的区别
  </h1></center>

### 相同点

两者都是将任意值转化为字符串

repr(object)

Str(object)

### 区别

str() 用于将值转化为适于人阅读的形式

repr() 转化为供解释器读取的形式。

对于数值类型、列表类型，str和repr方法的处理是一致

对于字符串类型，str和repr方法处理方式不一样。

repr函数得到的字符串，通常可以用来重新获取到该对象，适合于开发和调试阶段

```python
obj = "yes"
print(obj == eval(repr(obj)))
True
```

而str函数没有该功能，只适用于print输出

两者输出也不同

```python
print(repr("hello"))

print(str("hello"))

repr输出 'hello'
str输出   hello
```

### eval函数

eval() 函数用来执行一个字符串表达式，并返回表达式的值。

\>>> x = 7 

\>>> eval( '3 * x' ) 

21

