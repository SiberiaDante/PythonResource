# 9-Python3从入门到实战—基础之条件控制语句

## 条件判断 if
* 条件判断 if 语句语法
```
    if <条件判断1>:
        <执行1>
    elif <条件判断2>:
        <执行2>
    elif <条件判断3>:
        <执行3>
    else:
        <执行4>
```
>* 每个条件后面要使用冒号（:），表示接下来是满足条件后要执行的语句块;
>* 使用缩进来划分语句块，相同缩进数的语句在一起组成一个语句块;
>* 在Python中没有switch – case语句;
```
    num = 5
    if num == 0:
        print('num = 0 ')
    elif num > 0:
        print('num 是一个正数')
    else:
        print('num 是一个负数')
```
```
    x="520"
    if x:
        print("x是非零数值、非空字符串、非空list等")
    else:
        print("False")
```
> 输出结果：x是非零数值、非空字符串、非空list等
```
    x=""
    if x:
        print("x是非零数值、非空字符串、非空list等")
    else:
        print("False")
```
> 输出结果：False

## 循环语句while
* 语法(在Python中没有do..while循环)
```
    while 判断条件：
        语句
```
* 计算 1-100 之间的数的和 
```
    sum = 0
    num = 0;
    while num < 100:
        sum += num
        num += 1
    print(sum)
```
> 输出结果：4950
* while 实现无限循环
```
    num1 = 0
    while num1 == 0:
        print(num1)
```
>num1 永远为 0 ，while 无限循环
* while 循环中使用 else 语句
```
    count = 0
    while count < 5:
        print(count, " 小于 5")
        count += 1
    else:
        print(count, " 大于或等于 5 ,结束循环")
```

>输出结果：  
>    0  小于 5    
>    1  小于 5    
>    2  小于 5    
>    3  小于 5    
>    4  小于 5    
>    5  大于或等于 5 ,结束循环

## 循环语句for
