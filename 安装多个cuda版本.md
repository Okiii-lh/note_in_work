### 问题描述

使用conda安装多个版本的cuda

### 解决办法

直接使用conda安装即可

```python
# 安装cuda
conda install cudatool-kit=10.0
# 安装cudnn
conda install cudnn=7.0. -c https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/main/linux-64/
```

