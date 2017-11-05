这是我大三的时候做的一个嵌入式小设计——动态艺术时钟。

# 介绍
先看一下效果吧，从视频上看刷新的感觉很明显，实际中看起来会好一些，不过大致的意思到了就行了，毕竟也没做什么优化。

![](http://chuquan-public-r-001.oss-cn-shanghai.aliyuncs.com/github-images/dynamic-art-clock001.gif)

这个时钟的特殊之处在于，其数字的切换具有一个动态的演化过程。下面两张图分别示意了从3到4的演变、从8到9的演变过程。

![](http://chuquan-public-r-001.oss-cn-shanghai.aliyuncs.com/github-images/dynamic-art-clock006.png?x-oss-process=image/resize,w_500)

![](http://chuquan-public-r-001.oss-cn-shanghai.aliyuncs.com/github-images/dynamic-art-clock007.png?x-oss-process=image/resize,w_500)

# 仿真
最开始做的时候，我先使用proteus仿真软件搭建电路进行仿真，运行程序即可达到我想要的效果。详细仿真设计请参见```simulation```目录下的文件。

# 实物
然而仿真毕竟还是仿真，当时的我还是太naive了。仿真成功了便参考仿真的电路画了PCB电路板，来做样板。如下图所示，分别显示屏和控制电路的PCB的正反面。

![](http://chuquan-public-r-001.oss-cn-shanghai.aliyuncs.com/github-images/dynamic-art-clock002.jpg?x-oss-process=image/resize,w_500)

![](http://chuquan-public-r-001.oss-cn-shanghai.aliyuncs.com/github-images/dynamic-art-clock003.jpg?x-oss-process=image/resize,w_500)

![](http://chuquan-public-r-001.oss-cn-shanghai.aliyuncs.com/github-images/dynamic-art-clock004.jpg?x-oss-process=image/resize,w_300)

![](http://chuquan-public-r-001.oss-cn-shanghai.aliyuncs.com/github-images/dynamic-art-clock005.jpg?x-oss-process=image/resize,w_300)

由于点阵的数量比较多，使用锁存器一个IO的输出电流难以点亮一排LED。因此需要在锁存器的输出与LED的输入之间加上三极管进行电流放大。这也是为什么gif效果图中有一个外接电路板的原因。
