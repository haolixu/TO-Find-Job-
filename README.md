# Java工程师笔试✊✌
### 内存有哪几种存储组织结构?
>* 1:可执行代码
>* 2:静态数据
>* 3:动态数据（堆）
>* 4:栈
### 内存越界和内存泄漏？
> 内存越界又叫内存溢出，指程序在申请内存时，没有足够的内存空间供其使用。
内存泄漏是指程序在申请内存后，无法释放已申请的内存空间，占用有用内存。
### 如何在linux多个进程间 进行通讯？给出三种？
> 管道，共享内存，信号量（又叫信号灯），套接口 （socket）。
### 运输层的两个主要协议是？ 
> CP和UDP。用户数据报协议UDP在传送数据之前不需要建立连接,UDP不提供可靠交付,UDP首部只有8个字节。
传输控制协议TCP在传送数据之前必须先建立连接,数据传送结束要释放链接,TCP提供可靠的，提供面向连接的服务,TCP首部的最小长度是20个字节。
### 结构化程序设计的三种基本逻辑结构？
> 顺序结构、选择结构和循环结构。采用结构化程序设计方法，程序结构清晰，易于阅读、测试、排错和修改。由于每个
模块执行单一功能，模块间联系较少，使程序编制比过去更简单，程序更可靠，而且增加了可维护性，每个模块可以独立编制、测试。
### 什么是死锁？如何避免死锁？
> 死锁是指多个进程在运行过程中因争夺资源而造成的一种僵局，当过程处于这种僵持状态时，若无外力作用，他们
将无法向前推进。在资源动态分配过程中，防止系统进入不安全状态，以避免发生死锁。
### 轮询任务调度和可抢占式调度有什么区别？
>* 轮询任务调度无需记录当前所有连接的状态，所以它是一种无状态调度，但不利于后面的请求及时得到响应。
>* 抢占式调度允许高优先级的任务打断当前执行的任务，抢占CPU的控制权。这有利于后面的高优先级的任务也能及时得到响
应。但实现相对较复杂且可能出现低优先级的任务长期得不到调度。
### 简单描述面向对象的三个特征？
>* 封装：将客观事物抽象成类，每个类对自身的数据和方法实行protection(private,protected,public) 。
>* 继承：它可以使用现有类的所有功能，并在无需重新编写原来的类的情况下对这些功能进行扩展。
>* 多态：是将父对象设置成为和一个或更多的他的子对象相等的技术，赋值之后，父对象就可以根据当前赋值给它的子对象的特性以不同的方式运作。
### 交换和路由的区别是什么？VLAN有什么特点？
>* 交换是不需要 IP 地址的，而路由需要。
>* VLAN 是虚拟局域网的英文缩写，它的特点有三：控制广播，安全，灵活性和可扩张性。
### C语言中的static的作用是什么？
> static在c里面可以用来修饰变量，也可以用来修饰函数。
### C++中引用与指针有什么区别？
> 引用是变量的别名，引用不占用内存空间，而指针占用内存空间。
### C语言编程：实现把一个字符倒序的功能，如abcd倒成dcba。
```c
#include <stdio.h>
#include <stdlib.h>
#include <string.h>
int main(void)
{
    char    str[120];
    int     i, j;
    char    tmp;
    while (scanf("%s", str) == 1) {    // 连续输入字符串给str变量,遇到EOF结束
        i = strlen(str);
        i--;   // 求结束符'\0'前一个位置
        for (j = 0; j < i; j++, i--) {     //字符串反转
            tmp = str[i];
            str[i] = str[j];
            str[j] = tmp;
        }
        printf("%s\n", str);
    }
 return 0;}
 ```
 ### 请用C语言编写算法求ax2+bx+c=0方程的根。a,b,c由键盘输入，设b2-4ac>0(采用if语句）。
 ```c
 #include <stdio.h>
#include <math.h>
 int main()
{
        float a,b,c,d,x1,x2;
        printf("输入方程的三个系数:");
        scanf("%f %f %f",&a,&b,&c);
        if(a!=0)
        {
                d=sqrt(b*b-4*a*c);
                x1=(-b+d)/(2*a);
                x2=(-b-d)/(2*a);
                if(x1<x2) 
                    printf("%0.2f %0.2f\n",x2,x1); 
                else
                    printf("%0.2f %0.2f\n",x1,x2);
        }
        return 0;}
		
以下程序的运行结果为？
#include<stdio.h>
int main();
{
        int sum,pad;
		sum=pad=5;
		pad=sum++;
		pad++;
		++pad;
		printf("%d\n", pad);
}
```
### js的数据类型？
> 字符串、数字、布尔、数组、对象、Null、Undefined.
### js的事件流模型都有什么？
> 单击事件:onclick，改变事件:onchange，选中事件:onselect，获得焦点事件:onfocus，失去焦点事件:on
blur，载入文件事件:onload，鼠标镇盖事件:onmouseover等。
### 什么是ajax和json？
>* Ajax用来描述一组技术，它使浏览器可以为用户提供更为自然的浏览体验，它是“Asynchronous JavaScript + XML的简写”。
>* JSON来自于javascript，是一种比较流行的标准格式，是数据的载体，更加易读、更便于肉眼检查。
### 想实现一个对页面某个支点的拖曳？如何做？
> 给需要拖拽的节点绑定mousedown, mousemove, mouseup事件。mousedown事件触发后，开始拖拽。mousemove时，需要通过event.clientX和clientY获取
拖拽位置，并实时更新位置。mouseup时，拖拽结束。需要注意浏览器边界的情况。
### 页面布局常用的HTML5语义元素有哪些？
>* header 
>* footer 
>* section
>* article
>* aside
### call 和apply的区别是什么?
>* call：它可以接受多个参数，第一个参数与apply一样，后面则是一串参数列表。
>* apply：最多只能有两个参数――新this对象和一个数组argArray。
### 请说明一下static，relative，absolute和fixed元素的特点？
>* static(静态) 不能通过z-index进行层次分级。 
>* relative(相对定位) 参考自身静态位置通过top,bottom,left,right 定位，并且可以通过z-index进行层次分级。
>* fixed（固定定位）所固定的参照对像是可视窗口而并非是body或是父级元素，其总是固定在浏览器窗口的某个位置，并且不受滚动的影响，是绝对的坐标定位。
### 请解释一下inline和inline-block的区别？
>* inline元素设置width,height属性无效。
>* inline-block展现inline元素的属性，但是可以设置自己的宽和高了。
### 日志文件用于保存？ 
> 日志文件是 对数据库的更新操作.
### String,StringBuffer,StringBuilder的区别?
>* 操作少量的数据使用 String；
>* 单线程操作大量数据使用 StringBuilder；
>* 多线程操作大量数据使用 StringBuffer。
### 在浏览器地址栏键入URL,按下回车之后会经历以下流程:
>* 浏览器向DNS服务器谞求解析该URL中的域名所对应的IP地址；
>* 解析出IP地址后，根据该IP地址和默口 80,和服务器建立TCP连接；
>* 浏览器发出读取文件(URL中域名后面部分对应的文件)的HTP请求,该请求报文作为TCP三次握手的第三个报文的数据发送给服务器
>* 服务器对浏览器请求作出响应,并把对应的htm文本发送给浏览器
>* 释放TCP 连接
>* 浏览器将该html文本并显示内容
### IP地址中的ABCD类网:
>* A类地址范围：1. 0. 0.1—126.155. 255. 254
>* B类地址范围：128. 0. 0.1—191. 255. 255. 254
>* C类地址范围：192. 0. 0.1—223. 255. 255. 254
>* D类地址范围：224. 0. 0.1—239. 255. 255. 254
>* E类地址范围：240. 0. 0.1—255. 255. 255. 254
### OSI七层机构:
![OSI七层机构](https://gitee.com/uploads/images/2018/0329/131735_d8942627_1846199.png "OSI七层机构")


| 具体七层 | 数据格式  |  功能和连接方式  | 典型设备 |
| --------   | -----:  | :----:  | :----:  |
| 应用层    | data |   网络服务和使用者应用程序间的一个接口    |  终端设备(pc和手机) |
| 表示层    | data |   数据表示,数据安全,数据压缩    |  终端设备(pc和手机) |
| 会话层    | data |   数据传输,会话连接管理与流量控制,差错控制    |  终端设备(pc和手机) |
