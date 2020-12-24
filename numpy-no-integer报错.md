### 报错代码

AttributeError: module 'numpy' has no attribute 'integer'（2）

### 报错原因

当前环境中有多个版本numpy，没有全部卸载再安装，直接使用现存的numpy会报次错误

### 解决办法

写在掉当前环境中所有的numpy，再重新安装即可