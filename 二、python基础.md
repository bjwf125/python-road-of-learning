一、python3命名空间和作用域
>命名空间
先看看官方文档的一句话：
A namespace is a mapping from names to objects.Most namespaces are currently implemented as python dictionaries.
命名空间（namespace）是从名称到对象的映射，大部分的命名空间都是通过python字典来实现的。
命名空间提供了在项目中避免名字冲突的一种方法。各个命名空间是独立的，没有任何关系的，所以一个命名空间中不能有重名,但不同的命名空间是可以重名而没有任何影响。
我们举一个计算机系统中的例子，一个文件夹（目录中）可以包含多个文件夹，每个文件夹中不能有相同的文件名，但不同的文件夹中可以重名。
