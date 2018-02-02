# 5-Python3从入门到实战—基础之数据类型（列表-List）

## [Python从入门到实战系列——目录](https://github.com/SiberiaDante/PythonResource/blob/master/README.md)

## 列表定义
* list：列表（list）是Python内置的一种数据类型，list是一种有序的集合，索引从0开始，可以进行截取、组合等；
```
    //创建列表
    list1 = [1,2,3,4,5]
    list2 = ["Java","C++","Python","Kotlin"]
    
    print(list1[0]) # 结果：1
    print(list1[2]) # 结果：Python
```

## 获取列表中的数据
* 读取列表中某一个数据：list[索引]
* 截取列表中的某一部分数据：list[索引：索引]
```
    //创建列表
    list1 = [1,2,3,4,5]
    list2 = ["Java","C++","Python","Kotlin"]
    
    print(list1[0]) # 结果：1
    print(list1[2]) # 结果：Python
    print(list1[0:3])   # 结果： [1,2.3]
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
>* + 号用于组合列表，* 号用于重复列表;
>* len(列表) ：获取列表的长度
>* in:判断元素是否在列表中
>* 
>* 
```
    list1 = ["Java","C++","Python"]
    list2 = ["Kotlin","PHP"]
    list = list1 + list2
    print(list) # 结果： ["Java","C++","Python","Kotlin","PHP"]
    print(list1*2)  # 结果：["Java","C++","Python"，"Java","C++","Python"]
    print(len(list))    # 结果：5
    print("Java" in list)   # 结果： True
```
