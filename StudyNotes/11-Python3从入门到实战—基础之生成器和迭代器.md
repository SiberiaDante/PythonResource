# 11-Python3从入门到实战—基础之生成器和迭代器

## [Python从入门到实战系列——目录](https://github.com/SiberiaDante/PythonResource/blob/master/README.md)

## 切片
Python提供切片（Slice）操作符用来获取列表、元组等数据中的部分元素；如，读取列表
> list[m:n]:表示获取m-n区间的元素        
> list[m:n:o]:表示以条件o获取m-n之间的元素
```
num = list(range(100))  # 创建0-99的列表num
```
中部分元素：
* 获取language中前三个元素
```
>>> num[0:3]
['0', '1', '2']
>>> num[:3]    # 索引从0开始时，0可以省略
['0', '1', '2']
```
* 获取language中后三个元素
```
>>> num[-3:]
['97', '98', '99']]
```
* 每隔10个数获取所有元素
```
>>> num[::5]
[0, 10, 20, 30, 40, 50, 60, 70, 80, 90]
```
* 复制一个列表
```
>>> num[:]
[0, 1, 2, 3, 4, 5, 6...98,97]
```

## 迭代
Python 中通过for循环来遍历list或tuple，这种遍历称为迭代（Iteration）；
* 迭代的使用
```
>>> user={'0':'张三','1':'李四','2':'王五','3':'赵六',}
>>> for key in user:
...     print(key)
>>> print('---------分割线-----------')
>>> for value in user.values():
...     print(value)
```
输出结果：
>   0   
    1   
    2   
    3   
    ---------分割线-----------     
    张三  
    李四  
    王五  
    赵六  

* 判断对象是否可迭代
```
>>> user={'0':'张三','1':'李四','2':'王五','3':'赵六',}
>>> print(isinstance(1,Iterable))
>>> print(isinstance(user,Iterable))
```
输出结果：
> False     
  True
  
* 遍历输出对象的下标和值
```
>>> user={'0':'张三','1':'李四','2':'王五','3':'赵六',}
>>> for key,value in enumerate(user.values()):
...     print(key,value)
```
输出结果：
> 0 张三      
  1 李四      
  2 王五      
  3 赵六      
  
## 迭代器
迭代器是一个可以记住遍历的位置的对象；迭代器对象从集合的第一个元素开始访问，直到所有的元素被访问完结束；迭代器只能往前不会后退；

迭代器有两个基本的方法：创建迭代器对象的 iter() 和 输出迭代器对象的下一元素的 next()；
* 基本使用
```
>>> nums = [1,2,3,4]
>>> num = iter(nums)
>>> print(next(num))
>>> print(next(num))
>>> print(next(num))
```
输出
> 1     
  2      
  3     
  
* 迭代器结合 for 循环使用
```
>>> nums = [1,2,3,4]
>>> num = iter(nums)
>>> for n in num:
...     print(n)
```
输出结果：
> 1     
  2     
  3     
  4     

* 迭代器结合 while 循环使用
```
>>> while True:
...     try:
...         print(next(num))
...     except StopIteration:
...         print("迭代完毕")
...         sys.exit()
```
输出：
> 1     
  2     
  3     
  4     
  迭代完毕      
  
## 列表生成式
* 生成列表的方法
```
>>> list(range(10))
[0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
```
* 原始生成[1*1,2*2,...,10*10]方法
```
>>> for x in range(1,11):
...     l.append(x*x)
...
>>> l
[1, 4, 9, 16, 25, 36, 49, 64, 81, 100]
>>>
```
* 使用Python内置强大的生成[1*1,2*2,...,10*10]列表的方法
```
>>> [x * x for x in range(1,11)]
[1, 4, 9, 16, 25, 36, 49, 64, 81, 100]
>>>
```
* 生成[1*1,2*2,...,10*10]元素为偶数的列表
```
>>> [x * x for x in range(1,11) if x % 2 ==0]
[4, 16, 36, 64, 100]
```
* 双重循环生成列表
```
>>> [x + y for x in 'ABC' for y in 'abc']
['Aa', 'Ab', 'Ac', 'Ba', 'Bb', 'Bc', 'Ca', 'Cb', 'Cc']
```
* 使用两个变量生成列表
```
>>> str = {'x': 'A', 'y': 'B', 'z': 'C' }
>>> [key + '=' + value for key, value in str.items()]
['x=A', 'y=B', 'z=C']
```
## 生成器
通过列表生成式可以生成一个列表，但是列表受内存限制，容量是有限的，并且，如果创建一个包含几百万元素的列表，而只需要使用其中元素时便造成了空间浪费；
这时候就应该使用生成器（generator）；生成器表达式能做的事情列表解析基本都能处理，只不过在需要处理的序列比较大时，列表解析比较费内存。
* 创建一个生成器
```
>>> gen = (x * x for x in range(10))
>>> gen
<generator object <genexpr> at 0x0000000002742E08>
>>>
```
* 读取生成器中的元素
```
>>> for x in gen:
...     print(x)
...
0
1
4
9
16
25
36
49
64
81
>>>
```


### 生成器函数 
生成器函数：在函数中如果出现了yield关键字，那么该函数就不再是普通函数，而是生成器函数；
* 使用函数实现斐波拉契数列
```
def fib(max):
    n, a, b = 0, 0, 1
    while n < max:
        print(b)
        a, b = b, a + b
        n = n + 1
    return 'done'
```
```
>>> fib(6)
1
1
2
3
5
8
'done'
```
* 使用生成器函数实现斐波拉契数列
```
def fib(max):
    n, a, b = 0, 0, 1
    while n < max:
        yield b
        a, b = b, a + b
        n = n + 1
    return 'done'
```
```
>>> for n in fib(6):
...     print(n)
...
1
1
2
3
5
8
```
* generator和函数的执行流程不一样。函数是顺序执行，遇到return语句或者最后一行函数语句就返回。而变成generator的函数，在每次调用next()的时候执行，遇到yield语句返回，再次执行时从上次返回的yield语句处继续执行。

