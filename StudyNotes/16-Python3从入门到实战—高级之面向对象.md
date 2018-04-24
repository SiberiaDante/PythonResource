# 16-Python3从入门到实战—高级之面向对象

## [Python从入门到实战系列——目录](https://github.com/SiberiaDante/PythonResource/blob/master/README.md)

## 类和实例
* 定义一个类的语法
```
    class ClassName(Object):
        pass
```
> 类名后面跟的 Object 类集成自哪个类；        
> 创建类的实例：类名（）
```
    # 定义一个 Student 类
    class Student(object):
        name = "SiberiaDante"
    # 创建 Student 实例
    student = Student()
    print(student.name)
```
* __init__()方法：使用 __init__() 方法对类进行初始化处理
```
    class Student(object):
        name = "SiberiaDante"
        def __init__(self, name):
            self.name = name
    student = Student("Handsome Guy")
    print(student.name)
```

## 类的方法
使用 def 关键字来定义一个方法，与一般函数定义不同，类方法必须包含参数 self, 且为第一个参数，self 代表的是类的实例;
```
    class Student(object):
        def showMsg(self,msg):
            print("is a msg from showMsg void:",msg)
    student = Student("Handsome Guy")
    student.showMsg("SiberiaDante")
```
输出：
> is a msg from showMsg void: SiberiaDante

## 类的继承
一个类可以继承另一个类
```
    # 定义一个父类
    class Course(object):
        msg = "SiberiaDante is studying"
        age = 18
        __name = "SiberiaDante"  # 父类私有属性，子类无法使用
    
        def showMsg(self, msg):
            print("msg from Course class:", msg)
    
    # 定义一个子类，继承父类Course
    class Python(Course):
        def showMsg1(self, msg):
            print("msg from Python class:", msg)
    
        # 重写父类的方法
        def showMsg(self, msg):
            print("void is overwrite from Course class:", msg)
    
    python = Python()  # 创建Python类的实例
    print(python.msg)  # 子类条用父类中的属性
    python.showMsg("Course")  # 子类调用重写自父类的方法
    python.showMsg1("Python")  # 子类调用子类的方法
```
输出结果：
> SiberiaDante is studying      
  void is overwrite from Course class: Course       
  msg from Python class: Python         

## 
