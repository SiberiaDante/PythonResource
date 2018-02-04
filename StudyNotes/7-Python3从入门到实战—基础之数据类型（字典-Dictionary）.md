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
* 向已有的字典中增加键值对
```
    dict = {'name' : 'SiberiaDante' , 'age' : 18  , 'address' : 'China'}
    print(dict) # 结果 ：{'name': 'SiberiaDante', 'age': 18, 'address': 'China'}
    dict['language']='Python'
    print(dict) # 结果 ： {'name': 'SiberiaDante', 'age': 18, 'address': 'China','language':'Python'}
```

## 删除字典
* 删除字典中的单个元素：dict[key]
```
    dict = {'name' : 'SiberiaDante' , 'age' : 18  , 'address' : 'China'}
    print(dict) # 结果 ： {'name': 'SiberiaDante', 'age': 18, 'address': 'China'}
    del dict['name']
    print(dict) # 结果 ： { 'age': 18, 'address': 'China'}
```
* 删除一个字典： del dict
```
    dict = {'name' : 'SiberiaDante' , 'age' : 18  , 'address' : 'China'}
    del dict
```
* 清空字典：dict.clear()
```
       dict = {'name' : 'SiberiaDante' , 'age' : 18  , 'address' : 'China'}
       print(dict) # 结果 ： {'name': 'SiberiaDante', 'age': 18, 'address': 'China'}
       dict.clear() 
       print(dict)  # 结果：{}
```
## 字典内置函数&方法
* 函数
```
    len(dict)   计算字典元素个数，即键的总数。	
    str(dict)   输出字典，以可打印的字符串表示。	
    type(variable)  返回输入的变量类型，如果变量是字典就返回字典类型。
```
* 方法
```
    dict.clear() 删除字典内所有元素
    dict.copy()  返回一个字典的浅复制
    dict.fromkeys()  创建一个新字典，以序列seq中元素做字典的键，val为字典所有键对应的初始值
    dict.get(key, default=None)  返回指定键的值，如果值不在字典中返回default值
    key in dict 如果键在字典dict里返回true，否则返回false
    dict.items() 以列表返回可遍历的(键, 值) 元组数组
    dict.keys()  以列表返回一个字典所有的键
    dict.setdefault(key, default=None)   和get()类似, 但如果键不存在于字典中，将会添加键并将值设为default
    dict.update(dict2)   把字典dict2的键/值对更新到dict里
    dict.values()    以列表返回字典中的所有值
    pop(key[,default])  删除字典给定键 key 所对应的值，返回值为被删除的值。key值必须给出。 否则，返回default值。
    popitem()   随机返回并删除字典中的一对键和值(一般删除末尾对)。
```

## 字典和列表对比
* 和list比较，dict有以下几个特点：
    * 查找和插入的速度极快，不会随着key的增加而变慢；
    *需要占用大量的内存，内存浪费多；
* 和dictionary相比，list的特性：
    * 查找和插入的时间随着元素的增加而增加；
    * 占用空间小，浪费内存很少；