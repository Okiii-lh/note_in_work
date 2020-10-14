<center><h1>No Module named 'nms.cpu_nms'</h1></center>

先确定路径是否正确

#### 解决方案

把cpu_nms.pyx替换为cpu_nms.py

这样就可以用了

#### gpu_nms.pys 报同样的错误

直接将gpu相关代码注释掉，只用cpu，后续补充