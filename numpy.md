<center><h1>
  numpy使用笔记
  </h1></center>

### 1、随机数

#### np.random.rand(n, m)

随机生成n行m列的均匀分布的随机数

#### np.random.randm(n, m)

生成n行m列的符合正态分布的随机数

#### np.randint(low, high, size, dtype)

生成随机整数

low：最小值；high：最大值；size：数据个数

#### 随机选取内容

#### np.random.choice(a, size=None, replace=True, p=None)

从a中随机选取元素，组成大小为size的数组，a必须为一维的

replace：表示能否取相同的数字

p：与数组a对应，表示数组a中各个元素的选取概率，默认为每个元素的选取概率相同

### 2、数组操作

#### 数组合并

水平合并

### 3、numpy与array互相转换

#### array转换为numpy

```python
test = [1, 2, 3, 4]

print(np.array(test))
```



#### numpy 转换为array

```python
test = np.ones(5)

print(test.tolist())
```



### 4、np.linspac

np.linspac()用来创建一个等差数列

numpy.linspace(start, stop, num=50, endpoint=True, retstep=False, dtype=None, axis=0)

#### 参数含义：

start：样本数据开始点

stop：样本数据结束点

num=50：生成的样本数量，默认为50

endpoint：生成的数列是否包含stop

retstep：是否给出数据间隔

dtype：数据类型