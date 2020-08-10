<center><h1>
  type和isinstance
  </h1></center>

### isinstance

isinstance用来判断一个对象是否是已知类型，类似type

```python
isinstance(object, classinfo)
```

- object -- 实例对象。
- classinfo -- 可以是直接或间接类名、基本类型或者由它们组成的元组。如果是元组，则意味着判断是否是元组中的一个

### type

type() 函数如果你只有第一个参数则返回对象的类型，三个参数返回新的类型对象。

```python
type(object)
type(name, bases, dict)
```

- name -- 类的名称。
- bases -- 基类的元组。
- dict -- 字典，类内定义的命名空间变量。

### isinstance() 与 type() 区别：

- type() 不会认为子类是一种父类类型，不考虑继承关系。
- isinstance() 会认为子类是一种父类类型，考虑继承关系。

如果要判断两个类型是否相同推荐使用 isinstance()。

