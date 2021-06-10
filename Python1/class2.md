## Turtle-101

> 上课时间：2021-06-12  13:20-14:50

[toc]

官方文档：[Turtle](https://docs.python.org/3/library/turtle.html)

### Turtle绘图窗体
注意width、height、startx、starty
![1.png](https://i.loli.net/2021/06/10/u46Jt2oeKNzwAUi.png)

### Turtle坐标系
原点在画布正中间
![2.png](https://i.loli.net/2021/06/10/wpy9rYAHR7gvuXk.png)

### 命令讲解（重点）
#### 设置绘图窗体大小
`turtle.setup(width,height,startx,starty)`
**例如**：turtle.setup(800, 600, 0, 0)
**解释**：设置窗体宽800像素，高600像素，位于屏幕左上角

#### 画笔前进
`turtle.forward()` 或者 `turtle.fd()`
**例如**：turtle.forward(200)
**解释**：沿着当前方向前进200像素

#### 画笔后退
`turtle.back()` 或者 `turtle.bk()`
**例如**：turtle.back(200)
**解释**：后退（当前方向的反方向）200像素

#### 设置颜色
##### 设置画笔颜色
`turtle.pencolor()`
**例如**：turtle.pencolor("green")
**解释**：设置画笔颜色为绿色

##### 设置填充颜色
`turtle.fillcolor()`
**例如**：turtle.fillcolor("red")
**解释**：设置填充颜色为红色

##### 设置画笔、填充颜色
`turtle.color(pencolor, fillcolor)`
**例如**：turtle.color("green", "red")
**解释**：设置画笔颜色为绿色，并且设置填充颜色为红色

#### 开始填充
`turtle.begin_fill()`
**例如**：turtle.begin_fill()
**解释**：开始填充，在绘制需要填充的图形前使用

#### 结束填充
`turtle.end_fill()`
**例如**：turtle.end_fill()
**解释**：结束填充，在绘制需要填充的图形后使用

#### **绘制案例-1**
绘制一个边长200像素的正方形，边框绿色，填充蓝色
![微信截图_20210610155357.png](https://i.loli.net/2021/06/10/rvzH4C6WaSq2Tox.png)
```python
import turtle

turtle.color("green", "blue")
turtle.begin_fill()
turtle.fd(200)
turtle.right(90)
turtle.fd(200)
turtle.right(90)
turtle.fd(200)
turtle.right(90)
turtle.fd(200)
turtle.right(90)
turtle.end_fill()
```

#### 抬起画笔
`turtle.penup()` 或者 `turtle.up()`
**例如**：turtle.penup()
**解释**：抬起画笔。抬起画笔后移动，不会画出痕迹


#### 放下画笔
`turtle.pendown()` 或者 `turtle.down()`
**例如**：turtle.pendown()
**解释**：放下画笔。放下画笔后移动，才会画出痕迹

#### **绘制案例-2**
![微信截图_20210610160716.png](https://i.loli.net/2021/06/10/MJAjCvFEsh2yxi7.png)
绘制两个间隔30像素的正方形，左侧正方形边框蓝色，填充绿色，边长50；右侧正方形边框绿色，无填充，边长100

```python
import turtle

turtle.color("blue", "green")
turtle.begin_fill()
turtle.fd(50)
turtle.right(90)
turtle.fd(50)
turtle.right(90)
turtle.fd(50)
turtle.right(90)
turtle.fd(50)
turtle.right(90)
turtle.end_fill()

turtle.penup()
turtle.fd(80)
turtle.pendown()

turtle.pencolor("green")
turtle.fd(100)
turtle.right(90)
turtle.fd(100)
turtle.right(90)
turtle.fd(100)
turtle.right(90)
turtle.fd(100)
turtle.right(90)

turtle.done()
```
#### 清除画布
`turtle.clear()`
**例如**：turtle.clear()
**解释**：清除画布上的所有内容，注意画笔的位置和方向不会改变

#### 右转
`turtle.right()`
**例如**：turtle.right(90)
**解释**：右转90度（顺时针）

#### 左转
`turtle.left()`
**例如**：turtle.left(90)
**解释**：左转90度（逆时针）

#### 设置方向
`turtle.setheading()` 或者 `turtle.seth()`
**例如**：turtle.setheading(90)
**解释**：不管以前朝向哪个方向，设置画笔朝向90度方向（向上）

#### **绘制圆、圆弧、正多边形**
`turtle.circle(radius, extent=None, steps=None)`
##### 顺时针绘制圆
**例如**：turtle.circle(-30)
**解释**：如果radius为负数，那么圆心在右侧

##### 逆时针绘制圆
**例如**：turtle.circle(30)
**解释**：如果radius为正数，那么圆心在左侧

##### 圆弧
**例如**：turtle.circle(30, 270)
**解释**：画一个半径为30,270度的圆弧

##### 正多边形
**例如**：turtle.circle(30,steps=6)
**解释**：绘制一个六边形

#### **绘制案例-3**
阅读代码，在纸上画出来程序所绘制的图形
```python
import turtle
turtle.circle(30)
turtle.circle(-30)
turtle.goto(0,200)
turtle.circle(30, 270)
turtle.left(90)
turtle.forward(100)
turtle.fd(100)
turtle.circle(30,steps=6)
turtle.right(90)
turtle.forward(200)
turtle.left(90)
turtle.circle(-30,180,5)
```
#### 绘制点
`turtle.dot()`

**例如**：turtle.dot(20)
**解释**：绘制一个大小为20的点

**例如**：turtle.dot(20, "blue")
**解释**：绘制一个大小为20的点，颜色为蓝色

#### 撤销上一步
`turtle.undo()`
**例如**：turtle.undo()
**解释**：撤销上一步操作

代码举例：
```python
import turtle
for i in range(4):
    turtle.fd(50)
    turtle.lt(80)

for i in range(8):
    turtle.undo()
```

#### 控制绘制速度
`turtle.speed()`
**例如**：turtle.speed(9)
**解释**：设置绘制速度为9  可选范围0-10，其中0最大，1-9依次增大

#### 移到某点
`turtle.goto(x, y)` 或者 `turtle.setpos(x, y)` 或者 `turtle.setposition(x, y)`
**例如**：`turtle.goto(100, 200)`
**解释**：将画笔移到（100,200）坐标位置。如果画笔抬起，则不会有笔迹；如果画笔放下，则有笔迹。

##### 只改变x坐标
`turtle.setx()`
**例如**：turtle.setx(90)
**解释**：y坐标不动，将画笔移动到x坐标为90的位置

##### 只改变y坐标
`turtle.sety()`
**例如**：turtle.sety(90)
**解释**：x坐标不动，将画笔移动到y坐标为90的位置

#### **绘制案例-4**
绘制一个正方形
```python
import turtle

turtle.setx(90)
turtle.sety(-90)
turtle.setx(0)
turtle.sety(0)
```
#### 设置背景颜色
`turtle.bgcolor()`
**例如**：turtle.bgcolor("green")
**解释**：设置背景颜色为绿色

#### 隐藏画笔
`turtle.hideturtle()` 或者 `turtle.ht()`
**例如**：turtle.hideturtle()
**解释**：隐藏画笔

#### 显示画笔
`turtle.showturtle()` 或者 `turtle.st()`
**例如**：turtle.st()
**解释**：显示画笔

#### 控制画笔粗细
`turtle.pensize()`
**例如**：turtle.pensize(10)
**解释**：设置画笔大小为10

#### 画笔印章
`turtle.stamp()`
**例如**：turtle.stamp()
**解释**：画笔印章。返回一个整数，代表此位置的印章

#### 清除印章
`turtle.clearstamp()`
**例如**：turtle.clearstamp(9)
**解释**：删除指定位置的印章

### 绘图案例
#### 多个画笔
创建两个画笔，第一个画笔在第二象限绘制一个三角形，第二个画笔在第一个象限绘制一个半圆，绘制完成后隐藏画笔。图形均无填充。
![微信截图_20210610170431.png](https://i.loli.net/2021/06/10/UkCsT2PevYgb9Zr.png)
代码：
```python
import turtle

pen1 = turtle.Pen()
pen2 = turtle.Turtle()

pen1.penup()
pen1.goto(-100, 100)
pen1.pendown()

pen1.circle(30,steps=3)

pen2.penup()
pen2.goto(100,100)
pen2.pendown()

pen2.circle(30,steps=4)

pen1.ht()
pen2.ht()
```
#### 绘制笑脸
![微信截图_20210610171546.png](https://i.loli.net/2021/06/10/p23GIQK1BSjVDwd.png)
代码：
```python
import turtle

turtle.penup()
turtle.sety(-100)
turtle.pendown()
turtle.circle(100)
turtle.penup()
turtle.goto(-50,30)
turtle.pencolor("green")
turtle.pendown()
turtle.dot(20)
turtle.penup()
turtle.setpos(50,30)
turtle.color("red", "blue")
turtle.sety(20)
turtle.pendown()
turtle.begin_fill()
turtle.circle(12)
turtle.end_fill()
turtle.penup()
turtle.goto(-50,0)
turtle.goto(-50,-20)
turtle.pendown()
turtle.goto(0,-50)
turtle.goto(50,-20)
turtle.ht()
```
### 练习题目
#### 正方形内的圆
要求：
（1）画一个边长为200的正方形，里面嵌套一个直径为100的圆
（2）圆的填充颜色为蓝色，所有的线条为黑色。
（3）圆心位置为画布正中心。
代码：
```







```
#### 绘制靶心
要求：
绘制如下图形
![](http://www.liankexue.cn/linkscience/linkscience/1602740046633127642.png)
代码：
```







```

全国青少年等级考试-模拟题目：[链科学](https://liankexue.cn/grade)