# 11-Python3从入门到实战之一些特性

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
>>>     print(key)
>>> print('---------分割线-----------')
>>> for value in user.values():
>>>     print(value)
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
>>>     print(key,value)
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
>>>     print(n)
```
输出结果：
> 1     
  2     
  3     
  4     

* 迭代器结合 while 循环使用
```
>>> while True:
>>>     try:
>>>         print(next(num))
>>>     except StopIteration:
>>>         print("迭代完毕")
>>>         sys.exit()
```
输出：
> 1     
  2     
  3     
  4     
  迭代完毕      
  
## 列表生成式

## 生成器
