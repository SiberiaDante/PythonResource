# 17-Python3从入门到实战—高级之正则表达式

## [Python从入门到实战系列——目录](https://github.com/SiberiaDante/PythonResource/blob/master/README.md)

## 正则表达式匹配规则
```
'\d'  匹配一个数字
'\D'  匹配一个非数字字符
'\w'  匹配数字字母下划线
'\W'    匹配非数字字母下划线
'\s'  匹配任何空白字符，包括空格、制表符、换页符等等
'\s'  匹配任何非空白字符
'\w'  匹配包括下划线的任何单词字符
'\W'  匹配任何非单词字符
'^'  匹配字符串的开头
'$'  匹配字符串的结尾
'[0-9]'  匹配任何数字
'[a-z]'  匹配任何小写字母
'[A-Z]'  匹配任何大写字母
'[a-zA-Z0-9]'  匹配任何字母及数字
'[^0-9]'  匹配除了数字外的字符
'\n'  匹配一个换行符
'\t'  匹配一个制表符
'a|b'  匹配a或b
```

## re.match函数
* 函数语法
```
    # pattern:匹配的正则表达式；string:要匹配的字符串；flags：正则表达式的匹配方式
    re.match(pattern,string,flag=0)
```
从字符串的起始位置匹配一个模式，如果不是起始位置匹配成功的话，match()就返回none；
```
    >>> import re
    >>> print(re.match('https','https://github.com'))
    <re.Match object; span=(0, 5), match='https'>
    >>> print(re.match('https','https://github.com').span())
    (0, 5)
    >>>
```

## groups() 获取匹配表达式
返回匹配到的字符串元组

> group() 返回一个包含所有小组字符串的元组，从 1 到 所含的小组号；        
> group(num)    返回一个包含num组所对应值的元组；
```
    import re
    line = "100 + 10 = 110"
    matchObj = re.match(r'(\d*) \+ (\d*?) \d*', line, re.M | re.I)
    if matchObj:
        print("matchObj.group():", matchObj.group())
        print("matchObj.group(1):", matchObj.group(1))
        print("matchObj.group(2):", matchObj.group(2))
    else:
        print("match end")
```
输出结果：
>   matchObj.group(): 100 + 10      
    matchObj.group(1): 100      
    matchObj.group(2): 10       

## re.search函数
语法
```
    # pattern:匹配的正则表达式；string:要匹配的字符串；flags：正则表达式的匹配方式
    re.search(pattern, string, flags=0)
```
扫描整个字符串并返回第一个成功的匹配；
```
    >>> import re
    >>> print(re.search('https','https://github.com'))
    <re.Match object; span=(0, 5), match='https'>
    >>> print(re.search('https','https://github.com').span())
    (0, 5)
    >>>
```

## re.match与re.search的区别
re.match只匹配字符串的开始，如果字符串开始不符合正则表达式，则匹配失败，函数返回None；而re.search匹配整个字符串，直到找到一个匹配；
```
    import re
    msg = "SiberiaDante is a handsome young guy"
    
    matchObj = re.match("handsome", msg)
    if matchObj:
        print("match:",matchObj.group())
    else:
        print("not match")
        
    searchObj = re.search("handsome", msg)
    if searchObj:
        print("search:",searchObj.group())
    else:
        print("not search")
```
输出结果：
> match:not match           
  search: handsome

## re.sub函数
语法
```
    # 参数说明：
    # pattern : 正则中的模式字符串；
    # repl : 替换的字符串，也可为一个函数；
    # string : 要被查找替换的原始字符串；
    # count : 模式匹配后替换的最大次数，默认 0 表示替换所有的匹配；
    re.sub(pattern, repl, string, count=0)
```
re.sub用于替换字符串中的匹配项
```
    import re
    msg = "SiberiaDante is a handsome gay"
    resultMsg = re.sub("gay", "guy", msg)
    print("替换后的结果：", resultMsg)
```
输出：
>   替换后的结果： SiberiaDante is a handsome guy
参数 repl 为函数使用
```
    import re
    msg = "SiberiaDante is a handsome guy"
    
    def makemsg(matched):
        return str("young " + matched.group('value'))
    
    rMsg = resultMsg = re.sub("(?P<value>guy+)", makemsg, msg)
    print("替换后的结果：", rMsg)
```
输出：
> 替换后的结果： SiberiaDante is a handsome young guy

## re.compile 函数
语法
```
    re.compile(pattern[, flags])
```
compile 函数用于编译正则表达式，生成一个正则表达式（ Pattern ）对象，供 match() 和 search() 这两个函数使用;
```
    import re
    pattern = re.compile(r'\d+')
    print("re.match:", re.match(pattern, "中午 12 点 46分"))
    print("re.search:", re.search(pattern, "中午 12 点 46分"))
```
输出结果：
> re.match: None            
  re.search: <re.Match object; span=(3, 5), match='12'>
  
## findall函数
语法
```
    # string 待匹配的字符串;
    # pos 可选参数，指定字符串的起始位置，默认为 0;
    # endpos 可选参数，指定字符串的结束位置，默认为字符串的长度;
    findall(string[, pos[, endpos]])
```
在字符串中找到正则表达式所匹配的所有子串，并返回一个列表，如果没有找到匹配的，则返回空列表;
> 区别： match 和 search 是匹配一次 findall 匹配所有。

```
    import re
    pattern = re.compile(r'\d+')
    print("result=",pattern.findall("12345,你妈会跳舞，56789，看你像条狗"))
```
输出：
> result= ['12345', '56789']

## re.finditer函数
语法
```
    # pattern:匹配的正则表达式;
    # string:要匹配的字符串;
    # flags:标志位，用于控制正则表达式的匹配方式;
    re.finditer(pattern, string, flags=0)
```
和 findall 类似，在字符串中找到正则表达式所匹配的所有子串，并把它们作为一个迭代器返回;
```
    import re
    result=re.finditer(r"\d+","12345你妈会跳舞56789看你像条狗")
    for r in result:
        print(r.group())
```
输出结果：
> 12345         
  56789
  
## re.split函数
语法
```
    re.split(pattern, string[, maxsplit=0, flags=0])
```  
split 方法按照能够匹配的子串将字符串分割后返回列表
```
    import re
    print(re.split(r"/W","Siberia,Dante,Python"))
    print(re.split(r"g*","Siberia,Dante,Python"))
```
输出结果：
> ['Siberia,Dante,Python']          
  ['', 'S', 'i', 'b', 'e', 'r', 'i', 'a', ',', 'D', 'a', 'n', 't', 'e', ',', 'P', 'y', 't', 'h', 'o', 'n', '']

