# 6-Python3从入门到实战—基础之数据类型（元组-Tuple）

## [Python从入门到实战系列——目录](https://github.com/SiberiaDante/PythonResource/blob/master/README.md)

## 元组的定义
* 定义元组只需要在括号中添加元素，并使用逗号隔开即可
```
    tup = ('Python','Java','C++','Kotlin')
```

## 元组与列表的区别
* Python 的元组与列表类似，不同之处在于元组的元素不能修改;
* 元组使用小括号，列表使用方括号;
* 元组中只包含一个元素时，需要在元素后面添加逗号，否则括号会被当作运算符使用
```
    tup1=(18)
    type (tup1) #结果：<type 'int'>
    tup2=(18),
    type (tup1) #结果：<type 'tuple'>
```

## 访问元组
* 类似于列表，元组使用下标索引来访问元组中的值；
```
    tup = ('Python','Java','C++','Kotlin')
    print（tup[0])   # 结果： Java
    print(tup[1:3]) # 结果： ('Java','C++')
```
* 倒叙读取元组中某一个元素：tuple[-索引]
```
    tup = ('Python','Java','C++','Kotlin')
    print(tup[-2])  # 输出：C++
```
* 截取元组中的某一项开始之后的所有元素：tuple[索引：]
```
    tup = ('Python','Java','C++','Kotlin')
    print(tup[1:])  # 输出： ('Java','C++','Kotlin')
```

## 拼接元组
* 不同于列表，元组中的元素值是不允许修改的，但可以对元组进行连接组合；
```
    tup1 = ('Python','Java','C++','Kotlin')
    tup2 = (1,2,3,4,5)
    tup = tup1 + tup2
    print(tup)  # 结果：('Python','Java','C++','Kotlin',1,2,3,4,5)
```

## 删除元组
* 不同于列表，元组中的元素值是不允许删除的，但可以使用del语句来删除整个元组
```
    tup = ('Python','Java','C++','Kotlin')
    del tup
    print(tup)
```
* 元组被删除后，输出异常信息如下：
```
    Traceback (most recent call last):
      File "<stdin>", line 1, in <module>
    NameError: name 'tup' is not defined
```

## 元组函数
```
    len(tuple)   计算元组元素个数。
    max(tuple)   返回元组中元素最大值。
    min(tuple)   返回元组中元素最小值。
    tuple(seq)   将列表转换为元组。
```



