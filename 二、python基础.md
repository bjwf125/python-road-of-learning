一、列表



1、列表的定义



```

一个队列，一个排列整齐的队伍

列表内的个体称作元素，由若干个元素组成列表

元素可以是任意对象（数字、字符串、对象、列表等）

列表内元素有顺序，可以使用索引

使用[]表示

列表是有序的

```



2、列表索引访问



- 索引，也叫下标

- 正索引：从左至右，从0开始，为列表的每一个元素编号

- 负索引：从右至左，从-1开始

- 正索引不可以越界，否则会引发异常IndexError



3、列表常用方法



```

1、创建列表



lst = [12,23,4,54,'hello']



2、添加元素 # append从尾部增加，一次只能增加一个



In [1]: lst = [1,2,3,6,8]

In [2]: lst.append('hello','world')

---------------------------------------------------------------------------

TypeError Traceback (most recent call last)

<ipython-input-2-8f47abb14f28> in <module>

----> 1 lst.append('hello','world')

TypeError: append() takes exactly one argument (2 given)

In [3]: lst.append('hello')

In [4]: lst

Out[4]: [1, 2, 3, 6, 8, 'hello']



3、插入元素 # insert



In [5]: lst = [1,3,4]



In [6]: lst.insert(1,2) #list.insert(index,objecct) 参数一：index位置 参数二：object



In [7]: lst  

Out[7]: [1, 2, 3, 4]



4、扩展列表 # extend 等于两个列表相加



In [8]: lst1 = [1,2,3]



In [9]: lst2 = ['xixi','haha']



In [10]: lst1.extend(lst2)



In [11]: lst1

Out[11]: [1, 2, 3, 'xixi', 'haha']



5、删除元素 # remove pop

list.remove(object) #参数object如有重复，只会删除最靠前的



In [12]: lst = [1,2,3,4,5,1,'a','b']



In [13]: lst.remove(1)



In [14]: lst

Out[14]: [2, 3, 4, 5, 1, 'a', 'b']



list.pop(index) #默认删除最index，index是可选参数，要移除列表中对应索引值



In [14]: lst

Out[14]: [2, 3, 4, 5, 1, 'a', 'b']



In [15]: lst.pop()

Out[15]: 'b'



In [16]: lst

Out[16]: [2, 3, 4, 5, 1, 'a']



In [17]: lst.pop(2) #指定索引删除

Out[17]: 4



In [18]: lst

Out[18]: [2, 3, 5, 1, 'a']



del list[index] #可以删除整个列表或指定元素或者列表切片，list删除之后无法访问



In [20]: lst

Out[20]: [2, 3, 5, 1, 'a']



In [21]: del lst[0]



In [22]: lst

Out[22]: [3, 5, 1, 'a']



In [23]: del lst



In [24]: lst

---------------------------------------------------------------------------

NameError Traceback (most recent call last)

<ipython-input-24-b5cada25ed2a> in <module>

----> 1 lst



NameError: name 'lst' is not defined



6、排序和反转

lst.reverse() #列表元素反转



In [27]: lst

Out[27]: [1, 2, 3, 4, 5, 'ab', 'cs', 'a']



In [28]: lst.reverse()



In [29]: lst

Out[29]: ['a', 'cs', 'ab', 5, 4, 3, 2, 1]



lst.sort() #排序，sort有三个默认参数，cmp=None,key=None,reverse=False，数字和字符串不能一起排序



In [32]: lst = [3,2,5,6,4]



In [33]: lst.sort() # 默认reverse=False 升序排列 



In [34]: lst

Out[34]: [2, 3, 4, 5, 6]



In [35]: lst = [3,2,5,6,4]



In [36]: lst.sort(reverse=True) # reverse=True 降序排列



In [37]: lst

Out[37]: [6, 5, 4, 3, 2]



sorted(lst) # sorted()函数和sort()方法有一点不同，sort()会在原list上重新排列并保存，而sorted()不会改变原列表的顺序，只是生成新的排序列表



7、列表切片



列表的位置，或索引，第一个索引是0，第二个索引是1，反向从-1开始



In [39]: L[2]

Out[39]: 'SPAM'



In [40]: L[-2]

Out[40]: 'Paul'



In [41]: L[1:]

Out[41]: ['Spam', 'SPAM', 'Sam', 'Paul', 'Kate']



In [42]: L[1:4:2]

Out[42]: ['Spam', 'Sam']



8、清空列表 # 清空列表里面所有元素，不会删除列表



In [43]: L

Out[43]: ['spam', 'Spam', 'SPAM', 'Sam', 'Paul', 'Kate']



In [44]: L.clear()



In [45]: L

Out[45]: []  

```



4、习题



```

求100以内的素数



n = 100

count = 0

primenumber = []



for x in range(2, n):

    for i in primenumber:

        if x % i == 0:

            break

    else:

        primenumber.append(x)

        count += 1



print(primenumber)

print(count)





打印杨辉三角



triangle = [[1],[1, 1]]



for i in range(2, 6):

    cur = [1]

    pre = triangle[i-1]

    for j in range(len(pre)-1):

        cur.append(pre[j] + pre[j+1])



    cur.append(1)

    triangle.append(cur)

print(triangle)



```



二、元组



1、定义



- 一个有序的元素组成的集合

- 使用小括号()表示

- 元组是不可变的对象



2、元组元素的访问



 



```

支持索引（下标）

正索引：从左至右，从0开始，为列表中每一个元素编号

负索引：从右至左，从-1开始

正索引不可以越界，否则会引发异常IndexError

元组通过索引访问 tuple[index]，index就是索引，使用中括号访问

```



3、元组查询



 



```

index(value,[start,[stop]])

 通过value，从指定区间查找列表内的元素是否匹配

 匹配第一个就立即返回索引

 匹配不到，抛出异常ValueError

count(value)

 返回列表中匹配value的次数

时间复杂度

 index和count方法都是O(n)

 随着列表数据规模的增大，而效率下降

len(tuple)

 返回元素的个数



In [1]: t = tuple(range(8))



In [2]: t

Out[2]: (0, 1, 2, 3, 4, 5, 6, 7)



In [3]: t[1]

Out[3]: 1



In [4]: t[3] 

Out[4]: 3



In [6]: len(t)

Out[6]: 8

```



三、字符串



- 一个个字符组成的有序的序列，是字符的集合

- 使用单引号，双引号、三引号引住的字符序列

- 字符串是不可变对象



```

示例

a = "Hello"

b = "Python"



print("a + b 输出结果：", a + b)

print("a * 2 输出结果：", a * 2)

print("a[1] 输出结果：", a[1])

print("a[1:4] 输出结果：", a[1:4])



if ("H" in a):

    print("H 在变量 a 中")

else:

    print("H 不在变量 a 中")



if ("M" not in a):

    print("M 不在变量 a 中")

else:

    print("M 在变量 a 中")



print(r'\n')

print(R'\n')





结果：

a + b 输出结果： HelloPython

a * 2 输出结果： HelloHello

a[1] 输出结果： e

a[1:4] 输出结果： ell

H 在变量 a 中

M 不在变量 a 中

\n

\n

```