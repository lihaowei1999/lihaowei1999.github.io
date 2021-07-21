## C++上的Hololens开发记录

本部分在初始时候的目标为复现文献[(Christian,2020)](asset/paper/infrared marker tracking with hololens for neurosurgical interventions.pdf)，利用Hololens的摄像机获取IR追踪球的位置。从而计算出被标记物体的位姿，进行虚实匹配。由于目前暂时只找到了在C++上的开发者模式摄像头接口，因此采用C++进行这部分的任务。我们在Hololens2ForCV和HololensForCV的基础上进行开发。

### Hololens2ForCV

原文献采用了Hololens1，因此我原计划采用Hololens2进行开发，软件环境为vs2019

首先整理一下项目里的每个类的内容：

[BasicHologramMain](classes_BasicHologramMain.md)



### HololensForCV

其实这边本来有一个听起来更不错的选择，是HololensForCVUnity，但是经过一天的试探，发现该项目的代码按照提供的README文档的确能跑通，但是问题在于，在Unity中不知道函数在哪里，类长什么样，build到C++之后产生的类名变量名都是电脑自动生成的，没有任何可读性。因此在后续的编写上受到了巨大的限制。

#### 视频接口

选择Debug-x86-SensorStreamViewer，调试，产生画面如下

![20210719_222114_HoloLens](cpp_dev_record.assets/20210719_222114_HoloLens.jpg)

