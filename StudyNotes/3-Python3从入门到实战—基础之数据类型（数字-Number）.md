
# 2-Python3从入门到实战—基础之数据类型（数字-Number）


Python3 中有六个标准的数据类型：
>* Number（数字）
>* String（字符串）
>* List（列表）
>* Tuple（元组）
>* Sets（集合）
>* Dictionary（字典）

#### Number(数字)
>* Python3 支持 int、float、bool、complex（复数）。
```
int:	1,5,10,500,10000...
float： 0.0,52.0,-66.66,88.8E-88...
bool:True,False
complex:3.14j,20+3j,-652+8j,3e+6j...
```
>* 在Python 3里，只有一种整数类型 int，表示为长整型，没有 python2 中的 Long。
>* 内置的 type() 函数可以用来查询变量所指的对象类型 
```
print(type(20))#输出结果：<class 'int'>
print(type("SiberiaDante"))#输出结果：<class 'str'>
print(type(True))#输出结果：<class 'bool'>
print(type(20+3j))#输出结果：<class 'complex'>
```






注意：在 Python2 中是没有布尔型的，它用数字 0 表示 False，用 1 表示 True。到 Python3 中，把 True 和 False 定义成关键字了，但它们的值还是 1 和 0，它们可以和数字相加。