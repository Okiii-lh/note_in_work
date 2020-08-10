<center><h1>Pytorch 笔记</h1></center>

### 1、nn.Linear()

#### 简介

用于设置网络中的全连接层

#### 使用方法

```python
torch.nn.Linear(in_features: int, out_features: int, bias: bool = True)
```

In_features: 输入维度

out_features: 输出维度

bias：是否需要偏置，默认为True

#### 备注

全连接层的输入和输出都是二维张量

而卷积成输入输出为四维张量

### 2、tensor与numpy互相转换

#### tensor 转换成 numpy

```python
import torch
import numpy as np

a = torch.ones(5)

print(a)

print(a.numpy())
```

转换后的tensor对象与numpy对象指向同一个地址，所以只要有一个有所修改，另一个也会跟着更新

#### numpy转换成 tensor

```python
c = np.ones(5)

d = torch.from_numpy(c)

print(c)
print(d)
```

### 3、梯度计算以及输出梯度

源码来自于MNIST识别手写数字

```python
net = Net(input_size, hidden_size, num_classes)
# 定义损失函数
criterion = nn.CrossEntropyLoss()
optimizer = torch.optim.Adam(net.parameters(), lr=learning_rate)

for epoch in range(num_epochs):
    for i, (image, labels) in enumerate(train_loader):

        images = Variable(image.view(-1, 28*28))
        labels = Variable(labels)

        # 梯度置零
        optimizer.zero_grad()
        # 正向传播一张照片
        outputs = net.forword(images)
        # 计算损失函数
        loss = criterion(outputs, labels)
        # 反向传播 计算梯度 此时还为进行梯度下降，此时可以输出梯度
        loss.backward()
        # 输出梯度
        # 输出第一层的权重梯度和偏置梯度
        print('dL/dw: ', net.fc1.weight.grad)  # 输出梯度
        print('dL/db: ', net.fc1.bias.grad)
        # 优化器进行优化
        # 进行梯度下降，对参数进行更新
        optimizer.step()

        if(i+1) % 100 == 0:
            print("Epoch[%d/%d], Step[%d/%d], Loss:%.4f" %
                  (epoch+1, num_epochs, i+1, len(train_dataset)/batch_size, loss.item()))
```

