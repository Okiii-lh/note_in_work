<center>pycharm sftp连接不到远程服务器</center>

#### 问题描述

pycharm在使用sftp远程连接乌班图服务器时发生request failed，但是使用ssh可以连接到

#### 解决办法

服务器端sftp没有配置

修改sshd_config

```bash
vim /etc/ssh/sshd_config
```

找到如下配置语句：

```bash
#Subsystem	sftp	/usr/lib/openssh/sftp-server
```

在下面添加配置语句

```bash
Subsystem	sftp	internal-sftp
```

修改完成后保存退出，重启服务

```bash
service sshd restart
```

完成