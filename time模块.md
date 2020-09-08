<center><h1>
  python time类
  </h1></center>
#### 代码设置当前时间以便查看

```python
import time

dt = time.localtime()
print(time.strftime("%H:%M:%S", dt))
```

