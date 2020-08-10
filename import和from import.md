<center><h1>
  import和from import区别
  </h1></center>

### import

import datetime时引入整个的datetime包，如果使用datetime包中的datetime类，需要加上模块名的限定

Import datetime

print(datetime.datetime.now())

若不加模块名限定会出现错误

### from datetime import datetime

只是引入datetime包里的datetime类，在使用时无需添加模块名的限定

from datetime import datetime

print(datetime.now())

