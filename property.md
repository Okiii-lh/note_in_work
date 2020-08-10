<center><h1>
  @property
  </h1></center>

@property用来实现对属性进行封装，封装成getter、setter方法，使得属性不能直接使用对象.属性的形式来访问，必须通过get、set方法来进行访问，使得编码更加规范，同时使用set方法对属性的赋值进行约束。

```python
class Student(object):

    @property
    def score(self):
        return self.score

    @score.setter
    def score(self, value):
        """
        score的set方法 可在此方法中对score的赋值进行约束
        :param value: score值
        :return:
        """
        if not isinstance(value, int):
            raise ValueError("数据类型错误")


student = Student()
#实际转换为student.set_score(60)
student.score = 60
# 实际转换为 student.get_score()
print(student.score)
```

还可以定义只读属性，只设定getter方法，不设定setter方法即可

```python
class Student(object):
    def __init__(self, age):
        self.age = age

    @property
    def age(self):
        return self.age
```

