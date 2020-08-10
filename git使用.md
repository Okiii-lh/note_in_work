<center><h1>git使用</h1></center>

### 上传到远程库

git init

git remote add origin git@github.com:O k iii-lh/Test.git

git add .

git commit -m"备注信息"

git push -u origin master

### 问题1 更新被拒绝，因为您当前分支的最新提交落后于其对应的远程分支

在github上创建项目，并开始第一次上传时会出现该问题

主要原因是远程库与当前库内容不一致，需要先将远程库的readme等文件保存到本地库，再进行更新

git pull origin master --allow-unrelated-histories

### 问题2 git fatal: 拒绝合并无关的历史的错误解决

使用git pull origin master --allow-unrelated-histories

### 问题3 退出vim

在使用git时，会弹出vim编辑

连按两次大写Z即可退出

### 问题4 您尚未完成合并(MERGE_HEAD存在)

使用git stash