# 13-Python3从入门到实战—高级之模块的使用

## [Python从入门到实战系列——目录](https://github.com/SiberiaDante/PythonResource/blob/master/README.md)

## 模块的定义
模块是一个包含所有你定义的函数和变量的文件，其后缀名是.py。
模块可以被别的程序引入，以使用该模块中的函数等功能。
这也是使用 python 标准库的方法。

## 模块的作用
1、模块内有许多函数方法，利用这些方法可以更简单的完成许多工作。
2、模块可以在文件中永久保存代码。在python交互式解释器中操作输入的代码，在退出python时是不会被保存的，而模块文件中的代码是永久存在的。
3、从实用性方面来说，模块可以跨系统平台使用，只需要Copy代码就可以。比如说，有一个全局对像，会被许多文件使用，这时为了方便把它写入一个模块中，再被调用是最好的方法。

## 模块的使用——import语句
* 语法
```
    import module1[, module2[,... moduleN]
```
使用import 导入sys库
```
>>> import sys
>>> sys.path
['', 'C:\\Users\\ZCL\\AppData\\Local\\Programs\\Python\\Python36\\python36.zip',
 'C:\\Users\\ZCL\\AppData\\Local\\Programs\\Python\\Python36\\DLLs', 'C:\\Users\
\ZCL\\AppData\\Local\\Programs\\Python\\Python36\\lib', 'C:\\Users\\ZCL\\AppData
\\Local\\Programs\\Python\\Python36', 'C:\\Users\\ZCL\\AppData\\Local\\Programs\
\Python\\Python36\\lib\\site-packages', 'C:\\Users\\ZCL\\AppData\\Local\\Program
s\\Python\\Python36\\lib\\site-packages\\django-2.0.2-py3.6.egg', 'C:\\Users\\ZC
L\\AppData\\Local\\Programs\\Python\\Python36\\lib\\site-packages\\pytz-2017.3-p
y3.6.egg']
>>>
```
* 使用 import 导入自己的库
创建一个斐波那契(fibonacci)数列模块：fibo.py
```
# 斐波那契(fibonacci)数列模块

def fib(n):    # 定义到 n 的斐波那契数列
    a, b = 0, 1
    while b < n:
        print(b, end=' ')
        a, b = b, a+b
    print()

def fib2(n): # 返回到 n 的斐波那契数列
    result = []
    a, b = 0, 1
    while b < n:
        result.append(b)
        a, b = b, a+b
    return result
```
使用
```
>>> import fibo
>>> fibo.fib(1000)
1 1 2 3 5 8 13 21 34 55 89 144 233 377 610 987
>>> fibo.fib2(100)
[1, 1, 2, 3, 5, 8, 13, 21, 34, 55, 89]
>>> fibo.__name__
'fibo'
```

## 模块的使用——from…import 语句
* from语句可以从模块中导入一个指定的部分到当前命名空间中，语法如下：
```
from modname import name1[, name2[, ... nameN]]
```
* 导入上例中fibo.py中的函数
```
>>> from fibo import fib, fib2
>>> fib(500)
1 1 2 3 5 8 13 21 34 55 89 144 233 377
```

## 模块的使用——from…import * 语句
* 把一个模块的所有内容全都导入到当前的命名空间,语法：
```
from modname import *
```

## __name__属性
* 使用__name__属性可以使该程序块仅在该模块自身运行时执行，模块被引入时，模块中的该程序块不执行；
```
#!/usr/bin/python3
# Filename: using_name.py
if __name__ == '__main__':
   print('程序自身在运行')
else:
   print('我来自另一模块')
```
* 运行输出
```
$ python using_name.py
程序自身在运行
```

```
$ python
>>> import using_name
我来自另一模块
>>>
```

>  每个模块都有一个__name__属性，当其值是'__main__'时，表明该模块自身在运行，否则是被引入。

## dir() 函数
* 内置的函数 dir() 可以找到模块内定义的所有名称,以一个字符串列表的形式返回:
```
>>> import sys
>>> dir(sys)
['__displayhook__', '__doc__', '__excepthook__', '__interactivehook__', '__loade
r__', '__name__', '__package__', '__spec__', '__stderr__', '__stdin__', '__stdou
t__', '_clear_type_cache', '_current_frames', '_debugmallocstats', '_enablelegac
ywindowsfsencoding', '_getframe', '_git', '_home', '_xoptions', 'api_version', '
argv', 'base_exec_prefix', 'base_prefix', 'builtin_module_names', 'byteorder', '
call_tracing', 'callstats', 'copyright', 'displayhook', 'dllhandle', 'dont_write
_bytecode', 'exc_info', 'excepthook', 'exec_prefix', 'executable', 'exit', 'flag
s', 'float_info', 'float_repr_style', 'get_asyncgen_hooks', 'get_coroutine_wrapp
er', 'getallocatedblocks', 'getcheckinterval', 'getdefaultencoding', 'getfilesys
temencodeerrors', 'getfilesystemencoding', 'getprofile', 'getrecursionlimit', 'g
etrefcount', 'getsizeof', 'getswitchinterval', 'gettrace', 'getwindowsversion',
'hash_info', 'hexversion', 'implementation', 'int_info', 'intern', 'is_finalizin
g', 'last_traceback', 'last_type', 'last_value', 'maxsize', 'maxunicode', 'meta_
path', 'modules', 'path', 'path_hooks', 'path_importer_cache', 'platform', 'pref
ix', 'ps1', 'ps2', 'set_asyncgen_hooks', 'set_coroutine_wrapper', 'setcheckinter
val', 'setprofile', 'setrecursionlimit', 'setswitchinterval', 'settrace', 'stder
r', 'stdin', 'stdout', 'thread_info', 'version', 'version_info', 'warnoptions',
'winver']
>>>
```

* dir() 函数不指定参数时，会罗列出当前模块中定义的所有名称
```
>>> username = 'SiberiaDante'
>>> dir()
['__annotations__', '__builtins__', '__doc__', '__loader__', '__name__', '__pack
age__', '__spec__', 'username']
>>>
```

## 包的使用
* 导入模块时可以使用 包名.模块 的形式导入,如包名为：com.file;模块名为：showMsg
```
# 第一种导入方式
import com.file.showMsg
```
> 如上这种导入方式，使用模块时需要包名全路径：com.file.showMsg.print...;

```
# 第二种导入方式
```
from com.file import showMsg
```

> 这种导入方式就可以直接使用 showMsg.***，不需要那些冗长的前缀包名
```
# 第三种导入,可以导入模块showMsg中的变量、函数等
from com.file.showMsg import username
```




