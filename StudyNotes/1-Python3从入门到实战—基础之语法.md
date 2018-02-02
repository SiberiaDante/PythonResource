# 1-Python3从入门到实战—基础之语法

## [Python从入门到实战系列——目录](https://github.com/SiberiaDante/PythonResource/blob/master/README.md)

## 编码格式
* 默认情况下，Python 3 源码文件以 UTF-8 编码，所有字符串都是 unicode 字符串
```
# -*- coding=utf-8 -*-
```

* 也可以为源码文件指定不同的编码
```
# -*- coding: cp-1252 -*-
```
* 指定编码格式的正则
```
^[ \t\v]*#.*?coding[:=][ \t]*([-_.a-zA-Z0-9]+)
```

## 标识符
>* 第一个字符必须是字母表中字母或下划线'_';
>* 标识符的其他的部分有字母、数字和下划线组成;
>* 标识符对大小写敏感;

## Python保留字
* 保留字即关键字，不能把关键字用作任何标识符名称 ;执行Python命令查看Python保留字
```
>>> import keyword
>>> keyword.kwlist
['False', 'None', 'True', 'and', 'as', 'assert', 'break', 'class', 'continue', '
def', 'del', 'elif', 'else', 'except', 'finally', 'for', 'from', 'global', 'if',
 'import', 'in', 'is', 'lambda', 'nonlocal', 'not', 'or', 'pass', 'raise', 'retu
rn', 'try', 'while', 'with', 'yield']
>>>
```
	
## 注释
* 单行注释使用 # 
```
# Python单行注释
```
* 多行注释使用多个 # 或者 使用''' 和 """ 包裹
```
# 多行注释
# 多行注释
# 多行注释

'''
多行注释
多行注释
多行注释
'''

"""
多行注释
多行注释
多行注释
"""
```
## 输出语句
* 输出语句使用 print()
```
print("Hello World!")
```
* print 默认输出是换行的，如果要实现不换行需要在变量末尾加上 end=""：
```
print("Hello",end="")
print("World")
```

## 代码块的表示
* Python 中使用缩进来表示代码块，不需要使用大括号({})；
```
if True:
    print ("True")
else:
    print ("False")
```
* 缩进的空格数是可变的，但是同一个代码块的语句必须包含相同的缩进空格数；如果缩进的空格数不一致，会导致运行错误：
```
if True:
    print ("True")
else:
    print ("Answer")
  print ("False")    # 缩进不一致，会导致运行错误
```

## 多行语句表示
* Python中通常是一行一条语句，但如果语句很长，我们可以使用反斜杠(\)来实现多行语句；
```
total = item_one + \
        item_two + \
        item_three
```
* 特殊情况下，如在 [], {}, 或 () 中的多行语句，不需要使用反斜杠(\)；
```
number = ['1', '2', '3',
        '4', '5']
```

## 同一行显示多条语句
* Python可以在同一行中使用多条语句，语句之间使用分号(;)分割；
```
print ("Hello");print ("World");print ("!");
```

## 多个语句构成代码组
* 缩进相同的一组语句构成一个代码块，称之代码组；像if、while、def和class这样的复合语句，首行以关键字开始，以冒号( : )结束，该行之后的一行或多行代码构成代码组。我们将首行及后面的代码组称为一个子句(clause)
```
if expression : 
   suite
elif expression : 
   suite 
else : 
   suite
```
## 空行
* 函数之间或类的方法之间用空行分隔，表示一段新的代码的开始；

## 数据类型
* python中数有四种类型：整数、长整数、浮点数和复数。
>* 整数， 如 1
>* 长整数 是比较大的整数
>* 浮点数 如 1.23、3E-2
>* 复数 如 1 + 2j、 1.1 + 2.2j

## 字符串
* python中使用单引号或者双引号定义一个字符串;
```
name = "SiberiaDante"
name = 'SiberiaDante'
```
* 使用三引号('''或""")可以指定一个多行字符串;
```
info = ''' name is SiberiaDante,
age is 18,
gender is man'''

info = """ name is SiberiaDante,
age is 18,
gender is man"""
```
* 引号可以使用转义符 '\'标识；
```
# 输出结果：name is "SiberiaDante"
print("name is \"SiberiaDante\"")
```
* 自然字符串， 通过在字符串前加r或R
```
# 输出结果：name is \"SiberiaDante\"
print(R"name is \"SiberiaDante\"")
```
* python允许处理unicode字符串，加前缀u或U， 如 u"this is an unicode string"。
* 字符串是不可变的。

## import 与 from...import
* 在 python 用 import 或者 from...import 来导入相应的模块。
>* 将整个模块(somemodule)导入，格式为： import somemodule
>* 从某个模块中导入某个函数,格式为： from somemodule import somefunction
>* 从某个模块中导入多个函数,格式为： from somemodule import firstfunc, secondfunc, thirdfunc
>* 将某个模块中的全部函数导入，格式为： from somemodule import *

