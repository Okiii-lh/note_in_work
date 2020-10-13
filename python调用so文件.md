<center><h1>python调用so文件</h1></center>

```python
from ctypes import cdll

cur = cdll.LoadLibrary(path)

cur.function()
```

