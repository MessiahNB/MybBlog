---
title: JAVA笔记
date: 2022-07-25 17:30:02
---

# JavaSE笔记
    1.java的历史
    jdk	java开发工具包
    jre jave运行环境
    jvm	java虚拟机
局部变量，必须声明和初始化
布尔值 默认为false
除了基本值默认为0其他都为null
修饰符final不存在前后循序
常量全大写 变量名首字母小写驼峰原则 类名首字母大写驼峰原则
<< 左移*2   >> 右移/2
字符串连接符 +  要注意字符串所在的位置
三目运算符 a>b ? x,y a为真返回x，为假返回y 
包就是文件夹
定义包packeg 导入包 import
阿里巴巴开发手册规范
javadoc生成文档
scanner类 
用scanner对象的next()和nextline()来获取用户输入的字符串，可以用hasnext()和hasnestline()来判断用户是否有下一个输入
凡是io流用完记得关掉它 close()
next()不可以获得空白，空白作为分隔符或者结束符，而nextline()就可以获得空白，它以回车为结束符，用的比较多

java的基本结构为顺序结构，总共有三种结构：顺序结构，判断结构，循环结构

switch 每一个case就要有一个break，不然会出现case穿透现象，输出后面所有值
选择结构
if单选择
if(布尔表达式){
	代码块
}
if多选择
if(布尔表达式){
	代码块
}else{
	代码块
}
多重if结构
if(布尔表达式1){
	代码块1
}else if(布尔表达式2){
	代码块2
}else if(布尔表达式3){
}else{
	代码块3
}

循环结构
while循环：先判断在执行
while(布尔表达式){
	循环代码块
}

dowhile循环：先执行一次在判断条件
do{
	循环代码块
}while(布尔表达式)

for循环：先判断满足条件在执行，是循环中最有效，最灵活的循环结构，循环次数在开始的时候就被确定

for(初始值,循环条件,迭代器){
	代码块
}
增强for循环 ：重点遍历数组和集合
break 用于强制退出循环，不执行循环剩下的语句
continue 终止某次循环，既跳过之后的语句，重新回到循环判定

## Java方法详解
静态方法：不需要示例化 直接类名.方法名调用 用static修饰 是和类一起加载的
非静态方法：不需要修饰但一定要示例化创建对象。通过对象.方法名调用
return 除了了返回方法结果外还有一个功能就是return 0;终止方法
什么是值传递什么是引用传递  java是值传递  java的八大基本数据类型一般都是值传递 靠返回值来修改真是的值信息，而对象数组的话一般都是引用传递
	值传递：会复制一份，形参无返回是不会改变实参
	引用传递：一般存在与对象 改变的不是形参改变的是对象                                                                                                                                                                                 方法重载：名称相同 参数必须不同(可以是类型不同，个数不同，参数排列顺序不同)发生在本类 返回类型也可以不同或者相同
方法重写：名称相同 参数列表相同且返回类型必须相同  发生在父类与子类之间
重载："两同三不同"
	同一个类 同一个方法名
	参数 不同 类型 顺序 个数


命令行传参：一定要写上我们的包路径 ，main方法也是可以传参的

可变参数：...类型要相同，且必须要在参数列表最后一个

递归：自己调用自己 包含两个部分递归头和递归体   递归头：递归方法的结束，什么时候不调用自身 递归体：什么时候需要调用自身
## Java数组
数组：想同类型数的有序集合
特点：长度是确定，长度一旦确定就不可改变
	  必须是相同类型的数据
	  数组中的元素可以是任何类型的数据
	  数组变量属于引用类型，也可以看成是一个对象，数组中的每个元素可以看成是该对象的成员变量
	  数组是存放在堆中的，无论数组中的元素类型是基本类型还是引用类型
数组的定义两种方法：在类型名后写数组符号，在变量名后面写数组符号  通过new来创建 数组长度要确定
静态初始化： int[] a = {1,2,3,4}  创建+赋值
动态初始化:	 int[] a = new int[4]  包含默认初始化  只是创建但是不会给数组赋值
lenth()：求数组长度

多维数组：相当于数组类的每个元素都是一个数组
多维数组的打印要用多个循环

Arrays类：数组工具类 包含操作数组的各个方法的工具类
	tostring()打印数组元素
	sort()数组排序默认升序	
冒泡排序：总共有八种排序 时间复杂度O(n^2)
稀疏数组：用来压缩数组，获取有效值
## Java内存分析
java内存 堆：存放new的对象和数组
			 可以被所有线程共享，不会存放别的对象的引用
		 栈：存放基本数据类型(会包含这个基本类的具体数值)
			 引用对象的变量(会存放这个对象在堆里面的具体地址)		 
		 方法区：可以被所有线程共享
				 包含所有class和static变量
## Java面向对象编程oop
面向过程编程 线性思维
面向对象编程 分类思维
本质：以类的方式组织代码，以对象来组织(封装)数据 抽象
三大特性；继承 封装 多态
this：指当前对象
类只包含属性和方法 是抽象的，使用的时候一定要示例化
使用new来创建对象 的时候除了灰分配空间，还会对创建好的对象 进行默认的初始化(调用类的构造方法)和类中构造器的调用

类中构造器也成构造方法，用来初始化值，是在进行创建对象的时候必须被调用的方法，构造方法有两个特点，和类名相同，没有返回类型也不能写void
类的构造方法会默认存在一个无参构造，即使类中什么也没写，如果一旦写了有参构造那么无参构造就一定要写出来

可以使用alt+insert快捷键
来生成构造

封装：属性私有 get/set方法来操作数据  alt+insert快捷键来生成get/set
		提高程序安全性，保护数据
		统一接口
		隐藏代码实现细节
继承： extends java只能单继承
ctrl+h 打开继承树
在java中只会有单继承
子类继承父类，会拥有父类所有的方法，无法继承私有的
supper代表父类对象的引用，也只能出现在子类之中，子类会默认存在一个supper()方在第一行也必须是第一个调用父类的构造方法，supper和this不能同时调用构造方法
supper和this的区别与注意点
代表的对象不同
	this：本身调用者这个对象
	supper：父类对象的引用
前提条件不同
	this：没有继承也可以使用
	supper：只有存在继承条件才可以死使用
构造方法不同
	this():本类的构造
	supper():父类的构造

方法的重写
	静态方法和被final修饰的不能重写
	父类的引用指向子类
	重写都是方法的重写和属性无关
	需要有继承关系
	是子类重写父类的方法执行子类的方法
	方法名字和参数列表必须一样。方法体不一样
	修饰符范围可以扩大但不能缩小
	抛出的异常范围可以缩小但不能扩大
为什么需要重写？
	1.父类的功能子类不一定需要	
多态：同一方法可以根据对象的不同产生不同的行为，一个对象的实际类型是确定的(因为new)，但可以指向对象的引用的类型可以有很多，也是方法的多态，和属性无关
多态存在的条件：
	1.存在继承关系
	2.子类重写父类方法
	3.父类引用指向子类对象  Animal animal = new Cat(); cat是继承animal的子类 Animal animal 
	一、使用父类类型的引用指向子类的对象； 
    二、该引用只能调用父类中定义的方法和变量； 
    三、如果子类中重写了父类中的一个方法，那么在调用这个方法的时候，将会调用子类中的这个方法；(动态连接、动态调用) 
个人总结：父类的引用根据new的子类对象不同而产生不同的行为
instanceof 可以判断两个类是否有联系
## Java static，final详解
static：静态的
	在java中静态属性是和类一起加载
	静态方法或者类的静态属性，是可以直接通过类名. 来使用的
	非静态方法就不能需要类的实例化
	被static修饰的成员变量和成员方法独立于该类的任何对象，也就是说他不依赖类的任何特殊实例，被类的所有实例所共享，只要这个类被加载了，java虚拟机能根据类名在运行时数据区的方法区内找到他们。
	静态变量(类变量)：静态变量被所有的对象共享，也就是说我们创建了 一个类的多个对象，但是这个类具有一个静态变量，那么这多个对象其实就是共享这一个静态变量，如果我们修改了这个静态变量的值，那么其他对象的静态变量值也会随之修改。
	非静态变量(实例变量)：如果我们创建了一个类的多个对象，那么每个对象都会有属于自己的非静态变量，当你修改一个对象的非静态变量的时候 不会引起其他对象的非静态变量值发生改变
	static修饰的方法 成员称作静态方法，静态方法的使用可以通过类名.方法名来进行调用，由于静态 方法在类加载的时候就已经存在，所以说静态方法并不依赖任何一个实例对象	
final：被final修饰的变量是常量，值不可以改变
	   被final修饰的方法不能被重写
	   被final修饰的类不能够被继承
## 抽象类
abstract：被abstract修饰的类就为抽象类，方法为抽象方法
抽象类：不一定只含有抽象方法
		抽象类只能够继承，不能够被实例化
		子类继承抽象类就必须实现抽象类没有被实现的抽象方法
抽象方法：只有方法的定义没有方法的实现，只能存在于抽象类，有抽象方法此类必为抽象类
抽象方法：只有方法的定义没有方法的实现
思考：抽象类有没有构造器 有
抽象类是有构造器的	
## 接口
interfa：定义接口 相当于一种约束
接口只能定义抽象方法，所以接口都需要有一个实现类
让类实现接口就需要用到implemens关键字来实现接口
借口不能被实例化，也没有构造函数
实现接口的类，就必须实现接口中的抽象方法
抽象类和接口的区别
	1.抽象类除了不能够被实例化以外，其余和普通类没什么区别
	2.接口是完全抽象的，不存在抽象方法的实现，只能够定义
	抽象方法，也没有构造器

## 内部类

### 成员内部类

​	一个类中写了另一个类。这个内部类作为外部类的成员，这个内部内可以获得外部类的私有变量和私有方法  

### 局部内部类

​	类中的方法里面包含一个类

## 异常
抛出异常throw:在方法内抛出  throws：抛出方法外
捕获异常
try{
	检测异常区域
}catch(什么样的异常){//捕获异常
	捕获后怎么处理
}finally{
	异常善后工作
}
ctrl+alt+t快捷键用来对选中语句生成try-catch

## 多线程
### JAVA内存模型(JMM)
java内存模型 描述了Java程序中各种变量(线程共享变量)的访问规则，以及在JVM中将变量存储到内存和从内存中读取出变量这样的底层细节。
可见性：一个线程对共享变量值的修改，能够及时地被其他线程看到。
共享变量：如果一个变量在多个线程的工作内存中都存在副本，那么这个变量就是这几个线程的共享变量。
乐观锁 与 悲观锁
CAS(Compare And Swap 比较并且替换)是乐观锁的一种实现方式，是一种轻量级锁，JUC 中很多工具类的实现就是基于 CAS 的。
CAS 是怎么实现线程安全的？
线程在读取数据时不进行加锁，在准备写回数据时，先去查询原值，操作的时候比较原值是否修改，若未被其他线程修改则写回，若已被修改，则重新执行读取流程。
他是乐观锁的一种实现，就是说认为数据总是不会被更改，我是乐观的仔，每次我都觉得你不会渣我，差不多是这个意思。
cas采用的是自旋锁(一直尝试，直到成功)的思想，是一种轻量级的锁机制。
悲观锁
悲观锁从宏观的角度讲就是，他是个渣男，你认为他每次都会渣你，所以你每次都提防着他
AQS：也就是队列同步器，这是实现 ReentrantLock 的基础。

### JAVA并发-理论基础
并发出现问题的根源 并发三要素:可见性，原子性，有序性
	可见性：cpu缓存引起
    定义：一个线程对共享变量的修改，另外一个线程能够立马看得到
    原子性：分时复用引起
    定义:即一个操作或者多个操作，要不全部执行并且在执行的过程中不会被任何因素所打断，要么就全都不执行
    有序性：重排序引起
    定义：即程序的执行顺序按照代码的先后顺序进行执行
在执行程序时为了提高性能，编译器和处理器常常会对指令做重排序。重排序分三种类型： 

1、编译器优化的重排序。编译器在不改变单线程程序语义的前提下，可以重新安排语句的执行顺序。 

2、指令级并行的重排序。现代处理器采用了指令级并行技术(Instruction-Level Parallelism， ILP)来将多条指令重叠执行。如果不存在数据依赖性，处理器可以改变语句对应机器指令的执行顺序。 

3、内存系统的重排序。由于处理器使用缓存和读 / 写缓冲区，这使得加载和存储操作看上去可能是在乱序执行。
原子性：一般来说 只有简单的赋值、读取 操作语句才有可能是原子操作 才能体现原子性 对于这种赋值来说还必须应该是将数字 赋值给某个变量，变量之间的相互赋值还不算是原子操作，为啥 因为 这涉及到两个步骤 ①他会先去读一个变量的值，然后再将这个变量的值赋值给另一个变量的值
我们由此可以看来 java内存模型只保证了基本读取和赋值是原子操作，如果要实现更大范围的原子操作就必须使用到java的关键字synchronized和Lock来实现

在我们java中 通常都会使用它到 synchronized 和 volatile  他们两个都是用在多线程的环境下。

#### Volatile

​	volatile保证不同线程对共享变量操作的可见性，也就是说一个线程修改了volatile修饰的变量，当修改写回主内存时，另外一个线程立即看到最新的值。
具备两种特性 

- 当我们改变了一个volatile，jvm会把其他线程对应的本地内存中的变量强制刷新，立即获取主内存中最新的值 ,从而来保证此***变量对所有线程的可见性***

- ***防止指令重排序***：重排序是指JVM的即时编译器和处理器为了优化程序性能而对指令序列进行重新排序的一种手段。

   + 这个时候就会有疑问

      1. 是怎么保证可见性的？

      2. 为什么要保证可见性？

      3. 怎么防止指令重排序的？

      4. 为什么要防止指令重排序？

         ​	可见性问题主要是指一个线程修改了共享变量值，而另一个线程却看不到。引起这种问题的主要原因在于每个线程拥有一个自己的高速缓存区（本地线程工作内存），如果不保证可见性的话，多个线程之间就会出现数据不一致的问题。而volatile是基于内存屏障来实现变量的内存可见性。在 volatile 修饰的共享变量进行写操作的时候，编译后会多出 lock 前缀的指令，lock 前缀的指令在多核处理器下会引发两件事情:

         1. 将当前线程处理器缓存行的数据写回到系统内存也就是主内存中。
         2. 写回主内存的操作会使在其他 CPU 里缓存了该内存地址的数据无效。

         如果对声明了 volatile 的变量进行写操作，JVM 就会向处理器发送一条 lock 前缀的指令，将这个变量所在缓存行的数据写回到系统内存也就是主内存。

         为了保证各个处理器的缓存是一致的，实现了缓存一致性协议(MESI)，每个处理器通过嗅探在总线上传播的数据来检查自己缓存的值是不是过期了，当处理器发现自己缓存行对应的内存地址被修改，就会将当前处理器的缓存行设置成无效状态，当处理器对这个数据进行修改操作的时候，会重新从系统内存中把数据读到处理器缓存里。

         所有多核处理器下还会完成：当处理器发现本地缓存失效后，就会从内存中重读该变量数据，即可以获取当前最新值保证数据可见性。

         而对于指令重排序也是如此，指令重排序后导致执行顺序出现问题，而Lock前缀：Lock不是一种内存屏障，但是它能完成类似全能型内存屏障的功能。为什么说Lock是一种伪类型的内存屏障，是因为内存屏障具有happen-before的效果，而Lock在一定程度上保证了先后执行的顺序，因此也叫做伪类型。比如，IO操作的指令，当指令不执行时，就具有了mfence的功能。

         总而言之一个变量被volatile关键字修饰之后有两个作用：

         （1）对于写操作：对变量更改完之后，要立刻写回到主存中。

         （2）对于读操作：对变量读取的时候，要从主存中读，而不是缓存。

         volatile 变量通过这样的机制就使得每个线程都能获得该变量的最新值来保证数据的可见性和有序性。

使用场景：只能在有限的情形下使用volatile变量替代锁，要使volatile变量提供理想的线程安全，必须同时满足一下两个条件
	①对变量的写操作不依赖于当前值。
	②改变量没有包含在具有其他变量的不变市中。
	volatile 最适合 一个线程写 多个线程读的情况下。如果有多个线程并发写的操作
volatile 和 synchronized 的区别
	1、volatile 关键字是线程同步的轻量级实现，所以从性能这一方面来讲 volatile 比 synchronize要好，volatile只能修饰变量，而synchronized可以修饰方法、代码块。随着jdk版本的发布 synchronized的执行效率有很大的提升，在开发中使用synchronized的比率还是很大。
	2、多线程环境 访问volatile变量不会发生阻塞，而synchronized可能会发生阻塞
	3、volatile可以保证数据的可见性，但是不能保证原子性；而synchronize的可以保证原子性也可以保证可见性
	4、关键字volatile 解决的是变量在多个线程之间的可见性；synchronized关键字解决多个线程之间的访问公共资源的同步性

一个应用程序在运行时会有多个进程，而一个人进程又包含多个线程---->每个进程都会有自己的生命周期，所以每个线程也都会有自己的生命周期
一个进程在jvm中会有一个堆，而每一个线程都会有一个自己的栈和程序计数器，而这些线程栈会共享进程堆和方法区
优点：
	1.提高应用程序的响应
	2.提高计算机系统cpu的利用率
	3.改善程序结构
应用场景：
	1.程序需要同时执行两个或者多个任务
	2.程序需要实现一些需要等待的任务时，如用户输入，文件读写操作，网络操作，搜索等
	3.需要一些后台运行时
Thread类方法详解：
start方法：①启动当前线程 ②调用当前线程的run方法
run方法：通常需要重写此方法，内容就是需要此线程做的事
currentThread方法：静态方法，返回执行当前代码的线程
getname方法：获取当前线程的名字
setname方法：设置当前线程的名字
yield方法：释放当前cpu执行权
join方法：在线程a中调用线程b的join方法，此时线程a就进入阻塞状态，直到线程b完全执行完以后，线程a才结束阻塞状态
stop方法：已过时，强制结束线程
sleep方法：带参数毫秒，让当前线程”睡眠“，在指定的毫秒内，线程是阻塞状态
isalive方法：判断线程是否还存活
线程的优先级：
	10 5(默认) 1
	getpriority方法 获取线程优先级
	setpriority	设置线程优先级
怎么实现多线程？
方法一：通过继承Thread类，重写run方法，用子类对象通过start方法启动线程
	1.创建一个继承Thread类的子类
	2.重写父类的run方法-->run方法内容就是需要此线程做的事
	3.实例化子类对象，通过子类对象start方法来启动多线程
方法二：实现Runnable类接口，重写run方法。
	1.创建一个实现Runnable接口的实现类
	2.实现runnabl接口类中的run方法
	3.示例化一个实现类的对象
	4.将这个对象作为参数传递给thread类的构造方法中，创建thread类的对象
	5.还是通过这个thread类对象调用start方法	
方法一与方法二比较：
开发中优先使用实现Runnable接口的方式来创建
原因：
	1.实现的方法没有单继承的局限性
	2.自然而然的解决多个线程共享数据的问题
	相同点：其实thread类也实现了Runnable接口
	1.都需要重写run()方法，将索要执行的逻辑写在run方法之中
	经典例题：消费者生产者问题
方法三：实现callable接口重写call方法并使用future来获取call方法的返回结果   
	jdk5.0新增方式
	1.创建一个实现callable接口的实现类
	2.实现call方法，将需要此线程所做的操作内容写入此方法中，需要注意的是call方法是具有返回值的
	3.创建实现类对象
	4.将此实现类对象作为参数传入futuretask构造器之中，创建futuretask对象
	5.将futuretask对象又作为参数出入thread构造器之中，创建thread对象
	6.通过thread对象的start方法来启动线程
	7.就可以通过futuretask对象的get方法获取到call方法的返回值，也就是线程的返回值，这个时候可能会异常需要抛出。
	实现runable接口和实现callable接口都可以实现多线程
	而实现callable接口相比于实现runable接口的优点在于
	call方法有返回值，并且还可以抛出异常也支持泛型 run方法没有返回值 
方法四：实现多线程池
	线程池；有多个线程组成的池子，提前创建多个线程，使用时直接获取，用完后返回，可以实现线程的重复利用
	有点：①减少创建新线程的时间，提高响应速度
		  ②重复利用线程，避免资源浪费
		  ③便于线程管理
		corepoolsize：核心池的大小
		maxnumpoolsize：最大线程数
		keepalivetime：线程存在时间
	ExecutorsService: 真正的线程池接口。常用的子类为ThreadPoolExecutors  通过这个子类的对象可以设置我们的线程池，使我们的线程池便于管理
Execuyors：线程池工厂类，用于创建线程池
	1.实例化创建指定数量的的线程池
	2.执行指定的线程的操作。需要提供实现Runnable接口或callable接口实现类的对象
	3.通过shoutdown方法关闭线程池
线程的生命周期：一般有五种状态
	创建，就绪，运行，阻塞，死亡
new
runnable
blocked
waitting
新建：当一个线程被new的时候就是新建
就绪：当线程调用start方法后就是进入就绪状态，此时还没有被CPU分配资源
运行：当线程获取到CPU执行权是就处于运行状态，当正在运行的线程失去CPU执行权或者被挂起时就又回到了就绪状态
阻塞：当正在运行的线程出现sleep，join，wait，等待同步锁，suspend的方法时，线程就会进入阻塞状态，阻塞状态结束的时候会回到就绪状态等待CPU执行
死亡：当正在运行的线程执行完run方法或者调用stoop方法或者出现异常没有解决的时候线程就会死亡，一个线程的最终状态也就是死亡

线程的同步：其实也就是为了解决线程的安全问题
同步的方法一：同步代码块
利用synchronized(同步监视器){
	//这里就是需要被同步的代码  同步的代码可以理解为操作共享数据的代码，就是需要被同步的代码  共享数据就是多个线程操作的变量
}
	说明：同步监视器 俗称锁 任何一个类的对象都可以充当锁 所有的线程需要共用一把锁
synchronized 
	优点：解决线程安全问题
	缺点：操作同步代码块的时候其实只允许一个线程运行，其他的线程则需要等待，相当于是一个单线程的过程效率低
同步的方法二：同步方法
	也是利用synchronized 将方法申明为同步方法
	也会涉及到同步监视器，只不过不会显示声明
	对于静态方法的监视器 默认为当前类本身
	对于非静态方法默认为 this 当前对象
死锁问题
	不同的线程分别占用对方需要的同步资源不放弃，都在等待对方放弃自己需要的同步资源，这样就形成了死锁问题		
同步的方法三：lock锁接口
		先要实例化lock
		调用lock上锁
		就一定要调用unlock解锁调用	
synchronized与lock锁的异同
	相同点：都可以解决线程安全问题
	不同点：synchronized在执行完同步代码块的内容时会自动释放lock锁
			lock需要我们手动上锁，和手动解锁		
线程安全问题的解决方式有三种
		同步代码块
		同步方法
		lock锁接口
线程的通信
	wait():执行此方法就会使当前线程就进入阻塞状态，并释放同步监视器
	notify()：执行此方法就会唤醒被wait的一个线程，此时如果有多个线程被wait就会唤醒优先级比较高的线程 都是位于java.Object
	notifyall()：执行此方法就会唤醒所有被wait的线程 都是位于java.Object类。
这三种方法的使用必须是在同步方法或者同步代码块之中
这三种方法的调用者也不一样 同步代码块或者同步方法的对象也就是同步监视器
这三种方法都是定义在onject类之中	
sleep方法和wait方法的异同
		相同点：都可以使线程进入阻塞状态
		不同点：申明的位置不同 sleep申明在threed类之中 wait申明在object之中
				调用要求不同 sleep在任何需要调用的地方都可以调用，wait只能在同步代码快之中调用
				是否释放同步监视器 如果两个方法都定义在同步代码快或者同步方法之中，sleep不会释放锁 wait会释放锁

## java常用类
### 字符串相关的类
String类及常用方法：
String是一个final类，不能够被继承也具有不可变性，字符内容实际上是存在一个字符数组之中
String实现了Serializable接口：表示字符串是支持序列化得
实现了Comparable接口:表示字符串是可以比较大小的
具有不可变性：也就是说在对字符串内容进行修改或者赋值是，都会在方法区字符串常量池之中重新赋值
通过字面量的方式赋值，不同于其他类的对象通过new，此时字符串是存放在方法区的字符串常量池之中
而且方法区的字符串常量池中是不允许存储相同内容的字符串
String的实例化方式
方式一：通过字面量方式
方式二：通过new+构造器的方式	
面试题：String s = new String(“abc”)创建了几个对象？
两个对象，一个堆里面的new构造器 一个方法区里面的abc
字符串调用interm方法，返回值就在方法区的字符串常量池之中
	

```java
    int length():返回字符串的长度值
    char charAt(int n):返回某索引处的字符
    boolean isEmpty():判断字符串是否为空
    String toLowercase():默认语言环境，将字符串中所有字符转换为小写
    String toUppercase():默认语言环境，将字符串中所有字符转换为大写
    String trim():返回字符串副本，忽略首部空白和尾部空白
    boolean equals(object obj)：比较字符串的内容是否相同
    boolean equalsIgnoreCase(object obj)：比较字符串的内容是否相同，会忽略大小写
    String concat(String str):将指定字符串连接到此字符串的结尾 类似于+
    nt compareTo(String anotherStr):比较两个字符串的大小
    String substring(int beginindex)：截取字符串，返回索引之后的字符串
    String substring(int beginindex，int endindex)：截取字符串，返回索引开始到结束的中间的的字符串，需要注意的是不会包含结束的那个索引也就是左闭又开
    boolean endswitch(String str)：测试字符串是否为指定字符串样进行结尾的
    boolean startswitch(String str)：测试字符串是否为指定字符串样进行开头的
    boolean startswitch(String str，int)：测试字符串在指定索引处是否为指定字符串样进行开头的
    boolean contains(String str)：判断字符串内是否包含指定字符串
    int indexOf(String str)：返回指定字符串在字符串中出现的索引位置
    int indexOf(String str，int index)：返回指定字符串在指定索引后字符串中出现的索引位置
    int lastindexOf(String str)：返回指定字符串在字符串中出现的索引位置，从后往前找
    int lastindexOf(String str，int index)：返回指定字符串在指定索引前字符串中出现的索引位置，从后往前找
    注意：没找到都默认返回-1
    替换：
    String replace(String oldstr,String newstr):将字符串中旧串替换为新串
    匹配：
    boolean matches(String regex):告知此字符串是否符合给定的正则表达式
    切片：
    String[] sqlit(String regex):根据给定的正则表达式拆分字符串
```

String类型与基本数据类型转换问题
	String--》基本类型：不能通过强转将字符串转换为基本类型，而应该调用基本类型的包装类的静态parseXXX(str)方法
	基本类型--》String：调用String重载的valueof(基本类型)方法 或者通过+拼接""字符串也可以		
String类型与char[]字符数组转换问题
String--》char[]:调用String类的tocharArray()方法返回字符数组
char[]--》string:将字符数组作为参数传入String的构造器中，就可返回得到一个字符串
String类型与byte[]转换问题
String-->byte[]:直接调用String的getbytes()
byte[]-->string：将byte[]作为参数传入String的构造器中，就可返回得到一个字符串
Stringbuffer类：
是可变序列，线程也是安全的，效率低 这个时候问题来了 我们为什么要说StringBuffer 是线程安全的呢 因为StringBuffer每一个公开的方法都是被synchronized 关键字所修饰 只允许一个线程进行访问 这样的话就导致效率偏低
	

```java
	StringBuffer append(XXX):字符串拼接
	StringBuffer delete(int startindex,int endindex):删除[str,end)指定位置内容左闭又开
	StringBuffer replace(int str,int end,String str):吧[str,end)的内容替换为str
	StringBuffer insert(int index,XXX):在指定位置插入XXX
	StringBuffer reverse():把当前字符串逆转
	public indexOf(String str)
	public String substring(int start,int end)
	public int length()
	public char charAt(int n)
	public void setcharAt(int n,char ch)将索引处的字符替换为c
```


Stringbuilder类：
	也是可变序列，线程是不安全的，但是效率高
	String 与StringBuffer与StringBuilder的异同
	String ①不可变的字符序列 内容和长度是不可以进行修改的，②并且重写了equals方法，③可以使用+来进行字符串的拼接
	Stringbuffer可变的字符序列 线程安全 效率低   ，
	Stringbuilder可变的字符序列 线程不安全 效率高 
	相同点：都与字符串相关;底层都是通过char[]字符数组进行存储的

### 时间相关的类
jdk8之前得日期时间api
System静态方法 currentTimeMillis()用来返回当前时间与1970年1月1日0时0分0秒之间的毫秒差，称为时间戳
Date类
	掌握两个构造器的使用
	Date() 创建当前时间的date对象
	Data(时间戳) 创建指定毫秒数的date对象
	掌握两个方法的使用
	tostring()打印显示当前年月日时分秒
	getTime()获取时间戳
Calender类
	是一个抽象类不能被直接实例化
	通常创建GregorianCalendar()子类对象或者调用其静态方法getinstance()来进行实例化	
常用方法
    get()
    set()
    add()
    gettime()
    settime()		
SimpleDdateFormat类 对date类的格式化和解析
常用格式：
	Date date = new Date();
	SimpleDateFormat simpleDateFormat = new 				 SimpleDateFormat("yyyy-MM-dd hh:mm:ss"); System.out.println(simpleDateFormat.format(date));
		格式化：将日期转化为字符串 通过format(Data date)
		解析：将字符串转化为日期 通过parse()  要求格式必须符合格式化的格式，否侧会抛异常			
Date年偏移量1900 月偏移量1
jdk8新增日期时间api
以前的问题：有偏移性，线程也不是安全，
新版具有不可变性
实例化 调用now()方法获取当前
of()方法：设置指定年月日时分秒，没有偏移量
getXXX()获取需要的值
withXXX()设置需要的值
LocalDate本地日期
LocalTime本地时间
LocalDateTime本地日期时间
Instant 时间线上的一个点
DateTimeFormatter
通过ofpattern方法来进行实例化
类似于simpleDateformater用于格式化和解析

### Java比较器
Comparable接口 自然排序
	像String,包装类等实现了compareable接口，重写compareto(obj)方法 这个方法的内容就是比较两个对象的方法 默认从小到大
Comparator接口 订制排序按照参数来比较
	重写compare(object obj，object obj)(这两个接口都是比较对象的)
两者的区别：
	comparable接口的方式一旦确定，保证接口实现类的对象在任何位置都可以比较大小
	comparator接口属于临时性的比较。

### System类
方法
	exit():退出系统
### Math类
提供一些常用的数学方法
	abs 绝对值
	random 随机数
### BigInteger和BigDecimal
	前者对数字长度
	后者对数字特别是浮点数精度可以做处理
## 枚举型&注解
枚举类
	类似数学枚举法 类的对象是有限个的并且是确定的
	当需要定义一组常量时，强烈建议使用enum
	如果枚举类中只有一个对象，就可以看成单例模式的一种实现方式
	枚举类的理解：类的对象只有有限个，确定的。我们称此类为枚举类
	当需要定义一组常量时，强烈建议使用枚举类
	如果枚举类中只有一个对象，则可以作为单例模式的实现方式(详细见构建者模式之单例模式)。
	枚举类的属性
	枚举类对象的属性不应允许被改动, 无setter()方法，所以应该使用 private final 修饰；
	枚举类的使用 private final 修饰的属性应该在构造器中为其赋值 ；
	枚举类的对象有限，所以构造器应该设置成私有，不允许外界添加；
	若枚举类显式的定义了带参数的构造器, 则在列出枚举值时也必须对应的传入参数。
    如何定义枚举类？
    方式一：jdk5.0之前 自定义枚举类
    ①申明自定义枚举类对象的属性：用private final修饰
    ②私有类的构造器，并给对象属性赋值
    ③提供当前类的多个枚举对象，public static final的
    ④其他诉求：获取枚举类对象的属性通过gat/set方法
    ⑤其他诉求：提供toString方法，避免对象打印出地址值
    方式二：jdk5.0 通过enum关键字
    如何使用关键字enum来定义枚举类
    ①不需要class修饰类名而使用enum来修饰类名
    ②提供当前枚举类的对象，多个对象之间使用‘，’隔开末尾分号结束
    ③申明自定义枚举类对象的属性：用private final修饰
    ④私有类的构造器，并给对象属性赋值
    ⑤其他诉求：获取枚举类对象的属性通过gat/set方法
    Enmu类的主要方法
    values()返回枚举类型的对象数组可以很方便的遍历所有枚举值
    valueof(String str)返回一个和str同名的枚举对象，如果没有找到，会报异常
    tostring()返回当前枚举类对象常量的名称
    实现接口的枚举类
    情况一：实现接口，在枚举类中实现接口抽象方法
    情况二：让枚举类对象分别实现抽象方法，个人感激啊有点类似于多态了
注解(Annotation)
注解概述
在jdk5.0新增 其实就是代码里的特殊标记
框架=注解+反射+设计模式
注解前面都会有@符号
常见注解示例
示例一：文档注解
示例二：在编译时进行格式检查(jdk中内置的三个注解)
@Override 限定重写父类方法，该注解只能用于方法
@Deprecated 用于表示所修饰的元素已过时
@SuppressWarmings 抑制编译器警告
示例三：跟踪代码依赖性，实现替代配置文件功能
Servlet3.0提供注解，使得不需要在配置文件中进行servlet配置
spring框架中关于事务的管理
自定义注解 --参照SuppressWarmings注解定义
通过@interface 关键字定义
注解的成员变量无参方法的形式来申明
①注解声明为@interface
②内部定义成员通常value表示
③可以指定成员变量的默认值 通过default
④如果注解没有成员，那么就是一个标识，如果有就要给值
自定义注解必须配备上特定的信息处理流程(使用反射)才有意义
自定义注解通常都会指明两个元注解 retention target
jdk中的元注解
提供四种 元注解就是用于修饰注解的注解
retention指定注解的生命周期
target 用于限制注解可以修饰那些程序元素
利用反射获取注解信息
jdk8中注解新特性
可重复注解
类型注解
(都是jdk5.0新增内容

## java集合
### java集合框架概述
集合，数组都是对多个数据进行存储的 简称Java渣蛙容器  这个存储主要是指内存层面的，不涉及持久化
Array(数组)弊端：长度确定，类型确定 提供的方法很少，对于增删改查非常的不便 不能获取到实际元素个数 有序，可重复注解
分为两个大接口 Collection 单列数据存储一个一个的对象和Map 双列数据 用来存储一对一对的数据
ArrayList：元素有序 可重复 线程不安全
hashSet：元素无序 不可重复 线程不安全 可以存null
hashMap：双列集合 也就是一种键值对的集合，其中key是不可以重复的且无序，作为key对应的value只是可以重复的 并且需要注意的是key和value都是可以为空的 同样的是 他也是线程不安全的
### Collection接口方法
单列集合

```java
add(object obj):将元素obj添加到集合的方法 注意要求obj所在的类必须重写equals方法
size():获取集合元素个数
addall(Collection co):将co集合的所有元素添加到集合中
clear()：清空集合元素
isEmpty():判断集合是否有元素，这是一个返回值为布尔类型的函数
contains(object obj)：判断当前集合中是否包含obj 注意：我们在判断的时候会调用obj所在类的equals
containsAll(Collection coll)：判断集合coll中所有元素都存在与当前集合之中
remove(Object obj):从当前集合中移除元素obj 注意这个也默认要求obj所在类重写equals方法 会通过equals方法判断obj是否存在
removeAll(Collection coll):从当前集合中移除coll中所有的元素 相当于数学中的差集
retainALL(Collection coll)：获取当前集合和coll集合中相同的元素 相当于数学中交集
equals(object obj):判断当前集合与形参集合是否相同
hashcode()定义在object中 返回当前对象的哈希值。
toArray()：将集合转换为数组 扩展：
aslist()：	将数组转换为集合 调用Arrays类的静态方法aslist()
iterator():返回迭代器iterator接口的示例，用于遍历Collection集合元素
```


### lterator迭代器接口
一般都是通过集合对象调用iterator方法返回一个迭代器的示例
iterator迭代器有:
两个方法一个是 hasNext()判断是否还有下一个 
next()指针下移读取下一个值
集合每次调用iterator方法时都会得到一个全新的迭代器对象
默认的指针都在集合第一个元素之前
迭代器内部定义了一个remove方法，可以在迭代器遍历的时候删除集合中的元素
jdk5.0新增特性增强for循环 for(集合元素类型 局部变量:集合对象)

### Collection子接口list 

​	元素有序 可重复 “动态”数组 底层长度为10
​	通常使用list来替代数组
​	常用的实现类有三个 ArrayList LinkedList vector
​	三者的异同：都实现了list接口，存储特点也是相同的有序可重复

ArrayList 作为list主要实现类，线程是不安全的，效率高 底层使用的object[]存储.

vector 作为list的古老实现类 ，线程安全 效率低 底层使用的object[]存储

list集合除了继承Collection的方法外还提供了根据索引来操作集合的方法

```java
void add(int index，object e)：在index出插入元素e  (如果没有写index时 会默认在集合的末尾进行数据的添加)
boolen addAll(int index,collection coll):在index处，插入集合coll的所有元素
Object get(int index)：获取指定集合中指定index下标处的值
int indexOf(Object obj):返回obj在当前集合中首次出现的位置
int lastindexof(object obj)：返回obj在当前集合中末次出现的位置
object remove(int index)：移除指定index位置的元素，并返回此元素
object set(int index，object ele)：设置指定index位置的元素为ele
list sublist(int fromindex，int toindex)：返回从fromindex到toindex的子集合
总结常用方法
增：add(obj)  这个方法可以有两个参数，第一个参数为添加元素的下标值(可以写也可以不写，不写的话默认为数组最后一个位置)，第二个元素为需要添加的元素值这个是必须要写的
删：remove(Object obj)/remove(int index)  也可以是数组中存在的值也可以是数组中的下标，一般情况下都是索引-
改：set(index,newdata) 此方法将数组下标索引处的值修改为新的值 需要注意的是此处的操作实际上是一个修改的操作
查：get(index) 需要注意的是此方法执行时 参数一定是数组的下标值，获取数组集合某处下标处的位置
插：add(index,data) 向数组集合中插入数据 需要注意的是 方法有两个参数，第一个参数是插入数据在数组集合中的下标值可以写也可以不写，不写的话默认为数组最后一个位置)，第二个元素为需要添加的元素值这个是必须要写的
长度：size()  注意size是元素的个数并不是底层数组的长度
```


遍历：①iterator迭代器
②增强for循环
③普通for循环

### Collection子接口set 

​	元素无序 不可重复 类似高中数学中的“集合” 底层其实是map
​	三个主要实现类：Hashset，linkedhashset，treeaet
​	Hashset：作为set借口的主要实现类，线程不安全可以存储null值  在底层也是通过数组+链表进行存储的(jdk7)
​	linkedhashset：是hashset的一个子类，遍历内部是时可以按添加的循序进行遍历
​	Treeset：可以按照添加对象的指定属性，进行排序

如何理解set接口的无序性和不可重复性  
无序性：不是随机性，而是理解为以哈希值进行数组存储的的顺序
不可重复性：通过equals来判断，相同的元素只能添加一个

set借口没有新添加的方法，全部使用的是Collection的方法

要求：向set接口中添加数据，其所在得类一定要重写equals和hashcode方法

Treeset：在添加对象时只能添加相同类的对象，可以按照添加对象的指定属性，进行排序

### Map接口  
双列集合，用来存储一对一对的数据 类似高中数学中的函数    
key 不能重复 无序(使用set存储key  key可能是一个对象如果是一个对象的话就要求可以所在得类必须重写equals和hashcode方法) 
value 可以重复 一般使用colllection存储所有的value 如果value是对象 那么要求对象所在的类要重写equals方法

一个键值对就是key-value构成一个entry对象，map中的entry对象使用set存储
有三个常用的实现类分别为：Hashmap，linkedHashmap，hashTable
Hashmap：作为map主要的实现类，线程不安全的，效率高，能存储null的key和value  数组+链表+红黑树
linkedHashmap：作为hashmap的子类，保证在遍历map元素时，可以按照添加的循序进行遍历。原因：在原有的底层基础上，添加了一对指针，指向前一个和后一个，对于频繁的遍历，效率高于hashmap
Treemap：保证在key-value对进行排序，实现排序遍历，考虑对key进行自然排序和订制排序 底层使用红黑树实现
hashTable：作为古老的实现类，线程安全的，效率低，不能存储null的key和value
有一个子类 properties 使用来处理配置文件的 所有的key和value都是字符串的

HsahMap的底层实现原理？
在jdk8之前 使用的是数组+单向链表 在jdk8之后 使用的是 数组+链表+红黑树
jdk7版本
HashMap map = new HashMap();
在实例化以后底层创建了一个16长度的一维数组entry[] table
map.put(key1,value1):执行添加操作
首先，调用key1所在类的hashcode方法计算哈希值，次哈希值经过某种算法后，得到在entry数组中分存放位置
如果存放位置为空，此时key1-value1添加成功 ----》情况1
如果存放位置不为空(意味着此位置存在一个或多个数据(以链表的形式存在))比较key1和已经存在的一个或多个数据的哈希值
如果key1的哈希值与存在的哈希值不相同，此时key1-value1添加成功 ----》情况2
如果key1的哈希值和已经存在的某一个数据(key2-value2)的哈希值相同，继续比较：调用key1所在类的equals(key2)方法
如果equals返回false：此时key1-value1添加成功 ----》情况3
如果equals返回true：使用value1替换value2结束，相当于如果有重复的key哈希值就对原先的值进行修改

补充：关于情况2和情况3：此时key1-value1和原来的数据以链表的方式存储
在不断的添加过程中，会涉及到扩容的问题，当超出临界值并且存放位置索引不为空时扩容 默认的扩容方式为扩容到原来的2倍，并将原来的数据复制过来

jsk8版本 相较于jdk7在底层实现的不同
1.在new HashMap()：底层不会创建一个长度为16的数组
2.底层的数组是node[]而非entry[]
3.首次调用put方法是，才会在底层创建一个16的数组
4.jdk7的底层结构为数据+链表 jdk8底层使用的是 数组+链表+红黑树
当数组的某一索引位置已经以链表的形式存在，存在的数据个数>8 并且 整个数组的长度>64时，
此时索引位置上的数据全部改为红黑树进行存储

hashmap的哈希函数是如何设计的？
将hashcode的高16位和低16位进行 位亦或操作 两个好处 ①尽可能降低哈希碰撞，越分散越好 ② 算法一定要尽可能高效 因为这是高频运算 追求高效 因此采用位运算

LinkedHsahMap的底层实现原理？

Map接口中常用的方法

```java
添加，删除，修改操作方法
Object put(Object key,Object value) 将指定的key-value添加或修改到map对象之中
void putAll(Map m) 将m中所有的key-value键值对存放到当前map之中
Object remove(Object key) 将指定key的键值对移除，并返回指定key的value值
void clear():清空当前map中的所有元素

元素查询的操作
Object get(Object key): 获取指定key对应的value值
boolean containskey(Object key): 判断是否包含指定key
boolean containsvalue(Object value): 判断是否包含指定value值
int size():返回map中键值对的个数
boolean isEmpty():判断当前map是否为空
boolean equals(Object obj):判断当前map和参数对象obj是否相等

原始图的操作
set keyset():获取所有的key集合所构成的set集合
coll values():获取所有value值集合所构成的Collection集合
set entryset():返回所有key-value对所构成的set集合

总结常用的：
增：put(Object key,Object value)
删：remove(Object key)
改：put(Object key,Object value)
查：get(Object key)
长度：size()  注意size是元素的个数并不是底层数组的长度
遍历：set keyset()  /   values()  /  entryset()
```

Treemap：中key要求必须是同一类型的对象
因为要按照key进行排序，自然排序 订制排序
### Collections工具类

面试题：Collection 和Collections的区别
Collection 是一个集合的接口 里面封装有list和set
Collections是一个用来操作list set map集合的工具类

是一个操作list set map等集合的工具类
常用方法

```java
reverse(list):反转list中元素的顺序
shuffle(list):对 list集合中的元素进行随机排序
sort(list):根据元素的自然顺序对指定的list集合元素按升序排序
sort(list,compareator):根据指定的compareator对指定的list集合排序
swap(list,int i,int j):将集合list的i处和j处进行交换

Object max(collection):根据集合的自然排序，返回给定集合中最大的值
Object max(collection，compareator):根据集合的订制排序，返回给定集合中最大的值
Object min(collection)

int frequency(collection,obj):返回在指定集合中元素obj出现的次数
void copy(list1,list2)：将list2中的元素复制到list1之中
```
也提供了多个线程安全的方法
synchronizedXXX(list):将list集合转化为对应的线程安全的集合

## java泛型

1.为什么要有泛型
	泛型(generic) 可以理解为标签
	泛型就是在定义类的时候通过泛型来限制数据的类型，数据的类型是一定要与泛型是相同的数据类型
2.在集合中使用泛型
	在集合中不使用泛型，可能再添加数据的时候添加到了很多不一样的类型数据
	注意：泛型不能是基本类型，必须是包装类
	在集合中使用泛型进行类型检查保证数据安全
3.自定义泛型结构
	静态结构不能使用泛型
	异常类也不能申明为泛型
4.泛型在继承上的体现
	类a是类b的父类，所以他们就具有子父类之间的关系，但是G<a>和G<b>二者是不具备子父类的关系，二者是并列关系
	补充：类a是类b的父类，如果是这样a<G> 和 b<G>就具备了子父类之间的关系
5.通配符的使用
	通配符：？ 
	使用通配符之后 list<?> 不能向其添加数据，但是只允许添加null但是可以读取数据
6.泛型应用举例

## java IO流
1.File类的使用
File类表示的就是文件和文件目录路径
1.一个File类的对象，代表一个文件或者一个文件目录
2.File类声明在java.io包下
3.在File类中并没有涉及到写入或者读取文件内容的操作  注意 文件的读写操作都是通过不同的六来进行操作 但是根据本人经验相关 通常使用一个流的时候都会将一个file对象作为参数传递给流构造器
4.后续File类的对象常会作为参数传递到流的构造器之中
File常用的构造器：
File(String pathname):以pathname为路径创建file对象，可以是绝对路径或者相对路径
File(String parent，String child)：以parent为父路径，child为子路径创建file对象
File(File parent，String child)：根据一个父file对象和子文件路径创建File对象
Files类的常用方法

```java
public String getabsolutepath():获取绝对路径
public String getPath()：获取路径
public String getname()：获取文件名称
public String getparent()：获取上层文件名称，或没有就为null 
public long length()：获取文件长度(即字节数)，不能获取目录的长度 注意这个length其实就是文件的大小
public long lastmodified()：获取最后一次修改的时间，是一个时间戳毫秒值

用于文件目录
public String[] list():获取指定目录下的所有文件或者文件目录的名称数组
public File[] listFiles():获取指定目录下的所有文件或者文件目录的File数组
文件重命名
public boolean renameTo(File dest):将文件重命名为指定的文件路径
比如：File1.renameTo(File2)为例
要想保证返回true，方法执行chengg，就必须保证file1是真是存在的，file2是不能存在的
用于判断
public boolean isDirectory():判断是否是文件目录
public boolean isFile():判断是否是文件
public boolean exists():判断是否存在
public boolean canread():判断是否可读
public boolean canwrite():判断是否可写
public boolean isHidden():判断是否隐藏

创建硬盘中对应的文件或文件目录
public boolean createNewFile():创建文件，若文件存在，则不创建，返回false
public boolean mkdir():创建文件目录，如果此文件目录存在，就不创建了，如果此文件目录的上层文件不存在也不创建
public boolean mkdirs():创建文件目录，如果上层文件不存在，一并创建

注意，如果创建文件没有写路径，那么默认在项目文件路径下

删除磁盘照片那个的文件或者文件目录
public boolean delte()：删除文件或者文件夹 删除目录时 文件 中不能还有文件夹和文件
注意：java中删除不走回收站
```

2.IO流原理及流的分类
IO：input和output的缩写 处理设备之间的数据传输
在java中，数据的传输都是以流的形式进行传输

流的分类：按数据来分为字符流和字节流
按流向来分为输入流和输出流
按角色功能来分为 节点流和处理流

流的四个抽象基类  字节流       字符流
输入流        inputStream  Reader 
输出流		  outoutStream Writer

节点流      处理流
Fileinput
读取文件 从硬盘文件中读取数据到内存里
1.实例化file类的对象,指明要操作的文件，这文件必须存在不然会报错
2.提供具体的流 FillReader  注意  这里的意思就是 new一个流对象 但是需要注意的是要将file对象作为参数传递给流构造器
3.数据的读入
read()返回读入的一个字符，如果达到文件末尾，返回-1
read(char[] cbuf):返回每次读入cbuf数组中的字符个数，如果达到文件末尾返回-1
4.关闭数据流

写入文件 从内存中写出数据到硬盘的文件里
1.示例化file类的对象，指明要操作的文件 与读取不同的是 写入的文件如果不存在，会自动帮我们创建文件
2.提供具体的流对象 FileWriter
3.写入的操作  如果重复执行会讲原文件覆盖掉
Writer(Str,append) append默认为false 就是不会追加内容
4.关闭数据流

总结：对于文本文件需要使用字符流处理
对于非文本文件需要使用字节流来进行处理
3.节点流(文件流)
FileinputStream 字节输入节点流  用来读取文件
FileOutputStream 字节输出节点流
FileReader 字符输入节点流 用来输出文件
FileWriter 字符输出节点流
4.缓冲流
处理流的一种
BufferedInputStream  字节输入缓冲流
BufferedOutputStream 字节输出缓冲流
BufferedReader	字符输入缓冲流
BufferedWriter	字符输出缓冲流
注意在造流的时候一定要先实例化节点流，再将节点流对象出入缓冲流构造器实例化缓冲流的对象
作用：提高流的读取和写入的速度
原因：内部提供了一个缓冲区
处理流就是“套接”在已有的流的基础上
5.转换流 属于字符流
作用：提供了字节流和字符流之间的转换
InputStreamReader： 将字节的输入流转换为字符的输入流
OutputStreamWriter：将字符的输出流转换为字节的输出流
6.标准输入，输出流
System.in: 标准的输入流，默认从键盘输入
System.Out：标准的输出流，默认从控制台输出
7.打印流
8.数据流
9.对象流
对象序列化机制，将java对持久化得保存在硬盘文件中，或者通过网络传输出去
ObjectInputStream 反序列化 将文件中的数据转化为内存中的一个对象
ObjectoutputStream 序列化 将内存中的java对象保存在磁盘中或通过网络传输出去

一个类的对象需要满足一下条件
1.实现serializable接口
2.需要当前类提供一个id常量
3.还要保证该类的所有属性也是可以序列化的 ，默认java基本数据类型都是可以序列化的

注意：static和transient修饰的成员变量是不可以进行序列化的

10.随机存取文件流
RandomaccessFile:直接继承与object类 实现了datainput和dataouput接口 可读可写

## java网络编程
1.网络编程概述
2.网络通信要素概述
3.通信要素1：IP和端口号
4.通信要素2：网络协议
5.TCP网络编程
	客户端
	1.创建socket的对象，指明服务器端的ip和端口号
	2.获取一个输出流，用于输出数据
	3.用流来写出数据的操作
	4.关闭流
	服务器端
	1.创建一个serversocket 指明自己的端口号
	2.调用对象的accept方法接受客户端的socket
	3.获取一个输入流
	4.通过输入流读数据
6.UDP网络编程
	客户端
	1.创建Datagramsocket类
	2.
7.URL编程
	url：统一资源定位符

## java反射机制
JAVA的反射机制主要作用是用来访问对象的属性、方法等等
1.关于反射机制的概述 反射的特征：动态性
	主要使用的API
		java.lang.class:代表一个类
		java.lang.reflect.method：代表类的方法
		java.lang.reflect.Field：代表类的成员变量
		java.lang.reflect.constructor：代表类的构造器
2.理解class类并获取class实例
	1.调用运行时类的属性：.class
		Class class1 = Person.class;
	2.通过运行时类的对象调用getClass()
		Person p1 = new Persoon();
		Class class1 = p1.getClass();
	3.调用Class的静态方法forName();
		Class class1 = Class.forName("类的全包名");
3.类的加载和classloader的理解
	使用类加载器读取配置文件
		Properties pros = new Prooerties();
4.创建运行时类的对象
	Class<Person> clazz = Person.class;
	Person obj = clazz.newInstance();
	说明：newInstance():调用此方法，创建对应的运行时类的对象。内部调用了运行是类的空参的构造器。
		  要想此方法正常的创建运行时类的对象，要求：
		  1.运行时类必须提供空参的构造器
		  2.空参的构造器的访问权限得够。通常，设置为public。
		  在javabean中要求提供一个public的空参构造器。原因：
		  1.便于通过反射，创建运行时类的对象
		  2.便于子类继承此运行时类时，默认调用supper(),保证父类此构造器
5.获取运行时类的完整结构
6.调用运行时类的指定结构
7.反射的应用：动态代理
	动态代理：
		1、什么是动态代理？
			使用jdk的反射机制，创建对象的能力，创建的是代理类的对象，而不用你创建类文件，不用写java源文件
			动态：在程序运行时。调用jdk提供的方法动态创建代理类的对象
			注意：jdk动态代理 要求目标类必须实现接口，没有接口的话就需要使用cglib动态代理
		2、知道动态代理能做什么？
			在不改变目标类的功能方法前提下，在代理类中增强自己的功能代码。
			在实际程序开发中的意思
				比如 你所在的项目中，有一个功能是其他人已经写好的 你可以使用
				GoNong.class;   GoNong go = new GoNong(); go.方法()
				你发现这个功能，现在还缺点意思，不能完全满足项目的需要，我们需要在go.方法()执行后，需要自己再增加代码
				用代理实现go.方法()调用时，增加自己的代码，而不用去修改原GoNong文件
	在静态代理中目标类很多的时候，可以使用动态代理，避免静态代理的缺点
	在动态代理中即使目标类很多 1)代理类的数量可以很少 2)当你修改了接口中的方法是不会影响到代理类
	通常我们的代理类主要完成两个功能：1)对目标类就是被代理类的方法的调用 2)在不改变原来代码的基础上实现新功能的增强
	动态代理是指代理类对象在程序运行是由我们的jvm动态生成的，动态代理是不需要定义代理类的.java源文件的
	动态代理其实jdk运行期间，动态创建class文件并加载的jvm
	动态代理常见的实现方式有两种 ①jdk动态代理 ②cglib动态代理
	依赖注入的原理就是动态代理

```text
jdk动态代理：
	jdk动态代理是基于java的反射机制实现的，使用jdk中的接口和类实现代理对象的动态创建。
	jdk动态代理是要求我们的目标对象(被代理类)必须实现接口，这是java设计上的硬性要求
	从jdk1.3以来，java语言通过java.lang.reflect包提供三个类来实现动态代理 Proxy、Method、InvocationHander(InvocationHander接口叫做调用处理器，负责调用目标类的方法，并增强功能，通过代理对象调用接口中的方法，会把方法的调用分配给调用处理器的实现类也就是invocationhander接口的实现类，会自动执行类中的invoke方法)，我们需要做的就是在invoke中调用目标类的方法，并进行增强。
cglib代理：
	cglib是一个开源项目，是一个强大的，高性能的，高质量的code生成类库，它可以在项目运行期间扩展java类与实现java接口，它广泛的被许多AOP(面向切面编程)框架使用，例如SpringAOP.
	使用JDK的Proxy实现代理，要求目标类与代理类实现相同的接口，若目标类不存在实现的接口，那么就无法使用这种方式实现动态代理。
	对于无接口的类，要为其创建动态代理，就要使用cglib来实现cglib的原理是生成目标类的子类，而子类都是增强过的，这些子类其实就是不同的代理类，子类对象就是代理对象。所以使用cglib实现动态代理 要求我们的目标类是要能够被继承的 即目标类不是被final所修饰的类,调用的方法也是不能被final修饰的
	cglib的要求是比较宽松的，只要能继承就行。经常被使用在框架中，例如spring，hibernate等，并且我们的cglib的代理效率是要高于我们的jdk的，
	在我们真实的项目当中是很少使用到jdk来实现动态代理的 
```
JDK实现动态代理：
		1. 反射，Method类，表示方法，类中的某个方法，通过Method可以执行某个方法。
		2. jdk动态代理的实现
			反射包 java.lang.refrct 里面有三个东西 invocationhander、Method、Proxy
			1)invocationHander接口(调用处理器)：就一个方法 invoke(Object proxy,Method method,Object[] args)
				invoke()：表示代理对象要执行的功能代码，我们的代理类要完成的功能就写在这个方法之中 ①调用目标方法执行目标方法的功能 ②功能增强，在目标方法调用时增加功能
				方法原型
				参数：Object proxy jdk创建的代理对象无需赋值
					  Method method 目标类中的方法，jdk提供method对象的
					  Object[] args 目标类中方法的参数，jdk提供的
				public Object invoke(Object proxy,Method method,Object[] args)
				invocationHander接口：表示你的代理要干什么
				怎么用：①创建类实现接口invocationHander
						②重写invoke方法，把原来静态代理类要完成的功能写在这
			2)Method类:表示方法的，确切的说表示目标类中的方法
				作用：通过method可以执行某个目标类的方法 method.invoke(目标对象，方法参数)
			3)Proxy类：核心的对象，创建代理对象。之前创建对象都是new类的构造方法，现在我们使用proxy类的方法代替
				方法：静态方法newProxyInstance() 作用是创建代理对象 等同于new一个代理类对象
				参数：
				1、ClassLoader loader: 类加载器 负责像内存中加载对象的，使用反射获取对象的classloader 固定写法
				2、Class<?> interface: 接口 目标对象实现的接口，也是通过反射获取的 固定写法
				3、InvocationHander h: 我们自己写的代理类要完成的功能
				返回值：就是动态创建的代理对象
	实现步骤
		1、创建接口，定义目标类要完成的功能。
		2、创建目标类实现接口
		3、创建InvocationHander接口的实现类，在invoke方法中完成代理对象需要完成的功能 ①调用目标方法 ②增强功能
		4、使用proxy类的静态方法，创建代理对象，并把返回值转为接口类型。

## java  JDBC
1.加载数据库驱动
	Class.forName("com.mysql.jdbc.Driver");
2.通过Drivermanager的getConnection方法获取数据库连接对象
	Connection conn = DriverManager.getConnection("jdbc:mysql://localhost:3306/jdbc","root","123456");
3.通过数据库连接对象获取statement对象
	Statement statement = conn.createStatement();
4.通过statement对象执行sql语句,并通过resultset保存返回结果
	 ResultSet resultSet = statement.executeQuery("select * from tb_user");
5.通过resultset对象操作结果集
	这里我们通常会将resultset的结果集转为list<Map>

```java
//ResultSet 转List<Map>
    public static List<Map<String, Object>> toListMap(ResultSet ret) throws SQLException{
        List<Map<String, Object>> list = new ArrayList();
        ResultSetMetaData meta = ret.getMetaData();
        int cot = meta.getColumnCount();
        while(ret.next()) {
            Map<String, Object> map = new HashMap();
            for(int i = 0; i < cot; i++) {
                map.put(meta.getColumnName(i + 1), ret.getObject(i + 1));
            }
            list.add(map);
        }
        return list;
    }
```

在我们的mybatis中 是如何批量插入或者更新数据的呢？
	一般我们通常会在XML文件中使用mybatis的<foreach>标签循环遍历
	在我们的mybatis中我们的foreach标签经常被使用到遍历集合，构建in条件语句和批量删除

```sql
SELECT * FROM product_ 
    WHERE ID in
            <foreach item="item" index="index" collection="list"
                open="(" separator="," close=")">
                         #{item}
            </foreach>
```

foreach 标签主要有以下属性，说明如下。
item：表示集合中每一个元素进行迭代时的别名。
index：指定一个名字，表示在迭代过程中每次迭代到的位置。
open：表示该语句以什么开始(既然是 in 条件语句，所以必然以(开始)。
separator：表示在每次进行迭代之间以什么符号作为分隔符(既然是 in 条件语句，所以必然以,作为分隔符)。
close：表示该语句以什么结束(既然是 in 条件语句，所以必然以)开始)
使用 foreach 标签时，最关键、最容易出错的是 collection 属性，该属性是必选的，但在不同情况下该属性的值是不一样的，主要有以下 3 种情况：
如果传入的是单参数且参数类型是一个 List，collection 属性值为 list。
如果传入的是单参数且参数类型是一个 array 数组，collection 的属性值为 array。
如果传入的参数是多个，需要把它们封装成一个 Map，当然单参数也可以封装成 Map。Map 的 key 是参数名，collection 属性值是传入的 List 或 array 对象在自己封装的 Map 中的 key。

浅说一下mybatis的缓存

```text
一级缓存：基于PerpetualCache的HashMap本地缓存，其存储作用域为Session，当我们的session flush或者close之后，该session中的所有Cache就将清空，默认打开一级缓存
二级缓存：与一级缓存及其机制相同，默认也是采用PerpetualCache，HashMap存储，不同在于其存储作用域为Mapper(namespace)，并且可以自定义存储源，如Ehcache。默认不打开二级缓存，要想开启二级缓存，要开启二级缓存，使用二级缓存属性类需要实现Serializable序列化接口(可用来保存对象的状态)，可在它的映射文件中配置；
```

## java执行过程

java执行过程通常来说 有两个关键步骤 编译 解释执行
java类在被加载到虚拟机中是有七个 生命周期
.java文件其实就是我们程序员所书写的java源码
.class文件 是我们源码经java虚拟机编译后生成的字节码文件

双亲委托模型的工作过程是：如果一个类加载器收到了类加载的请求，它首先不会自己去尝试加载这个类，
而是把这个请求委托给父类加载器去完成，每一个层次的类加载器都是如此，因此所有的加载请求最终都应该传送到顶层的启动类加载器中，只有当父类加载器反馈自己无法完成这个加载请求(它的搜索范围中没有找到所需要加载的类)时，子加载器才会尝试自己去加载。
使用双亲委托机制的好处是：能够有效确保一个类的全局唯一性，当程序中出现多个限定名相同的类时，类加载器在执行加载时，始终只会加载其中的某一个类。
注意：所谓限定名其实就是 含包文件路径类名称 全限定名= 包名+类名

## JDK8 新特性

1、Lambda表达式
	其实偶然细想一下java8 有两个新特性 很像我们的es6的语法 就想我们的这个lambda表达式 像不像es6的箭头函数 你品 你细品
	举例：

```java
(o1，o2)-> Integer.compare(o1,o2)
    格式：
    	-> : Lambda操作符 或者叫做 剪头操作符
        ->左边 ：lambda形参列表 (其实就是接口中抽象方法的形参列表)
       	->右边 ：Lambda体(其实就是重写的抽象方法的方法体)
//lambda表达式的使用(分为6种情况)
//语法格式一：无参，无返回值
Runnable r1 = ()->{System.out.println("hello world");};
//语法格式二：lambda需要一个参数，但是没有返回值
Consumer<String> con = (String str)->{System.out.println(str);};
//语法格式三：数据类型可以省略，因为可由编译器推断得出 称为 类型推断
Consumer<Stting> str = (str)->{System.out.println(str);}
```
