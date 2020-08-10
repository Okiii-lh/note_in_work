<center><h1>
  python 开发环境问题汇总
  </h1></center>

### 1、pip安装遇到权限问题 windows

pip install --user 包名

#### 2、ApplePersistenceIgnoreState: Existing state will not be touched

终端运行：

defaults write org.python.python ApplePersistenceIgnoreState NO