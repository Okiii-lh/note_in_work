<center><h1>
  conda常用命令整理
  </h1></center>

#### conda创建虚拟环境

conda create -n [env_name] [python=python_version]

#### conda列出所有虚拟环境

conda env list

conda info --envs

#### conda激活虚拟环境

conda activate [env_name]

#### conda退出虚拟环境

linux:source deactivate [env_name] 

windows:conda deactivate [env_name]

通用：deactivate

#### 共享环境

服务端：conda env export > environment.yml

生成yml文件

客户端：conda env create -f environment.yml

### 安装包

conda install [package_name]

### 卸载包

conda remove [package_name]

### 查看包版本

pip show [package_name]

### 查看当前环境所有包

conda list

