# 1java

##### java API文档

###### API 应用程序编程接口，是java提供的基本编程接口。

![image-20230221093235945](C:\Users\businessman\AppData\Roaming\Typora\typora-user-images\image-20230221093235945.png)

字符类型（char）

◆字符类型可以表示**单个字符**，字符类型是char，char是两个字节（可以存放汉字），多个字符可以用String字符串。

字符类型（char）

◆字符类型使用细节

1.“9”表示的是字符串，‘ 9’表示的才是字符类型

例如：char c1 = 'a'; char c2 = '中';char c3 = '9';

2.Java中还允许使用转义字符 **‘\’** 来将其后的字符转变为特殊字符型常量。例如：char c3 = **'\n'**合起来表示一个字符; // '\n'表示换行符

3.在java中，char的本质是一个整数，任何输出都是字符，例如：97对应的是a

![image-20230221102847130](C:\Users\businessman\AppData\Roaming\Typora\typora-user-images\image-20230221102847130.png)



◆字符类型本质探讨



1.字符型 存储到 计算机中 需要将字符对应的码值（整数）找出来，比如'a'存储：‘a' ==> 码值97（ASCII） ==> 二进制（01100001） ==> 存储到计算机中

读取： 二进制（1100001） => 97 ===> 'a' => 显示

编码：计算机的语言

◆编码类型

**ASCII**（ASCII表1.一个字符由一个字节表示 2.一共有128个字符），但是实际上一个字节可以表示256个字符，ASCII只用128个，原由是美国人用128个也够了，英文字母，可以多组合来构建。

**Uni（统一）code（编码）** （Unicode表 固定大小的编码 使用两个字符来表示字符，字母和汉字同统一都是占用两个字节，冗余浪费空间）。

**utf-8**（编码表，大小可以变的编码，字母使用1个字节，汉字使用3个字节）转gbk报错，大的放到小的里面会报错。

**gbk**（可以表示汉字，而且范围广，字r使用1个字节，汉字2个字节）。

**gb2312**（可以表示汉字，了解即可，gb2312 < gbk）。

**big5 码** （台湾地区，香港使用，繁体汉字，了解即可）。



![image-20230221105258926](C:\Users\businessman\AppData\Roaming\Typora\typora-user-images\image-20230221105258926.png)

![image-20230221105921167](C:\Users\businessman\AppData\Roaming\Typora\typora-user-images\image-20230221105921167.png)

![image-20230221110200841](C:\Users\businessman\AppData\Roaming\Typora\typora-user-images\image-20230221110200841.png)



◆布尔类型 Boolean

1.占一个字节，适用逻辑运算，

2.使用细节说明：在java语言里，不能0或非0的整数替代false或者true，这点和C语言不同

![image-20230221111003883](C:\Users\businessman\AppData\Roaming\Typora\typora-user-images\image-20230221111003883.png)





◆基本数据类型转换

#### 1.自动类型转换

介绍

当java程序在进行赋值或者运算时，精度小的类型自动转换为精度大的数据类型，这个就是**自动类型转换**。

![image-20230221111147194](C:\Users\businessman\AppData\Roaming\Typora\typora-user-images\image-20230221111147194.png)



2.自动类型转换注意和细节

一.有多种类型的数据混合运算时，系统首先自动将所有数据转换成容量最大的那种数据类型，然后再进行计算。

二. 当我们把精度（容量）大 的数据类型赋值给精度（容量）小的数据类型时，就会报错，反之就会进行自动类型转换。

三.（byte，short）和char之间不会相互自动转换。

![image-20230221113313068](C:\Users\businessman\AppData\Roaming\Typora\typora-user-images\image-20230221113313068.png)

四.byte，short，char他们三者可以计算，在计算时首先转换为int类型。

五.boolean不参与转换

六.自动提升原则：表达式结果的类型自动提升为 操作数中最大的类型



![image-20230221144729214](C:\Users\businessman\AppData\Roaming\Typora\typora-user-images\image-20230221144729214.png)



![image-20230221144317373](C:\Users\businessman\AppData\Roaming\Typora\typora-user-images\image-20230221144317373.png)

◆强制类型转换

✔介绍

自动类型转换的逆过程，将容量大的数据类型转换为容量小的数据类型。

使用时要加上强制转换符（），但可能造成精度降低或溢出，格外要注意。数据损失

案例ForceConvert.java

![image-20230221155408449](C:\Users\businessman\AppData\Roaming\Typora\typora-user-images\image-20230221155408449.png)

#### ◆基础数据类型和String类型的转换

**介绍**

在程序开发中，我们经常需要将基本数据类型转成String类型。或者将String类型转成基本数据类型。

●基本类型转String类型

语法：将基本类型的值+“ ”即可，案例演示：StringToBasic.java

![image-20230221161314454](C:\Users\businessman\AppData\Roaming\Typora\typora-user-images\image-20230221161314454.png)

●String类型转基本数据类型

语法：通过基本类型的包装类调用parseXX方法即可，案例演示：StringToBasic.java

![image-20230221164156987](C:\Users\businessman\AppData\Roaming\Typora\typora-user-images\image-20230221164156987.png)

●基本数据类型和String类型的转换

案例演示：StringToBasicDetail.java

1.在将String类型转成基本数据类型时，要确保String类型能够转成有效的数据，比如 在我们可以把“123”，转成一个整数，但是不能把“hello”转成一个整数

2.如果格式不正确，就会抛出异常，程序就会终止，这个问题在异常处理章节中，会处理