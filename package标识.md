<center><h1>
  python __init__.py的作用
  </h1></center>

### package标识

python项目中，每个package都是一个目录，__init__.py的作用就是来标识这个文件是一个python目录，如果没有该文件，那么该package就不会被识别为一个目录。

### 用于模糊导入

Python中的包和模块有两种导入方式：精确导入和模糊导入

模糊导入中的*中的模块是由__all__来定义的，__init__.py的另外一个作用就是定义package中的__all__，用来模糊导入，如__init__.py：

``__all__ = ["Pack1Class","Pack1Class1"]``

