<center><h1>
  opencv 方法
  </h1></center>

### 说明

笔记记录opencv包常用的相关方法

### cv.circle()

在原始图像中画圆

```python
def circle(img: Any,
           center: Any,
           radius: Any,
           color: Any,
           thickness: Any = None,
           lineType: Any = None,
           shift: Any = None):
    
```

```python
import cv2 as cv

img = cv.imread("test.png")
# 在img原始图片中划圈，其圈的中心点为（520，430），半径=300，颜色为（255，0，0），粗细=8
cv.circle(img,(520,430),300,(255,0,0),8)  
```

thickness 如果是正数，表示组成圆的线条的粗细程度。否则，表示圆是否被填充

line_type 线条的类型。默认是8