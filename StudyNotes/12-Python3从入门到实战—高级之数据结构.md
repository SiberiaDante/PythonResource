# 11-Python3从入门到实战—高级之数据结构

## 列表相关操作
<table>
<tr>
	<th>操作符</th>
	<th>说明</th>
</tr>
<tr>
	<td>list.append(x)</td>
	<td>把一个元素添加到列表的结尾，相当于 a[len(a):] = [x]</td>
</tr>
<tr>
	<td>list.extend(L)</td>
	<td>通过添加指定列表的所有元素来扩充列表，相当于 a[len(a):] = L</td>
</tr>
<tr>
	<td>ist.insert(i, x)</td>
	<td>在指定位置插入一个元素,</td>
</tr>
<tr>
	<td>list.remove(x)</td>
	<td>删除列表中值为 x 的第一个元素,如果没有这样的元素，就会返回一个错误</td>
</tr>
<tr>
	<td>list.pop([i])</td>
	<td>从列表的指定位置删除元素，并将其返回。如果没有指定索引，a.pop()返回最后一个元素,元素随即从列表中被删除</td>
</tr>
<tr>
	<td>list.clear()</td>
	<td>移除列表中的所有项，等于del a[:]</td>
</tr>
<tr>
	<td>list.index(x)</td>
	<td>返回列表中第一个值为 x 的元素的索引。如果没有匹配的元素就会返回一个错误</td>
</tr>
<tr>
	<td>list.count(x)</td>
	<td>返回 x 在列表中出现的次数</td>
</tr>
<tr>
	<td>list.sort()</td>
	<td>对列表中的元素进行排序</td>
</tr>
<tr>
	<td>list.reverse()</td>
	<td>倒排列表中的元素</td>
</tr>
<tr>
	<td>list.copy()</td>
	<td>返回列表的浅复制，等于a[:]</td>
</tr>
<tr>
	<td></td>
	<td></td>
</tr>
</table>

> 方法中 i 两边的方括号表示这个参数是可选的，而不是要求你输入一对方括号，你会经常在 Python 库参考手册中遇到这样的标记。

## 队列和堆栈
* 队列：遵循先进先出原则；
	列表可以当做队列使用：使用list.append()将元素推入栈中，使用list.pop(0)取出最先推入的元素
```
>>> s=[]
>>> s.append(0)
>>> s.append(1)
>>> s.append(2)
>>> s
[0, 1, 2]
>>> s.pop(0)
0
>>> s.pop(0)
1
>>> s.pop(0)
2
>>>
```
* 堆栈：遵循后进先出原则;
	列表当做堆栈使用：用 append() 方法可以把一个元素添加到堆栈顶。用不指定索引的 pop() 方法可以把一个元素从堆栈顶释放出来
```
>>> l = [3, 4, 5]
>>> l.append(6)
>>> l.append(7)
>>> stack
[3, 4, 5, 6, 7]
>>> l.pop()
7
>>> l
[3, 4, 5, 6]
>>> l.pop()
6
>>> l.pop()
5
>>> l
[3, 4]
```

## 列表推导式
