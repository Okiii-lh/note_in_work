

### 1 生成私钥

```bash
ssh-keygen
```

### 2 上传公钥至服务器

```bash
ssh-copy-id -i ～/.ssh/id_rsa.pub root@192.168.x.x
```

### 3 直接使用用户名登录

```bash
ssh liuh@192.168.1.120
```

