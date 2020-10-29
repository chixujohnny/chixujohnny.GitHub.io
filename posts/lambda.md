# lambda

在Python中有两种函数，一种是def定义的函数，另一种是lambda函数，也就是大家常说的匿名函数。今天我就和大家聊聊lambda函数，在Python编程中，大家习惯将其称为表达式。

# lambda基础

<br />lambda语句中，冒号前是参数，可以有多个，用逗号隔开，冒号右边的返回值。lambda语句构建的其实是一个函数对象，见证一下：<br />
<br />>>> foo = [2, 18, 9, 22, 17, 24, 8, 12, 27]<br />>>> print filter(lambda x: x % 3 == 0, foo)<br />[18, 9, 24, 12, 27]<br />>>> print map(lambda x: x * 2 + 10, foo)<br />[14, 46, 28, 54, 44, 58, 26, 34, 64]<br />>>> print reduce(lambda x, y: x + y, foo)<br />139<br />
<br />
<br />从这个简单的例子，我们可以看出，用lambda函数首先减少了代码的冗余，其次，用lambda函数，不用费神地去命名一个函数的名字，可以快速的实现某项功能，最后，lambda函数使代码的可读性更强，程序看起来更加简洁。

同时，使用lambda并不会降低运行效率。

# 经典用法


## 按照第x个元素排序

<br />如果数据形如：data = [('Mike',23), ('John',25), ('Ted',19), ('Lois',21)]，想对第二个成员“年龄”做一个升序
```python
sorted(data, key=lambda x:x[1], reverse=False)
# 升序：reverse=False（默认）
# 降序：reverse=True
```
如果想对名字做降序：
```python
sorted(data, key=lambda x:x[0], reverse=True)
```


## 求列表每项的平方

<br />求列表 list_x = [1, 2, 3, 4, 5, 6, 7, 8]，每项的平方
```python
list_x = [1, 2, 3, 4, 5, 6, 7, 8]
r = map(lambda x:x*x, list_x)
print(list(r))
-----------------------------------------
# 输出：
[1, 4, 9, 16, 25, 36, 49, 64]
```
