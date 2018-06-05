# 10-Python3从入门到实战—基础之函数

## [Python从入门到实战系列——目录](https://github.com/SiberiaDante/PythonResource/blob/master/README.md)

## 函数的定义
* 函数是组织好的，可重复使用的，用来实现单一，或相关联功能的代码段。
* 函数的语法
```
    def 函数名（参数列表）:
        函数体
```

>   函数代码块以 def 关键词开头，后接函数标识符名称和圆括号 ();      
    任何传入参数和自变量必须放在圆括号中间，圆括号之间可以用于定义参数。        
    函数的第一行语句可以选择性地使用文档字符串—用于存放函数说明。             
    函数内容以冒号起始，并且缩进。     
    return [表达式] 结束函数，选择性地返回一个值给调用方。不带表达式的return相当于返回 None。
* 定义一个简单的函数
```
    def showmsg():
        print("定义一个简单的函数")
        return
```
* 定义一个含参数的函数
```
    def showmsg1(msg):
        print(msg)
        return
```
* 函数的调用
```
    # 调用以上两个函数
    showmsg()
    showmsg1("这是一个带参数的函数")
```
输出结果：
> 定义一个简单的函数     
  这是一个带参数的函数

## 函数的参数
> Python 中调用函数时可使用的正式参数类型：  
    1.必需参数    
    2.关键字参数   
    3.默认参数    
    4.不定长参数 
  
* 必需参数须以正确的顺序传入函数；调用时的数量必须和声明时的一样；
```
def showmsg2(msg):
    print(msg)
    return
showmsg2("必传参数")
showmsg2()	
```
showmsg2("必传参数")	输出结果：
> 必传参数
showmsg2()	报错：
> TypeError: showmsg2() missing 1 required positional argument: 'msg'

* 关键字参数允许函数调用时参数的顺序与声明时不一致
```
def showusermsg(name, age):
    print('name is ', name, '---age is ', age)
    return
showusermsg(age=18, name='SiebriaDante')
```
输出结果：
> name is  SiebriaDante ---age is  18

* 默认参数:调用函数时，如果没有传递参数，则会使用默认参数;
```
def showusermsg(name, age=18):
    print('name is ', name, '--- age is ', age)
    return
showusermsg(name='SiebriaDante')
```
输出结果：
> name is  SiebriaDante --- age is  18

* 不定长参数:能处理比当初声明时更多的参数,声明时不会命名;不定长参数使用星号（*）标记
```
def shownumber(msg, *num):
    print(msg)
    for x in num:
        print(x)
shownumber("开始输出不定长参数：",10,20,30,40)
```
输出结果：
> 开始输出不定长参数：
10	
20	
30	
40	

##  参数传递
>   在 python 中，类型属于对象，变量是没有类型的：       
    在 python 中，strings, tuples, 和 numbers 是不可更改的对象，而 list,dict 等则是可以修改的对象;
* 传递不可变对象实例，传递的只是实例的值，没有影响实例对象本身
```
    def changenumber(a):
        a = 10
    
    b = 20
    changenumber(b)
    print(b)
```
输出结果：
> 20
* 传递可变对象实例，传递是把对象本身传过去，改变对象的值，同时也是改变函数外对象的值
```
    def changelist(mlist):
        mlist.append([1, 2, 3.4, 5])
        print('函数内读取 mlist 的值：', mlist)
        return
    mlist = [10, 20, 30]
    changelist(mlist)
    print('函数外读取 mlist 的值：', mlist)
```
输出结果：
    > 函数内读取 mlist 的值： [10, 20, 30, [1, 2, 3.4, 5]]  
      函数外读取 mlist 的值： [10, 20, 30, [1, 2, 3.4, 5]]
  
## 匿名函数
* Python 使用 lambda 来创建匿名函数；

    > lambda的主体是一个表达式，而不是一个代码块。仅仅能在lambda表达式中封装有限的逻辑进去。     
       lambda 函数拥有自己的命名空间，且不能访问自己参数列表之外或全局命名空间里的参数。

* 语法 
    > lambda [arg1 [,arg2,.....argn]]:expression

```
sum = lambda arg1, arg2: arg1 + arg2;
# 调用sum函数
print ("相加后的值为 : ", sum( 10, 20 ))
print ("相加后的值为 : ", sum( 20, 20 ))
```
输出结果：
> 相加后的值为 :  30  
  相加后的值为 :  40

## 变量作用域
* 变量的作用域决定了在哪一部分程序可以访问哪个特定的变量名称；Python的作用域一共有4种，分别是：
```
    L （Local） 局部作用域
    E （Enclosing） 闭包函数外的函数中
    G （Global） 全局作用域
    B （Built-in） 内建作用域
```
> 作用域优先级由高到低： L ——> E ——> G ——> B
```
    b_count = 99999  # 内建作用域
    g_count = 0  # 全局作用域
    def outer():
        e_count = 1  # 闭包函数外的函数中
        def inner():
            l_count = 2  # 局部作用域
```
* Python 中只有模块（module），类（class）以及函数（def、lambda）才会引入新的作用域，其它的代码块（如 if/elif/else/、try/except、for/while等）是不会引入新的作用域的，也就是说这这些语句内定义的变量，外部也可以访问，如下代码：
```
    >>> if True:
    ...     msg = 'my name is SiberiaDante'
    ...
    >>> msg
    'my name is SiberiaDante'
    >>>
```
>  msg 变量定义在 if 语句块中，外部可以访问

```
    >>> def showmsg():
    ...     msg_def='my name is SiberiaDante'
    ...
    >>> msg_def
    Traceback (most recent call last):
      File "<stdin>", line 1, in <module>
    NameError: name 'msg_def' is not defined
    >>>
```
> msg_def 定义在函数中，是局部变量，外部不能访问

## 全局变量和局部变量
定义在函数内部的变量拥有一个局部作用域，定义在函数外的拥有全局作用域；
局部变量只能在其被声明的函数内部访问，而全局变量可以在整个程序范围内访问。调用函数时，所有在函数内声明的变量名称都将被加入到作用域中。如下实例：
```
    total = 0; # 这是一个全局变量
    def sum( arg1, arg2 ):
        total = arg1 + arg2; # total在这里是局部变量.
        print ("函数内是局部变量 : ", total)
        return total;
    #调用sum函数
    sum( 10, 20 );
    print ("函数外是全局变量 : ", total)
```
输出结果：
> 函数内是局部变量 :  30        
  函数外是全局变量 :  0

## global 和 nonlocal关键字
当内部作用域想修改外部作用域的变量时，需要使用global和nonlocal关键字声明
* 简单使用 global 关键字声明
```
    >>> num = 1314
    >>> def showNum():
    ...     global num
    ...     print(num)
    ...     num = 520
    ...     print(num)
    ...
    >>> showNum()
    1314
    520
    >>>
```
* 外层非全局作用域时，修改变量需要使用 nonlocal 关键字
```
    >>> def outer():
    ...     num=1314
    ...     def inner():
    ...             nonlocal num
    ...             print(num)
    ...             num = 520
    ...             print(num)
    ...     inner()
    ...
    >>> outer()
    1314
    520
    >>>
```

## 递归函数
* 在函数内部调用函数本身，即为递归函数；
```
    def voidTe(num):
        if num == 1:
            return 1
        return num * voidTe(num - 1)
    print(voidTe(10))
```
输出结果
> 3628800
* 递归函数的优点是定义简单，逻辑清晰；但是，在计算机中，函数调用是通过栈（stack）这种数据结构实现的，每当进入一个函数调用，栈就会加一层栈帧，每当函数返回，栈就会减一层栈帧。由于栈的大小不是无限的，所以，递归调用的次数过多，会导致栈溢出；