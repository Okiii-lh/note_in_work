<center><h1>
 python输出日志
  </h1></center>

### logging模块

作用：用于将信息输出到日志文件当中

### logging级别

使用级别来表示事件的重要性

WARNING是默认级别，即在实际跑程序的时候，只有WARNING及以上的等级的信息才会被反馈

| 级别     | 使用状态                                                     |
| -------- | ------------------------------------------------------------ |
| DEBUG    | 详细信息，一般只在调试的阶段使用                             |
| INFO     | 证明按正常计划进行                                           |
| WARNING  | 某些没有预料到的事情发生，但对当前运行没有影响，但在未来可能有隐患，如内存不足 |
| ERROR    | 比较严重的问题，导致不能执行某些功能                         |
| CRITICAL | 严重错误，导致程序直接崩溃                                   |

### 级别对应的数字值

| 级别     | 数字值 |
| -------- | ------ |
| CRITICAL | 50     |
| ERROR    | 40     |
| WARNING  | 30     |
| INFO     | 20     |
| DEBUG    | 10     |
| NOTSET   | 0      |

### 打印到控制台

```python
import logging
logging.debug('debug 信息')
logging.warning('只有这个会输出。。。')
logging.info('info 信息')
```

只有等于或高于warning的日志信息才会被显示，因此上面的代码只会输出warning方法中的信息

### 保存到文件中

使用basicConfig()将日志写入到日志文件中

```python
logging.basicConfig(level=logging.DEBUG,#控制台打印的日志级别
                    filename='new.log',
                    filemode='a',##模式，有w和a，w就是写模式，每次都会重新写日志，覆盖之前的日志
                    #a是追加模式，默认如果不写的话，就是追加模式
                    format=
                    '%(asctime)s - %(pathname)s[line:%(lineno)d] - %(levelname)s: %(message)s'
                    #日志格式
                    )
```

### 既在控制台输出也写入到文件中

```python
import logging
from logging import handlers

class Logger(object):
    level_relations = {
        'debug':logging.DEBUG,
        'info':logging.INFO,
        'warning':logging.WARNING,
        'error':logging.ERROR,
        'crit':logging.CRITICAL
    }#日志级别关系映射
    
def __init__(self,filename,level='info',when='D',backCount=3,fmt='%(asctime)s - %(pathname)s[line:%(lineno)d] - %(levelname)s: %(message)s'):
    self.logger = logging.getLogger(filename)
    format_str = logging.Formatter(fmt)#设置日志格式
    self.logger.setLevel(self.level_relations.get(level))#设置日志级别
    sh = logging.StreamHandler()#往屏幕上输出
    sh.setFormatter(format_str) #设置屏幕上显示的格式
    th = handlers.TimedRotatingFileHandler(filename=filename,when=when,backupCount=backCount,encoding='utf-8')#往文件里写入#指定间隔时间自动生成文件的处理器
    #实例化TimedRotatingFileHandler
    #interval是时间间隔，backupCount是备份文件的个数，如果超过这个个数，就会自动删除，when是间隔的时间单位，单位有以下几种：
    # S 秒
    # M 分
    # H 小时、
    # D 天、
    # W 每星期（interval==0时代表星期一）
    # midnight 每天凌晨
    th.setFormatter(format_str)#设置文件里写入的格式
    self.logger.addHandler(sh) #把对象加到logger里
    self.logger.addHandler(th)
    
    if __name__ == '__main__':
    log = Logger('all.log',level='debug')
    log.logger.debug('debug')
    log.logger.info('info')
    log.logger.warning('警告')
    log.logger.error('报错')
    log.logger.critical('严重')
    Logger('error.log', level='error').logger.error('error')
```
