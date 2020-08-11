<center><h1>python 开发问题汇总</h1></center>

### 1、cannot assign module before Module.__init__() call

#### 翻译

【error】在初始化函数调用前不能分配模块

#### 原因

调用了自定义的类，但是 在自定义的类的__init__函数下面没有写super(类名, self).__init__() 

#### 解决办法

```python
class CombatNN(nn.Module):
    def __init__(self, dimi, dimh, dimo):
        """
        网络结构
        三层全连接前向网络
        一层输入层
        两层隐藏层
        一层输出层
        relu作为激活函数
        :param dimi: 输入维数
        :param dimh: 隐藏层维数
        :param dimo: 输出维数
        """
        // 要记得加入super()
        super(CombatNN, self).__init__()
        self.fc1 = nn.Linear(dimi, dimh)
        self.fc2 = nn.Linear(dimh, dimh)
        self.fc3 = nn.Linear(dimh, dimo)
        self.relu = nn.ReLU()
```



### 2、RuntimeError: Integer division of tensors using div or / is no longer supported

#### 报错信息

 RuntimeError: Integer division of tensors using div or / is no longer supported and in a future release div will perform true division as in Python 3. Use true_divide or floor_divide (// in Python) instead.

#### 翻译

不再支持使用div或/对张量进行整数除法，在未来的版本中，div将像Python 3一样执行真正的除法。使用true_divide或floor_divide (Python中的//)代替。

#### 原因

Pytorch 1.16不再支持直接的 / 运算

#### 解决办法

使用 // 代替原来的 / 

```python
# 旧语句
print('Accuracy of the network on the 1000 test images: %d %%' % (100*correct/total))
#																															 使用 // 代替 原来的 /
# 新语句
print('Accuracy of the network on the 1000 test images: %d %%' % (100*correct // total))
```



### 3、IndexError: invalid index of a 0-dim tensor. Use tensor.item() to convert a 0-dim tensor to a Python

#### 翻译

0-dim张量的索引无效。使用tensor.item()将0-dim张量转换为Python

#### 原因

对于0-维 tensor， .item()方法，返回Python number。

#### 解决办法

```python
# 旧语句
if(i+1) % 100 == 0:
    print("Epoch[%d/%d], Step[%d/%d], Loss:%.4f" %
          (epoch+1, num_epochs, i+1, len(train_dataset)/batch_size, loss.data[0])
# 使用loss.item()代替原来的loss.data[0]的写法
# 新语句
if(i+1) % 100 == 0:
    print("Epoch[%d/%d], Step[%d/%d], Loss:%.4f" %
          (epoch+1, num_epochs, i+1, len(train_dataset)/batch_size, loss.item()))
```



### 4、TypeError: ToTensor() takes no arguments

#### 翻译

类型错误:ToTensor()不带参数

#### 原因

ToTensor是个方法不是个类属性

#### 解决办法

加上括号()

```python
# 旧语句
test_dataset = dsets.MNIST(root='./data', train=False, transform=transforms.ToTensor)
# 新语句 transforms.ToTensor()  要加方法的括号
test_dataset = dsets.MNIST(root='./data', train=False, transform=transforms.ToTensor())
```



### 5、ImportError: sys.meta_path is None, Python is likely shutting down

gym的游戏在不写env.close()关掉游戏的话会出现此问题，解决办法就是加上env.close()

```python
env = gym.make('CartPole-v0')

env.reset()

for _ in range(1000):
    env.render()
    env.step(env.action_space.sample())

env.close()
```



### 6、TypeError: 'CombatAgent' object is not subscriptable

subscriptable的意思是 可有下标的

所以这就话的意思就是对象不应该具有下标，检查一下报错的那一行带了下标的应该就能找到了。

一般是数组名写错了，写成了类型



### 7、i++ i--

python中可没有++ -- 操作



### 8、AttributeError: 'tuple' object has no attribute 'dim'

Linear（）层输入的数据结构不正确所导致



### 9、size mismatch, m1: [9 x 1], m2: [10 x 100]

输入维数与网络结构不符



### 10、AttributeError: numpy.ndarray object has no attribute dim

使用numpy对数组进行操作之后的类型为ndarry，不能负荷pytorch的输出，需要使用torch.Tensotr()对数组进行处理

```python
out = np.append([1, 0], np.append(state, state_))
out = torch.Tensor(out)
```



### 11、unsupported operand type(s) for +: 'numpy.ndarray' and 'Tensor'

忘记怎么解决的了

参考文献：https://stackoverflow.com/questions/27841916/unsupported-operand-types-for-numpy-ndarray-and-str



### 12、Can't call numpy() on Tensor that requires grad. Use tensor.detach().numpy() instead.

出现这个现象的原因是：待转换类型的PyTorch Tensor变量带有梯度，直接将其转换为numpy数据将破坏计算图，因此numpy拒绝进行数据转换，实际上这是对开发者的一种提醒。如果自己在转换数据时不需要保留梯度信息，可以在变量转换之前添加detach()调用。	

将weight_diff_return有Tensor转换为numpy类型

```python
weight_diff_return.detach().numpy()
```

