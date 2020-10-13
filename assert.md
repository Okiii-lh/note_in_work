<center><h1>
  断言
  </h1></center>

### 简介

assert用于判断一个表达式，在表达式条件为 false 的时候触发异常。

断言可以在条件不满足程序运行时直接抛出异常，而不需要等待程序运行后出现崩溃的情况

### 使用

语法：assert expression [, arguments]

```python
import sys
# 判断当前系统环境是否是linux，若不是，则直接抛出异常
assert ('linux' in sys.platform), "该程序只能在linux下运行"

输出异常为：
Traceback (most recent call last):
  File "/Users/liuhe/PycharmProjects/learn_in_work/repr_and_str/test.py", line 21, in <module>
    assert ('linux' in sys.platform), "该程序只能在linux下运行"
AssertionError: 该程序只能在linux下运行
```

断言