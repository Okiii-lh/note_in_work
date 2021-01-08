### 问题

树莓派 can't connect to HTTPS URL because the SSL module is not availab

### 解决办法

删除之前编译安装好的python

重新安装openssl和openssl-devel

```bash
sudo apt-get install openssl
sudo apt-get install openssl-devel
```

安装之后再重新安装python

