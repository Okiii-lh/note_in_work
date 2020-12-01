<center>windows安装ssh</center>

### 客户端安装

开始 -> 应用与功能 -> 可选功能 -> 添加功能

列表中有OpenSSH客户端的选项

点击安装OpenSSH客户端

安装之后可使用Windows PowerShell直接使用ssh命令

### 服务端安装

开始 -> 应用与功能 -> 可选功能 -> 添加功能

列表中有OpenSSH服务器的选项

点击安装OpenSSH服务器

服务端安装完之后需要进行一些配置

### 服务端配置

使用管理员身份运行Windows PowerShell

1. 开启SSHD服务

   ```bash
   Start-Service sshd
   ```

   

2. 设置服务自动启动

   ```bash
   Set-Service -Name sshd -StartupType 'Automatic'
   ```

   

3. 确认防火墙是否开放

   ```bash
   Get-NetFirewallRule -Name *ssh*
   ```

   查看OpenSSH-Server-In-TCP的enable是否为True

4. 配置完成之后其他客户端可使用ssh连接windows，用户名和密码就是windows的用户名和密码