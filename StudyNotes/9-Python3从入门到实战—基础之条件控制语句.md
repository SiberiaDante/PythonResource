# 9-Python3从入门到实战—基础之条件控制语句

## [Python从入门到实战系列——目录](https://github.com/SiberiaDante/PythonResource/blob/master/README.md)

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
* for 循环格式
```
    for <variable> in <sequence>:
        <statements>
    else:
        <statements>
```
* for 循环可以遍历任何序列的项目，如一个列表或者一个字符串等
```
    language = ['Java', 'C', "Python", 'Kotlin']
    for x in language:
        print(x)
    else:
        print("没有找到对应的语言")
```
> Java  
  C 
  Python    
  Kotlin    
  没有找到对应的语言 

## break 的使用
* break 语句可以跳出 for 和 while 的循环体
* break 在for 循环中
```
    for letter in 'SiberiaDante':
        if letter == 'D':
            print('这个字母', letter, '有毒，跳出循环')
            break
        print('当前字母是 ', letter)
```
> 输出结果：  
  当前字母是  S  
  当前字母是  i  
  当前字母是  b  
  当前字母是  e  
  当前字母是  r  
  当前字母是  i  
  当前字母是  a  
  这个字母 D 有毒，跳出循环
* break 在while循环中
```
    num = 10
    while num > 0:
        print('-----:', num)
        num = num - 1
        if num == 5:
            print('num = ', num, '终止循环')
            break
```
> 输出结果：  
  -----: 10     
  -----: 9  
  -----: 8  
  -----: 7  
  -----: 6  
  num =  5 终止循环
  
## continue 的使用
* continue 语句跳过当前循环块中的剩余语句，继续进行下一轮循环；
* continue 在 for 循环中的使用
```
    for let in 'SiberiaDante':
        if let == 'D' or let == 'a':
            continue
        print('当前字母：', let)
```
>   输出结果：     
    当前字母： S     
    当前字母： i     
    当前字母： b     
    当前字母： e     
    当前字母： r     
    当前字母： i     
    当前字母： n         
    当前字母： t     
    当前字母： e     
* continue 在 while 循环中的使用
```
    num = 6
    while num > 0:
        num = num - 1
        if num == 3:
            continue
        print('当前数字为：', num)
```
>   输出结果：       
    当前数字为： 5    
    当前数字为： 4    
    当前数字为： 2    
    当前数字为： 1    
    当前数字为： 0    

## pass 的使用
* pass是空语句，一般用做占位语句，不做任何事情，是为了保持程序结构的完整性
```
    for letter in 'SiberiaDante': 
       if letter == 'D':
          pass
          print ('执行 pass 块')
       print ('当前字母 :', letter)
    print ("Good bye!")
```
>   输出结果：   
    当前字母 : S    
    当前字母 : i    
    当前字母 : b    
    当前字母 : e    
    当前字母 : r    
    当前字母 : i    
    当前字母 : a    
    执行 pass 块   
    当前字母 : a    
    当前字母 : n    
    当前字母 : t    
    当前字母 : e    
    Good bye!   
    
## return 语句
* return [表达式] 语句用于退出函数，选择性地向调用方返回一个表达式；不带参数值的return语句返回None；
```
    def sum( arg1, arg2 ):
       total = arg1 + arg2
       return total;
    
    # 调用sum函数
    total = sum( 10, 20 );
    print ("调用sum函数返回结果 : ", total)
```
输出结果：
> 调用sum函数返回结果 :  30
