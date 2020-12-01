<center><h1>mysql笔记</h1></center>

#### 修改配置文件

```bash
sudo vim /etc/mysql/mysql.conf.d/mysqld.cnf 
```

#### mysql服务重启

```bash
/etc/init.d/mysql restart
```

#### 第一次安装没设置密码无法登陆解决办法

```bash
sudo cat /etc/mysql/debian.cnf
```

查看文件中的用户名和密码，使用配置文件中的用户名和密码进行登录，登录进入数据库之后再创建用户名和密码