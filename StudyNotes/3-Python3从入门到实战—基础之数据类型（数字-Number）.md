# 3-Python3从入门到实战—基础之数据类型（数字-Number）

## [Python从入门到实战系列——目录](https://github.com/SiberiaDante/PythonResource/blob/master/README.md)

Python3 中有六个标准的数据类型：
>* Number（数字）
>* String（字符串）
>* List（列表）
>* Tuple（元组）
>* Sets（集合）
>* Dictionary（字典）

## Number(数字)
* Python3 支持三种不同的数值类型： int（整型）、float（浮点型）、complex（复数）；
* 整型（Int），是正或负整数，不带小数点，int没有限制大小，表示为长整型，在Python 3里，只有一种整数类型 int，没有 python2 中的 Long；
* 浮点型(float) - 浮点型由整数部分与小数部分组成，浮点型也可以使用科学计数法表示（2.5e2 = 2.5 x 102 = 250）；
* 复数( (complex)) - 复数由实数部分和虚数部分构成，可以用a + bj,或者complex(a,b)表示， 复数的实部a和虚部b都是浮点型；
```
int:	1,5,10,500,10000...
float： 0.0,52.0,-66.66,88.8E-88...
bool:True,False
complex:3.14j,20+3j,-652+8j,3e+6j...
```

## 数字类型转换
>* int(x) 将x转换为一个整数。
>* float(x) 将x转换到一个浮点数。
>* complex(x) 将x转换到一个复数，实数部分为 x，虚数部分为 0。
>* complex(x, y) 将 x 和 y 转换到一个复数，实数部分为 x，虚数部分为 y。x 和 y 是数字表达式。
```
a = 1.0
b = 2
print(int(a))        #输出结果：1
print(float(b))      #输出结果：2.0
print(complex(a))    #输出结果：(1+0j)
print(complex(a,b))  #输出结果：(1+2j)
```
## 数学函数
```
2 + 2       # 结果 4
10 + 2 * 2  # 结果 14
10 / 2      # 结果 5.0
10 // 2     # 结果 5
10.0 // 2   # 结果 5.0
```

## 数学常量
* 数学常量 pi：表示圆周率，一般以π来表示
* 数学常量 e：e即自然常数（自然常数）。

> 注意：在 Python2 中是没有布尔型的，它用数字 0 表示 False，用 1 表示 True。到 Python3 中，把 True 和 False 定义成关键字了，但它们的值还是 1 和 0，它们可以和数字相加。