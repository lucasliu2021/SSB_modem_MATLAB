# **通信系统仿真课程设计**



## 摘要

为了在无线传输中获得较高的辐射效率，天线尺寸必须要与发射信号波长想比拟，而基带信号中通常包含较低频率分量，若直接发射，天线过长难以实现。并且，通过调制把多个基带信号搬移到不同载频，实现信道多路复用，提高信道利用率，并能提高扩展信号带宽有利于提高系统抗干扰能力。

最常用的是模拟调制方式，SSB就是其中之一。它是将双边带信号的一个边带处理掉形成的，即节省传输功率，又节省传输带宽。本文从滤波法和相移法分别仿真。程序运行平台MATLAB2021b，window11。

关键词： 模拟调制系统 单边带调制 单边带解调 MATLAB Simulink

## **ABSTRACT**

In order to obtain high radiation efficiency in wireless transmission, the size of the antenna must be comparable to the wavelength of the transmitted signal, and the baseband signal usually contains lower frequency components. In addition, multiple baseband signals are moved to different carrier frequencies through modulation to realize channel multiplexing, improve channel utilization, and increase the extended signal bandwidth, which is beneficial to improve the system's anti-interference ability.

The most commonly used is the analog modulation method, and SSB is one of them. It is formed by processing one sideband of the double-sideband signal, which saves both transmission power and transmission bandwidth. In this paper, the filtering method and the phase shifting method are simulated respectively. The program runs on the platform matlab2021b, window11.

**Keywords: Analog modulation system, SSB modulation, SSB demodulation, MATLAB, Simulink**

# **目录**

[第1章 绪论 [1](#第1章-绪论)](#第1章-绪论)

> [1.1 引言 [1](#引言)](#引言)
>
> [1.2 课程设计目的 [1](#课程设计目的)](#课程设计目的)
>
> [1.3 课程设计要求 [1](#课程设计要求)](#课程设计要求)

[第2章 设计理论与步骤 [2](#第2章-设计理论与步骤)](#第2章-设计理论与步骤)

> [2.1基础理论分析 [2](#基础理论分析)](#基础理论分析)
>
> [2.1.1 幅度调制 [2](#幅度调制)](#幅度调制)
>
> [2.1.2 单边带调制 [2](#单边带调制)](#单边带调制)
>
> [2.2 设计理论 [2](#设计理论)](#设计理论)
>
> [2.2.1 滤波法 [2](#滤波法)](#滤波法)
>
> [2.2.2 相移法 [5](#相移法)](#相移法)
>
> [2.2.3 相干解调 [6](#相干解调)](#相干解调)
>
> [2.3 设计步骤 [7](#设计步骤)](#设计步骤)

[第3章 图形界面设计 [7](#第3章-图形界面设计)](#第3章-图形界面设计)

> [3.1 设计思路 [7](#设计思路)](#设计思路)
>
> [3.2 界面布局 [8](#界面布局)](#界面布局)

[第4章 MATLAB程序仿真分析 [12](#第4章-matlab程序仿真分析)](#第4章-matlab程序仿真分析)

> [4.1 滤波法程序调制 [12](#滤波法程序调制)](#滤波法程序调制)
>
> [4.1.1程序结构 [12](#程序结构)](#程序结构)
>
> [4.1.2 仿真结果 [13](#仿真结果)](#仿真结果)
>
> [4.2 相移法程序调制 [16](#相移法程序调制)](#相移法程序调制)
>
> [4.2.1程序结构 [16](#程序结构-1)](#程序结构-1)
>
> [4.2.2 仿真结果 [17](#仿真结果-1)](#仿真结果-1)
>
> [4.3 相干法程序解调 [19](#相干法程序解调)](#相干法程序解调)
>
> [4.3.1程序结构 [19](#程序结构-2)](#程序结构-2)
>
> [4.3.2 仿真结果 [21](#仿真结果-2)](#仿真结果-2)
>
> [4.5 仿真程序总结 [23](#仿真程序总结)](#仿真程序总结)

[第5章 Simulink系统模型仿真 [23](#第5章-simulink系统模型仿真)](#第5章-simulink系统模型仿真)

> [5.1 滤波法模型调制 [23](#滤波法模型调制)](#滤波法模型调制)
>
> [5.1.1模块结构 [23](#模块结构)](#模块结构)
>
> [5.1.2 仿真结果 [25](#仿真结果-3)](#仿真结果-3)
>
> [5.2 相移法模型调制 [27](#相移法模型调制)](#相移法模型调制)
>
> [5.2.1模块结构 [27](#模块结构-1)](#模块结构-1)
>
> [5.2.2 仿真结果 [29](#仿真结果-4)](#仿真结果-4)
>
> [5.3 相干法模型解调 [31](#相干法模型解调)](#相干法模型解调)
>
> [5.3.1模块结构 [31](#模块结构-2)](#模块结构-2)
>
> [5.3.2 仿真结果 [33](#仿真结果-5)](#仿真结果-5)
>
> [5.4 仿真模型总结 [34](#仿真模型总结)](#仿真模型总结)

[第6章 加入噪声的SSB调制解调 [35](#第6章-加入噪声的ssb调制解调)](#第6章-加入噪声的ssb调制解调)

> [6.1 程序实现SSB调制解调 [35](#程序实现ssb调制解调)](#程序实现ssb调制解调)
>
> [6.1.1 调制 [35](#调制)](#调制)
>
> [6.1.2 解调 [37](#解调)](#解调)
>
> [6.2 仿真实现SSB调制解调 [39](#仿真实现ssb调制解调)](#仿真实现ssb调制解调)

[第7章 课程设计心得 [1](#第7章-课程设计心得)](#第7章-课程设计心得)

[参考文献 [2](#参考文献)](#参考文献)

# 第1章 绪论

## 1.1 引言

产生SSB信号最直观的方法，就是先产生一个双边带信号，让其通过一个边带滤波器，滤掉不要的边带信号而形成的，他是最简单和常用的方法。解调采用相干解调，解调与调制实质一样，都是频谱搬移，调制是把基带信号的频谱搬到载频位置，可通过一个相乘器与载频相乘来实现。解调是调制反过程，把已经搬移的信号通过相乘器与载频相乘来实现。本文采用MATLAB和集成的Simulink 分别对调制解调过程进行设计研究。

## 1.2 课程设计目的

1\. 用滤波法、相移法产生单边带信号，以及相干解调进行单边带信号的解调。

2\. 正确构建程序以及模型，根据理论课学到的知识，正确设置各模块参数，直到正常运行，应用频谱仪观察信号频谱在调制解调前后的变化，观察在添加噪声后发生的变化。若仿真正确，未加入噪声时，解调后的信号功率谱密度应与原信号谱一样，叠加高斯白噪声后，解调的波形相对于原始信号会产生失真。

## 1.3 课程设计要求

> 1． 绘制出SSB信号调制解调前后在时域和频域中的波形，观察两者前后的变化，通过对结果的分析来加强对SSB信号调制解调原理的理解。
>
> 2\. 绘制出载波的时域频谱图，与SSB信号调制解调后时域频域的波形进行比较，根据SSB调制解调的原理进行判断正确与错误。

# 第2章 设计理论与步骤

## 2.1基础理论分析

### 2.1.1 幅度调制

单边带调制是幅度调制的一种。幅度调制是由调制信号去控制高频载波的幅度，使随调制信号作线性变化的过程。在波形上，幅度己调信号的幅度随基带信号的规律而呈正比变化，在频谱结构上，它的频谱完全是基带信号频谱在频域内的简单搬移。由于这种搬移是线性的，因此，幅度调制通常又称为线性调制。

### 2.1.2 单边带调制

先产生一个双边带信号，让其通过一个边带滤波器，滤掉不要的边带信号而形成的。他是最简单和常用的方法。根据滤除的方法不同，产生SSB信号方法有：滤波法和相移法。解调与调制实质一样，均是频谱搬移，分为相干解调和包络检波，对于SSB是抑制载波的已调信号，其包络不直接表示已调信号，因而不能直接用简单的包络检波方法解调。需要插入很强的载波，使之近成为AM信号才可使用包络检波方式解调。

## 2.2 设计理论

### 2.2.1 滤波法

产生 SSB 信号最直观的方法是，先产生一个双边带信号,然后让其通过一个边带滤波器,滤除不要的边带，即可得到单边带信号。

![](https://cdn.staticaly.com/gh/lucasliu2021/Image-hosting@main/Image/202209272214346.png)

图 2.2.1 SSB调制模型

我们把这种方法称为滤波法，它是最简单也是最常用的方法。其原理框图如图2.2.2 所示。H(w)为单边带滤波器的传输两数,若它具有如下理想高通特性

$$H(w) = H_{USB}\left. （w \right.） = \left\{ \begin{matrix}
1,\ \ \&|w| > w_{c} \\
0,\ \ \&|w| \leq w_{c} \\
\end{matrix} \right.\ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ (2.1)$$

则可滤除下边带，保留上边带(USB)，具有如下理想低通特性：

$$H(w) = H_{LSB}\left. （w \right.） = \left\{ \begin{matrix}
1,\ \ \&|w| > w_{c} \\
0,\ \ \&|w| \leq w_{c} \\
\end{matrix} \right.\ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ (2.2)$$

$$S_{SSB}(w) = S_{DSB}(w)*H(w)\ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ (2.3)$$

![](C:/Users/lucas/Desktop/media/image4.emf)

图 2.2.2 SSB调制频谱图

![](C:/Users/lucas/Desktop/media/image5.emf)

图 2.2.3 SSB调制边带图

滤波法的技术难点是边带滤波器制作，因为实际滤波器都不具有图2.2.3所描述的理想特性即在载频f。处不具有陡峭的截止特性，而是有一定的过渡带。例如，若经过滤波后的语音信号的最低频率为 300Hz,则上、下边带之间的频率

间隔为 600Hz，即允许过渡带为 600Hz。实现滤波器的难易程度与过渡带相对载频的归一化值有关，该值越小,边带滤波器就越难实现。因此在 600Hz 过渡带和不太高的载频情况下,滤波器不难实现;但当载频较高时，采用一级调制直接滤波的方法已不可能实现。

单边带调制。这时可以采用多级(一般采用两级)DSB 调制及边带滤波的方法，即先在较低的载频上进行 DSB 调制，目的是增大过渡带的归一化值，以利于滤波器的制作，经单边带滤波后再在要求的载频上进行第二次调制及滤波(常称为变频)。但当调制信号中含有直流及低频分量时滤波法就不适用了。

### 2.2.2 相移法

显然，滤波法是从信号的频谱特性出发，从双边带信号中去掉上或者下边带频率成分，从而产生单边信号。那么是否还有其它方法可以产生单边带信号呢？

  我们先来看下边带信号，下边带滤波器可以表示为

$$HLSSB = 21\left\lbrack sgn(f + fc) - sgn(f - fc) \right\rbrack\ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ (2 - 4)$$

$$SLSSB(f) = 2Ac\left\lbrack M(f - fc) + M(f + fc) \right\rbrack HLSSB(f)$$

$$= 4Ac\left\lbrack M(f - fc) + M(f + fc) \right\rbrack + 4Ac\left\lbrack M(f + fc) \cdot sgn(f + fc) - M(f - fc) \cdot sgn(f - fc) \right\rbrack.\ \ \ \ \ \ \ \ \ \ \ \ \ \ \ (2 - 5)$$

我们可以求得(4)的傅立叶反变换为

$$sLSSB(t) = 2Ac\left\lbrack m(t)cos2\pi fct + m^{(t)sin2\pi fct} \right\rbrack.\ \ \ \ \ \ \ \ \ \ \ \ \ (2 - 6)$$

同理，我们可以推得上边带信号时域表达式为

$$sUSSB(t) = 2Ac\left\lbrack m(t)cos2\pi fct - m^{(t)sin2\pi fct} \right\rbrack.\ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ (2 - 7)$$

下边带信号的傅立叶变换如图4所示。从图中不难看出，

$$m(t)sin2\pi fct\ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ （2 - 8）$$

是将上边带频率部分反相，与双边带信号叠加后，上边带部分被正负抵消，因而被消除掉，只保留下边带部分。

![](https://cdn.staticaly.com/gh/lucasliu2021/Image-hosting@main/Image/202209272214347.png)

图 2.2.4 SSB调制下边带滤波器

根据(2-6)和(2-7)，我们可以画出相移法模型如图所示。

![在这里插入图片描述](https://cdn.staticaly.com/gh/lucasliu2021/Image-hosting@main/Image/202209272214348.png)

图 2.2.5 SSB相移法模型

### 2.2.3 相干解调

解调采用相干解调，也叫同步检波。解调与调制的实质一样，均是频谱搬移。调制是把基带信号的频谱搬移到载频的位置，这一过程可以通过一个相乘器与载波相乘来实现。解调是调制的反过程，即把在载波位置的已调信号的频谱搬回到原始基带位置，因此同样可以使用相乘器与载波相乘来实现。

$$Sp(t) = Sm(t)coswctSp(t) = Sm(t)coswct\ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ （2 - 9）$$

其中，coswct为相干载波，Sm(t)为SSB信号

![](https://cdn.staticaly.com/gh/lucasliu2021/Image-hosting@main/Image/202209272214349.png)

图 2.2.6 SSB相干解调模型

## 2.3 设计步骤

2.3.1 分析课题，查找有关 SSB 调整解调的相关资料，弄清楚原理，掌握滤波法，相干解调。

2.3.2 熟悉 MATLAB 集成环境下的 Simulink 仿真平合，掌握自己需要用到的仿真模块和器件，例如高斯白噪声，频谱仪等。

2.3.3 先设计调制部分，将基带信号与调整信号相乘形成双边带信号，然后通过滤波器形成单边带信号。

2.3.4 再设计解调部分，用相干解调法，将调整信号与相干载波相乘，并通过低通滤波器，得到解调信号。并用示波器和频谱仪观察分析，得出结论，验证是否份真成功。

# 第3章 图形界面设计

## 3.1 设计思路

由于需要多个不同调制解调方式和不同的参数，每一次需要打开相应的源文件去运行，繁琐且容易出错，所以开发一套GUI程序去方便使用。

Matlab有两种GUI的设计方法，其一是基于Java Swing的GUIDE，甲骨文已经不再对其投入开发。本次使用的是最最新性能更强的app design，因为采用面向对象语言，代码开发更加条理清晰。

通过建立私用函数，将程序仿真的代码写入里面，供app的调用。

![](https://cdn.staticaly.com/gh/lucasliu2021/Image-hosting@main/Image/202209272214350.png)

图 3.1 GUI 私用函数

## 3.2 界面布局

程序需要一些基本的按钮以及选择框，基本的图标区，所以采用自动调整分栏布局，由于多个图表 所以采用选项卡组，使页面更加简洁（如图3.2和图3.3）。

![](https://cdn.staticaly.com/gh/lucasliu2021/Image-hosting@main/Image/202209272214351.png)

图 3.2 GUI 主页面1

![](https://cdn.staticaly.com/gh/lucasliu2021/Image-hosting@main/Image/202209272214352.png)

图 3.3 GUI 主页面2

可以看到，在页面左面有控制面板，可选择调制参数，以及添加的 噪声等级。在界面的右面可以看到使用了一组选项卡，分别显示时域和频域图表和程序的一些信息。由于界面是动态调整的可以看到，在拉伸页面时也会发生相应的变化。

![](https://cdn.staticaly.com/gh/lucasliu2021/Image-hosting@main/Image/202209272214353.png)

图 3.4 GUI 拉伸页面1

![](https://cdn.staticaly.com/gh/lucasliu2021/Image-hosting@main/Image/202209272214354.png)

图 3.5 GUI 拉伸页面2

1.  在UI的处理上使用了最近流行的圆角小巧美观。

2.  程序运行图片展示（部分）

![](https://cdn.staticaly.com/gh/lucasliu2021/Image-hosting@main/Image/202209272214355.png)

图 3.6 GUI 展示界面

> 可以看到实验产生的波形显示在主界面的坐标区，十分美观和简洁。

# 第4章 MATLAB程序仿真分析

## 4.1 滤波法程序调制

### 4.1.1程序结构

function results = pgmod_filter(app)

%DSB design

Fs=1024;%采样频率

t=0:1/Fs:2;%信号长度

Am=2;%基带信号幅值

Ac=2;%载波信号幅值

fm=2;%基带信号频率

fc=20;%载波信号频率

wm=2\*pi\*fm;%基带信号模拟角频率

wc=2\*pi\*fc;%载波信号模拟角频率

Sm=Am\*sin(wm\*t);%基带信号

Sc=Ac\*sin(wc\*t);%载波信号

SDSB=Sm.\*Sc;%DSB已调信号

spec_SDSB=fft(SDSB,2\*Fs);%对DSB信号做2048点FFT，做频谱分析

mag_SDSB=abs(spec_SDSB);%计算DSB频响幅值

fdsb=(0:2\*Fs-1)./2;%真实频率

if app.Switch.Value=="On"

SDSB = awgn(SDSB,-app.Slider.Value);

End

%filter design

% N=7;%椭圆滤波器的阶数

N=uint8(app.Slider_2.Value);

\[BL,AL\]=ellip(N,0.1,80,(fc-fm)/(Fs/2),'low');%设计椭圆低通滤波器

%其中通带最大衰减为0.1，阻带最小衰减为80，通带边界频率为20-2=18Hz

%SSB design

LSSB=filter(BL,AL,SDSB);%DSB经过Ellips LPF后取得下边带

spec_LSSB=fft(LSSB,2\*Fs);%对LSSB信号做2048点FFT

mag_LSSB=abs(spec_LSSB);%计算LSSB频响幅值

fssb=(0:2\*Fs-1)./2;

%figure(1);

%plot(Sm);grid on;%显示基带信号

%title('Base Sign');

%set(gca,'xlim',\[0,1000\]);

%figure(2);

%plot(Sc);grid on;%显示载波信号

%title('Carry Sign');

%set(gca,'xlim',\[0,1000\]);

%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%

plot(app.UIAxes,SDSB,"b");

title(app.UIAxes,'DSB Wave');

set(app.UIAxes,'xlim',\[0,1000\]);

plot(app.UIAxes_2,LSSB,"b");

title(app.UIAxes_2,'LSSB Wave');

set(app.UIAxes_2,'xlim',\[0,1000\]);

%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%

plot(app.UIAxes_3,fdsb,mag_SDSB,"b");

title(app.UIAxes_3,'DSB Spectrum')

set(app.UIAxes_3,'xlim',\[10,30\]);

plot(app.UIAxes_4,fssb,mag_LSSB,"b");

title(app.UIAxes_4,'LSSB Spectrum')

set(app.UIAxes_4,'xlim',\[10,30\]);

%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%

End

### 4.1.2 仿真结果

·基带信号： 频率为2Hz，幅值为2，其时域表达式为2sin(4π)。

·载波信号： 频率为20Hz，幅值为2，其时域表达式为2sin(40π)。

![](C:/Users/lucas/Desktop/media/image15.emf)

图 4.1 DSB波形

上图可以看到DSB波形，过零点处有相位翻转180°的现象，幅值为4。

![](C:/Users/lucas/Desktop/media/image16.emf)

图 4.2 下边带波形

可以看到通过椭圆滤波器后的下边带SSB波形图。

![](C:/Users/lucas/Desktop/media/image17.emf)

图 4.3 DSB频谱

可以看到有两个边带，其中下边带频率为18Hz，幅值为2；上边带频率为22Hz，幅值为2，因为做2048点FFT，所以这里的幅值是2048

![](C:/Users/lucas/Desktop/media/image18.emf)

图 4.4 SSB 下边带信号频谱

下边带信号频谱： 主要频率成分集中在18Hz处，上边带基本被滤除。

## 4.2 相移法程序调制

### 4.2.1程序结构

function results = pgmod_phase(app)

ts=0.0025; %信号抽样时间间隔

t=0:ts:10-ts; %时间向量

fs=1/ts; %抽样频率

rng(123); %随机数种子为123

msg=randi(\[-3,3\],100,1); %生成消息序列,随机数种子为123

msg1=msg\*ones(1,fs/10); %扩展成取样信号形式

msg2=reshape(msg1.',1,length(t));

Pm=fft(msg2)/fs; %求消息信号的频谱

fc=100; %载波频率

s1=0.5\*msg2.\*cos(2\*pi\*fc\*t); %USSB信号的同相分量

hmsg=imag(hilbert(msg2)); %消息信号的Hilbert变换

s2=0.5\*hmsg.\*sin(2\*pi\*fc\*t); %USSB信号的正交分量

Sussb=s1-s2; %完整的USSB信号

Pussb=fft(Sussb)/fs; %USSB信号频谱

%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%

plot(app.UIAxes,msg1,"b")

title(app.UIAxes,'消息信号时域');

set(app.UIAxes,'xlim',\[0,100\]);

plot(app.UIAxes_3,fftshift(abs(Pm)),"b") %画出消息信号频谱

title(app.UIAxes_3,'消息信号频谱');

%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%

plot(app.UIAxes_2,Sussb,"b")

title(app.UIAxes_2,'LSSB信号时域')

plot(app.UIAxes_4,fftshift(abs(Pussb)),"b") %画出已调信号频谱

title(app.UIAxes_4,'LSSB信号频谱')

%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%

End

### 4.2.2 仿真结果

![](C:/Users/lucas/Desktop/media/image19.emf)

图 4.5 SSB信号波形2

![](C:/Users/lucas/Desktop/media/image20.emf)

图 4.6 下边带波形2

可以使用随机信号进行单边带压制后的效果图比较明显。

![](C:/Users/lucas/Desktop/media/image21.emf)

图 4.7 SSB 信号频谱2

![](C:/Users/lucas/Desktop/media/image22.emf)

图 4.8 SSB下边带频谱

相对于正弦信号的单个频率，LSSB的信号频谱容易观察单边带频谱。

## 4.3 相干法程序解调

### 4.3.1程序结构

function results = pgenmod_coherent(app)

%DSB design

Fs=1024;%采样频率

t=0:1/Fs:2;%信号长度

Am=2;%基带信号幅值

Ac=2;%载波信号幅值

fm=2;%基带信号频率

fc=20;%载波信号频率

wm=2\*pi\*fm;%基带信号模拟角频率

wc=2\*pi\*fc;%载波信号模拟角频率

Sm=Am\*sin(wm\*t);%基带信号

Sc=Ac\*sin(wc\*t);%载波信号

SDSB=Sm.\*Sc;%DSB已调信号

if app.Switch.Value=="On"

SDSB = awgn(SDSB,-app.Slider.Value);

end

%filter design

N=uint8(app.Slider_2.Value);

\[BL,AL\]=ellip(N,0.1,80,(fc-fm)/(Fs/2),'low');%设计椭圆低通滤波器

%其中通带最大衰减为0.1，阻带最小衰减为80，通带边界频率为20-2=18Hz

%SSB design

LSSB=filter(BL,AL,SDSB);%DSB经过Ellips LPF后取得下边带

%Demodulation SSB

coherent_carrier=Sc;%相干载波与输入载波一致

mul_LSSB_cc=coherent_carrier.\*LSSB;%相干载波与下边带相乘

spec_LSSB_cc=fft(mul_LSSB_cc,2\*Fs);%对相干载波与下边带相乘后的信号做FFT

mag_LSSB_cc=abs(spec_LSSB_cc);%求频响幅度

fdssb=(0:2\*Fs-1)./2;%真实频率

%pass the LPF

LPF_LSSB=filter(BL,AL,mul_LSSB_cc);

%把相干载波与下边带相乘后的信号通过LPF

spec_LPF_LSSB=fft(LPF_LSSB,2\*Fs);

%对相干载波与下边带相乘后信号经过LPF后的信号做FFT

mag_LPF_LSSB=abs(spec_LPF_LSSB);%求频响幅度

%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%

plot(app.UIAxes,mul_LSSB_cc,"b")

title(app.UIAxes,'相干载波相乘');

set(app.UIAxes,'xlim',\[500,2000\]);

plot(app.UIAxes_2,LPF_LSSB,"b")

title(app.UIAxes_2,'通过滤波器');

set(app.UIAxes_2,'xlim',\[500,2000\]);

%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%

plot(app.UIAxes_3,fdssb,mag_LSSB_cc,"b")

title(app.UIAxes_3,'相干载波相乘')

set(app.UIAxes_3,'xlim',\[0,50\]);

plot(app.UIAxes_4,fdssb,mag_LPF_LSSB,"b")

title(app.UIAxes_4,'通过滤波器');

set(app.UIAxes_4,'xlim',\[0,50\]);

%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%

End

### 4.3.2 仿真结果

![](C:/Users/lucas/Desktop/media/image23.emf)

图 4.9 相干载波相乘时域图

![](C:/Users/lucas/Desktop/media/image24.emf)

图 4.10 相干载波相乘频谱图

相干载波与LSB信号相乘后的波形频谱在20-18=2Hz处有一个信号，在18+20=38Hz处也有一个信号，符合DSB调制的规律。

![](C:/Users/lucas/Desktop/media/image25.emf)

图 4.11 解调出的波形时域图

![](C:/Users/lucas/Desktop/media/image26.emf)

图 4.12 解调出的波形频谱图

相干载波与LSB和USB信号相乘后经过LPF的信号与基带信号基本一致的，说明用下边带可以解调出基带信号。

## 4.5 仿真程序总结

通过把两个信号直接相乘来产生DSB信号，这种调制会把基带信号的频谱搬移到载波信号的频谱附近，形成对称的上下边带，所以从信息传输的角度考虑，仅需要任一边带就够了，所以通过适当的低通滤波器取得下边带，适当的高通滤波器取得上边带。这里原本的滤波器采用Butterworth滤波器的设计方式，但由于过渡带不够窄，即不够陡峭，总是会残留一部分边带，再经过查阅资料后选择了过渡带比较窄的椭圆滤波器，这样就基本滤除了另一个边带。

# 第5章 Simulink系统模型仿真

## 5.1 滤波法模型调制

### 5.1.1模块结构

![](https://cdn.staticaly.com/gh/lucasliu2021/Image-hosting@main/Image/202209272214356.png)

图 5.1 滤波法仿真模型图

![](https://cdn.staticaly.com/gh/lucasliu2021/Image-hosting@main/Image/202209272214357.png)

图 5.2 基带和载波信号配置

输入： 一个2Hz的正弦基带信号和一个20Hz的正弦载波信号，其中基带信号为2sin(4π),载波信号为2sin(40π)。

![](https://cdn.staticaly.com/gh/lucasliu2021/Image-hosting@main/Image/202209272214358.png)

图 5.3 低通滤波器配置

其中低通滤波器的通带边界频率为20-2=18Hz。

### 5.1.2 仿真结果

![](https://cdn.staticaly.com/gh/lucasliu2021/Image-hosting@main/Image/202209272214360.png)

图 5.4 滤波仿真调制结果时域图

第一个波形为：消息信号（2Hz）第二个波形为：载波信号 (20Hz)。

第三个波形为：DSB已调信号 第四个波形为：SSB下边带信号。

![](https://cdn.staticaly.com/gh/lucasliu2021/Image-hosting@main/Image/202209272214361.png)

图 5.5 滤波仿真调制DSB频谱图

可以看到有两个边带，其中下边带主要频率成分为18Hz，幅值为2；上边带主要频率成分为22Hz，幅值为2。

![](https://cdn.staticaly.com/gh/lucasliu2021/Image-hosting@main/Image/202209272214362.png)

图 5.6 滤波仿真调制SSB下边带频谱图

可以看到上边带基本没有了，主要频率成分为18Hz，幅值为2的下边带信号频谱。

## 5.2 相移法模型调制 

### 5.2.1模块结构

![](https://cdn.staticaly.com/gh/lucasliu2021/Image-hosting@main/Image/202209272214363.png)

图 5.7 相移仿真模型图

![](https://cdn.staticaly.com/gh/lucasliu2021/Image-hosting@main/Image/202209272214364.png)

图 5.8 基带信号配置

基带信号频率和幅度相同，相位相反。

![](https://cdn.staticaly.com/gh/lucasliu2021/Image-hosting@main/Image/202209272214365.png)

图 5.9载波信号配置

载频信号频率和幅度相同，相位相反。

### 5.2.2 仿真结果

![](https://cdn.staticaly.com/gh/lucasliu2021/Image-hosting@main/Image/202209272214366.png)

图 5.10 相移仿真调制结果时域图

第一个波形为：消息信号（2Hz）第二个第三个波形为：DSB已调信号

第四个波形为：SSB下边带信号。

![](https://cdn.staticaly.com/gh/lucasliu2021/Image-hosting@main/Image/202209272214367.png)

图 5.11 载频频域图

因两个载频只是相位不同，只显示一个。

![](https://cdn.staticaly.com/gh/lucasliu2021/Image-hosting@main/Image/202209272214368.png)

图 5.12 相移仿真调制双边带频域图

![](https://cdn.staticaly.com/gh/lucasliu2021/Image-hosting@main/Image/202209272214369.png)

图 5.13 相移仿真调制单边带频域图

可以看到，在使用相移法时，SSB的调制效果明显好于滤波法。

## 5.3 相干法模型解调

### 5.3.1模块结构

![](https://cdn.staticaly.com/gh/lucasliu2021/Image-hosting@main/Image/202209272214370.png)

图 5.14 相干法仿真解调模型

![](https://cdn.staticaly.com/gh/lucasliu2021/Image-hosting@main/Image/202209272214371.png)

图 5.15 基带信号

输入： 一个2Hz的正弦基带信号和一个20Hz的正弦载波信号，其中基带信号为2sin(4π),载波信号为2sin(40π)。

![](https://cdn.staticaly.com/gh/lucasliu2021/Image-hosting@main/Image/202209272214372.png)

图 5.16 调制滤波器

低通滤波器的通带边界频率为20-2=18Hz。

![](https://cdn.staticaly.com/gh/lucasliu2021/Image-hosting@main/Image/202209272214373.png)

图 5.17 解调滤波器

低通滤波器采用椭圆滤波器，具有较好的性能，因为基带是2hz，故滤波器截止频率也为2hz。相干载波： 2sin(40π)与输入时的载波信号同频同相。

### 5.3.2 仿真结果

![](https://cdn.staticaly.com/gh/lucasliu2021/Image-hosting@main/Image/202209272214374.png)

图 5.18 信号波形

从上向下分别是，已调波形、相干载波与LSB信号相乘后的波形、相干载波与LSSB信号相乘后经过低通后的波形、解调后波形。

![](https://cdn.staticaly.com/gh/lucasliu2021/Image-hosting@main/Image/202209272214375.png)

图 5.19 SSB信号

SSB信号调制的效果并不是特别好，上边带没有完全过滤。

![](https://cdn.staticaly.com/gh/lucasliu2021/Image-hosting@main/Image/202209272214376.png)

图 5.20 解调后信号

可以看到相干载波与LSB/USB信号相乘后经过低通后的波形频谱都是一样的，为频率2Hz,幅值为2的正弦信号。

## 5.4 仿真模型总结

通过从DSB信号经过单边带滤波器取得任一边带形成的SSB信号，与相干载波相乘后，形成的信号基本一样，再通过适当的LPF后就可得到基带信号。其中，相干载波要与DSB调制时的载波同频同相，从步骤上来看与DSB调制本质上一样。最后的结果说明用上边带或下边带都可以解调出基带信号。

# 第6章 加入噪声的SSB调制解调

## 6.1 程序实现SSB调制解调

### 6.1.1 调制

![](https://cdn.staticaly.com/gh/lucasliu2021/Image-hosting@main/Image/202209272214377.png)

图 6.1 噪声调制波形时域图

可以看到调制信号有轻微的畸变。

![](https://cdn.staticaly.com/gh/lucasliu2021/Image-hosting@main/Image/202209272214378.png)

图 6.2 噪声调制SSB 频谱图

在滤波器阶数小的时候，发现上边带滤除效果很差。

![](https://cdn.staticaly.com/gh/lucasliu2021/Image-hosting@main/Image/202209272214379.png)

图 6.3 噪声调制SSB 频谱图高阶

提高滤波器阶数后，效果显著。

### 6.1.2 解调

![](https://cdn.staticaly.com/gh/lucasliu2021/Image-hosting@main/Image/202209272214380.png)

图 6.4 噪声解调SSB图

![](https://cdn.staticaly.com/gh/lucasliu2021/Image-hosting@main/Image/202209272214381.png)

图 6.5 噪声解调SSB 频谱图

在解调是加入噪声，会导致解调出的信号产生畸变。

![](https://cdn.staticaly.com/gh/lucasliu2021/Image-hosting@main/Image/202209272214382.png)

图 6.6 噪声解调SSB 图高阶

![](https://cdn.staticaly.com/gh/lucasliu2021/Image-hosting@main/Image/202209272214386.png)

图 6.7 噪声解调SSB 频谱图高阶

可以看到在噪声很低的情况下，调制信号会产生畸变，当把滤波阶数调高后会有些改善。可以看到，经过LPF后的信号频谱的主要分量就集中在2Hz处，也就是说可以解调出基带信号。

## 6.2 仿真实现SSB调制解调

![](https://cdn.staticaly.com/gh/lucasliu2021/Image-hosting@main/Image/202209272214738.png)

图 6.8 噪声解调SSB 仿真模型图

输入： 一个2Hz的正弦基带信号和一个20Hz的正弦载波信号，其中基带信号为2sin(4π),载波信号为2sin(40π)。

边带滤波器： 采用的是椭圆模拟滤波器，过渡带比较窄。其中低通滤波器的通带边界频率为20-2=18Hz。

相干载波： 2sin(40π)与输入时的载波信号同频同相。

![](https://cdn.staticaly.com/gh/lucasliu2021/Image-hosting@main/Image/202209272214387.png)

图 6.9 调制滤波器

![](https://cdn.staticaly.com/gh/lucasliu2021/Image-hosting@main/Image/202209272214388.png)

图 6.10 噪声

加性噪声： 直接加噪声功率为1的带限白噪声。

![](https://cdn.staticaly.com/gh/lucasliu2021/Image-hosting@main/Image/202209272214389.png)

图 6.11 解调滤波器

低通滤波器 ： 通带边界频率为2Hz的椭圆模拟低通滤波器，整体上和上面的SSB调制所用的信号和滤波器一样。

![](https://cdn.staticaly.com/gh/lucasliu2021/Image-hosting@main/Image/202209272214390.png)

图 6.12 噪声

产生的噪声。

带限白噪声频谱

![](https://cdn.staticaly.com/gh/lucasliu2021/Image-hosting@main/Image/202209272214391.png)

图 6.13 下边带LSB加上带限白噪声后与相干载波相乘的波形

可以看到下边带LSB加上带限白噪声后与相干载波相乘的波形频谱都有幅度较大频谱分量和上面无噪声时的情况一样。

![](https://cdn.staticaly.com/gh/lucasliu2021/Image-hosting@main/Image/202209272214392.png)

图 6.14 波形图

（图 6.14 波形图）依次向下分别是，加噪、载频、相乘、解调波形图相干解调后的信号经过LPF后的信号波形，可以看到整体上与原基带信号相比，幅度上会有一些畸变，频率基本一样。

![](https://cdn.staticaly.com/gh/lucasliu2021/Image-hosting@main/Image/202209272214393.png)

图 6.15 相干解调后的信号经过LPF后的信号频谱

可以看到，经过LPF后的信号频谱的主要分量集中，也就是说可以解调出基带信号。

# 第7章 课程设计心得

本次实验学习了实现SSB信号的调制与解调，在仿真过程中遇到许多的问题，不过通过查阅资料，最终得到了解决，现总结如下。

在用Simulink仿真调制与解调过程时，需要分为两个模块，一个为调制模块，另一个为解调模块。在仿真过程中会遇到的问题，需要信号采样时间间隔保持一致，在那个频谱分析仪前还要加个零阶保持器（实现采样点之间插值的元件。零阶保持器基于时域外推原理，能够把采样信号转换成连续信号。保持器的作用是将离散信号转换为连续信号，这个连续信号近似的重现了作用在采样器上的信号。最简单的保持器是将采样信号转变为在两个连续采样瞬时之间保持常量的信号），采样间隔需要和前面信号的一致。在做matlab代码的仿真的滤波器设计时，最先使用的巴特沃斯滤波器，由于过渡带比较宽，在进行边带滤波时，总会残留一些边带，所以最后选择了边带窄的椭圆滤波器，实现了比较好的边带滤波效果。

在用Simulink做SSB带加性噪声的仿真调制过程中，因为在实际中，已调信号在传输过程中总会受到噪声干扰，所以只仿真了解调过程。按照书本上的原理，加性噪声为高斯白噪声，然后经过BPF后进行相干解调，然后进行相干解调，解调出来的信号，与基带信号相比，会有不少的畸变，当然因为实际情况更为复杂，所以我的仿真模块一些参数的设计并不能满足实际，所以这是我需要提升的。

#  

# 参考文献

\[1\] 刘浩.MATLAB R2018a 完全自学一本通.电子工业出版社,2019(01)：35.

\[2\] 樊昌信. 通信原理.国防工业出版社,2021(1)：30.

\[3\] 王靖, 李永全. 数字椭圆滤波器的Matlab设计与实现\[J\]. 现代电子技术, 2007, 30(6):3.

\[4\] 史燕, 杨小雪. 基于Matlab和Multisim的综合性实验——椭圆滤波器设计与仿真\[C\]// 全国高等学校电子技术研究会2008年年会. 0.
