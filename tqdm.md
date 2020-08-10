<center><h1>tqdm 模块</h1></center>

### 简介

tqdm是python的一个可扩展的进度条库，可以在长循环中加入tedm来显示当前进度

只需要封装任意的迭代器即可

### 使用

#### 直接使用

Tqdm(iterator)

```python
from time import sleep
from tqdm import tqdm

for i in tqdm(range(1000)):
    sleep(0.01)
```

#### 使用封装好的range()

```python
import time
from tqdm import tqdm
from tqdm.std import trange

for j in trange(100):
    time.sleep(0.1)
```

### 任意列表

```python
alist = list('letters')
bar = tqdm(alist)
for letter in bar:
    time.sleep(1)
    bar.set_description(f"Now get {letter}")
```

