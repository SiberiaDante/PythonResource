# 14-Python3从入门到实战—高级之输入输出

## [Python从入门到实战系列——目录](https://github.com/SiberiaDante/PythonResource/blob/master/README.md)

## 几种输出
* print 输出
```
print('hello world')
```
> 输出结果：hello world

* str()： 函数返回一个用户易读的表达形式
```
hello='hello world'
print(str(hello))
print(str(1/6))
```
> 输出结果：
> 
> hello world
> 
> 0.16666666666666666

* repr()： 产生一个解释器易读的表达形式
```
hello='hello world'
print(repr(hello))
```
> 输出结果：'hello world'

## str.format() 格式化输出结果
* {}以及里面的字符会被format对应的内容替换
```
print('{}请访问:{}'.format('学习更多内容', 'https://github.com/SiberiaDante/PythonResource'))
```
> 学习更多内容请访问https://github.com/SiberiaDante/PythonResource

* 可以使用{0}指定索引；
```
print('{1}请访问：{0}'.format('https://github.com/SiberiaDante/PythonResource','学习更多内容'))
```
> 学习更多内容请访问https://github.com/SiberiaDante/PythonResource

* ':' 和格式标识符联合使用
```
print('常量 PI 的值是：{}'.format(math.pi))
print('常量 PI 的值是：{:.3f}'.format(math.pi))
```
> 常量 PI 的值是：3.141592653589793
> 
> 常量 PI 的值是：3.142

## 读取键盘输入内容
* Python提供了 input() 函数读取输入的文本，，并将结果返回
```
name=input('请输入你的名字：')
print('你输入的名字是：',name)
```
> 请输入你的名字：SiberiaDante
> 
> 你输入的名字是： SiberiaDante

## 读写文件操作
* open(filename, mode)
    * filename:文件名称；
    * mode:文件的打开模式，只读，写入，追加等；
* f.read()：读取一个文件的内容
* f.readline()：读取单独的一行，换行符标志位“\n”,如果返回一个空字符串, 说明已经已经读取到最后一行；
* f.readlines()：读取文件中包含的所有行；
* f.write()：将数据写入到文件中, 然后返回写入的字符数；
