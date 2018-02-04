# 8-Python3从入门到实战—基础之数据类型（集合-Sets）

## 集合的定义
* 集合（set）和字典类似，也是一组key的集合，但不存储value；由于key不能重复，所以，在set中，没有重复的key。
* 创建一个set，需要提供一个list作为输入集合：
```
    list=[1,2,3,4]
    s = set(list)
    print(s)    # 结果：{1,2,3,4}
```
* 使用元组创建一个set
```
    tup=('Java','Python','Kotlin')
    s = set(tup)
    print(s)    # 结果：{'Kotlin', 'Python', 'Java'}
```
* 集合中重复元素会被自动过滤
```
    s = set([1,2,1,2,3,3,4])
    print(s)    # 结果：{1,2,3,4}
```

## 集合中添加/删除元素
* 使用add（key）向集合中添加元素
```
    s = set([1,2,3,4])
    s.add(9)
    print(s)    # 结果 ：{1,2,3,4,9}
```
* 使用remove（key）删除集合中的元素
```
    s = set([1,2,3,4])
    s.remove(4)
    print(s)    # 结果 ：{1,2,3}
```
## 集合操作
```
    s1 = set([1,2,3,4,5])
    s2 = set([1,3,5,7,9])
    print(s1 & s2)  # 结果：{1,3,5}
    print(s1 | s2)  # 结果：{1,2,3,4,5,7,9}
    print(s1 - s2)  # 结果：{2,4}
    print(s1 == s2) # 结果：False
    print(s1 != s2) # 结果：True
    print(s1 in s2) # 结果：False
    print(s1 not in s2) # 结果：True
```
