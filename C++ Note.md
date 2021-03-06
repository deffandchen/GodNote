# C++ Note

[TOC]



## C++的特性

### 封装

### 继承

### 多态
	面向对象的核心思想。
	多态：基类中定义的虚函数可以在派生类中重写。当使用基类的引用或指针调用一个虚成员函数时会执行动态绑定。动态绑定通过虚表指针实现，当一个类存在虚函数时，虚表的位置存放在类的首地址处，虚表中存放的是虚成员函数的地址指针。
#### 虚表
	每个拥有虚成员函数的类都有虚表，虚表只和类有关，和实例化对象无关。虚表的创建发生在编译器的编译阶段。
##  C++的内存管理
### 内存类型
	静态存储区：存放全局变量和静态变量。
	常量存储区：存放常量。eg. string a = "hello";"hello"存放在常量存储区。
	堆内存：存放动态申请的内存，eg：new、malloc。
	栈内存：存放局部变量。
### new和malloc的区别
	new申请内存时无需指定无需指定大小，返回的是类的指针。
	malloc申请内存需要指定内存的大小，返回的是void*;
### new和allocator的区别
	new创建对象时，先分配内存再构造对象。
	allocator将分配内存和构造对象分开，先进行内存的分配，再构造对象。
	allocator性能优于new：
		使用new string(10);并全赋值为"hello"时，先分配内存再构造10个空的string对象，也就是对内存赋值为""，然后再赋值"hello",造成性能的浪费。
		使用allocator则先分配内存，然后直接对内存赋值为"hello"。
### 如何判断内存泄露

### 深拷贝和浅拷贝
## class
### 构造函数不能是虚函数
### 类模板
每个参数(T1,T2)前面都需要加class

	template<class T1 ,class T2>
	class A{
	...
	}

## 类型转换
	static_cast:强制类型转换。float = dynamic_cast<float> ;
	dynamic_cast:基类和派生类之间的转换。可以将基类的指针或引用安全地转为派生类。
	const_cast:用于去除变量的const性。
## sizeof
	sizeof和strlen的区别：
	sizeof()返回参数（数组、指针、类、对象等），strlen返回字符串所占的字节数。
	指针、long、double占8个字节，int、float占4个字节，char占1个。
### struct
### union
### class
## c++11新特性
	auto、nullptr、lambda，右值引用、move
### lambda

## STL

### vector
	vector的底层实现是通过动态的数组，当内存不够时会重新申请内存，新申请的内存为之前内存大小的两倍。
### map
	自定义类型存入map需要重载 < ,因为map是有序的。
### 智能指针
### 数组和链表的区别
	数组定义时需要指定大小，内存是连续的，可以通过下标访问。
	链表不需要指定大小，内存不连续，不能通过下标访问。
## 编译
	C/C++编译到生成可执行文件的过程：预编译 -> 编译 -> 汇编  -> 链接
	编译：通过语法和词法分析代码是否符合规则，并将代码翻译成汇编语言。
	汇编：将汇编语言翻译成目标机器指令。
	链接：将程序所用到的库连接起来，并将汇编文件翻译成可执行文件。


# 数据结构
## 链表
## 二叉树
## 排序
## 随机数生成
好的，总结了一下：手撕的有：线程池，avl，红黑树及升级，map，deque，sort，约瑟夫链表，lru，ringbuff，数组实现生产者消费者队列