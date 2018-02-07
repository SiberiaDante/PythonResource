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
> 在 python 中，类型属于对象，变量是没有类型的：       
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

