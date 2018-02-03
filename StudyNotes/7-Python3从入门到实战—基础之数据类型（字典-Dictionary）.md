# 7-Python3从入门到实战—基础之数据类型（字典-Dictionary）

## 字典的定义
* 字典是另一种可变容器模型，且可存储任意类型对象；使用键-值（key-value）存储，具有极快的查找速度；
字典的每个键值(key=>value)对用冒号(:)分割，每个对之间用逗号(,)分割，整个字典包括在花括号({})中
```
    语法格式：{ key1 : value1, key2 : value2, key3 : value3 ...}
    users={' 张三 ' : 18 , ' 李四 ' : 19 , ' 王五 ' : 20 , ' 赵六 ' : 19}
```
* 字典的键必须是唯一的，并且值的数据类型是不可变的，但值可以使任意的或者重复的；
```
    # 编号作为键，键唯一，值可变
    users={ 1 :' 张三 '  , 2 :' 李四 ' , 3 :' 王五 '  , 4 :' 张三 ' }
```

## 访问字典里的值
* 访问字典中的值使用 dict[键]
```
    dict = {'name' : ' SiberiaDante ' , ' age ' : 18  , ' address' : ' China '}
    print(dict['name']  # 结果 ：SiberiaDante
```

## 修改字典
* 根据字典中的键修改字典中的值
```
    dict = {'name' : ' SiberiaDante ' , ' age ' : 18  , ' address' : ' China '}
    print(dict['age'])  # 输出：18
    dict [ ' age ' ] = 20
    print(dict['age'])  # 输出： 20
```
* 向已有的字典中增加键值对(注意，默认输出是排序过的)
```
    dict = {'name' : 'SiberiaDante' , 'age' : 18  , 'address' : 'China'}
    print(dict) # 结果 ： {' address': ' China ', 'name': ' SiberiaDante ', ' age ': 18}
    dict['language']='Python'
    print(dict) # 结果 ： {' address': ' China ', 'language': 'Python', 'name': ' SiberiaDante ', ' age ': 18}
```

## 删除字典
* 删除字典中的单个元素
```

```




## 字典与列表的区别