# 5-Python3从入门到实战—基础之数据类型（列表-List）

## [Python从入门到实战系列——目录](https://github.com/SiberiaDante/PythonResource/blob/master/README.md)

## 列表定义
* list：列表（list）是Python内置的一种数据类型，list是一种有序的集合，索引从0开始，可以进行截取、组合等；
```
    //创建列表
    list1 = [1,2,3,4,5]
    list2 = ["Java","C++","Python","Kotlin"]
    print(list1[0]) # 结果：1
    print(list2[2]) # 结果：Python
```

## 获取列表中的数据
* 读取列表中某一个数据：list[索引]
```
    list = ["Java","C++","Python","Kotlin"]
    print(list[0]) # 结果：Java
    print(list[2]) # 结果：Python
```
* 倒叙读取列表中某一个数据：list[-索引]
```
    list = ["Java","C++","Python","Kotlin"]
    print(list[-2]) # 结果：Python
```
* 截取列表中的某一部分数据：list[索引：索引]
```
    list = ["Java","C++","Python","Kotlin"]
    print(list[0:3])   # 结果：["Java","C++","Python"]
```
* 截取列表中的某一项开始之后的所有数据：list[索引：]
```
    list = ["Java","C++","Python","Kotlin"]
    print(list[1:])   # 结果：["C++","Python","Kotlin"]
```

## 修改列表中的数据
* 更新列表数据，使用 list[索引]=数值 更新
* 添加列表项，使用 append（）方法
```
    list  = ["Java","C++","Python","Kotlin"]
    # 修改 C++ 为 C
    list[1] = "C"
    print(list) # 结果：["Java","C","Python","Kotlin"]
    # 在上面输出的list的基础上追加一个 PHP
    list.append("PHP")
    print(list) # 结果：["Java","C","Python","Kotlin","PHP"]
```

## 删除列表元素
* del语句：删除列表的元素
```
    list = ["Java","C++","Python","Kotlin","PHP"]
    del list[4] 
    print(list) # 结果：["Java","C++","Python","Kotlin"]
```
* remove（obj）：移除列表中某个值的第一个匹配项
```
    list = ["Java","C++","Python","Kotlin","C++"]
    list.remove("C++")
    print(list) # 结果：["Java","Python","Kotlin","C++"]
```

## 列表操作符
>* +号:用于组合列表
>* *号:用于重复列表;
>* len(列表) ：获取列表的长度
>* in:判断元素是否在列表中
```
    list1 = ["Java","C++","Python"]
    list2 = ["Kotlin","PHP"]
    list = list1 + list2
    print(list) # 结果： ["Java","C++","Python","Kotlin","PHP"]
    print(list1*2)  # 结果：["Java","C++","Python"，"Java","C++","Python"]
    print(len(list))    # 结果：5
    print("Java" in list)   # 结果： True
```

## 嵌套列表
* 嵌套列表即在列表里创建其它列表：list[list1,list2]
```
    list1 = [1,2,3,1]
    list2 = ["Java","C++","Python"]
    list = [list1,list2]
    print(list) # 结果：[[1,2,3,1],["Java","C++","Python"]]
```

## 列表函数&方法
* 函数
```
    len(list)   返回列表元素个数
    max(list)   返回列表元素最大值
    min(list)   返回列表元素最小值
    list(seq)   将元组转换为列表
```
* 方法
```
    list.append(obj)    在列表末尾添加新的对象
    list.count(obj) 统计某个元素在列表中出现的次数
    list.extend(seq)    在列表末尾一次性追加另一个序列中的多个值（用新列表扩展原来的列表）
    list.index(obj) 从列表中找出某个值第一个匹配项的索引位置
    list.insert(index, obj) 将对象插入列表
    list.pop(obj=list[-1])  移除列表中的一个元素（默认最后一个元素），并且返回该元素的值
    list.remove(obj)    移除列表中某个值的第一个匹配项
    list.reverse()  反向列表中元素
    list.sort([func])   对原列表进行排序
    list.clear()    清空列表
    list.copy() 复制列表
```