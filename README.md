# CAPTCHA-Recognition
第九届大学生服务外包大赛 A16 验证码识别 二等奖方案

深度学习的第一次练手项目--由于比赛期间大部分时间都花在了学习新知识上,尤其是第五题出现了一些比较奇怪的原因，训练一开始loss就直接降为0，最后把直接计算距离的损失函数改为了二分类的交叉熵函数才得以训练起来，还是too young too simple
所以后期没有更多的时间去尝试更加复杂的模型。不过也算是在深度学习的道路上开了个头~有点跑题

题目相关：
比赛中包括5类验证码，难度按照题号由简到繁，具体的每一类验证码的介绍详解说明文档

以下为5个模型在5类验证码的实验效果：

![image](https://github.com/SaulZhang/CAPTCHA-Recognition/blob/master/images/acc.png)

反思与总结：
由于没有经验这个比赛也是一边看着吴教主的course.ai课程，一遍查看博客，一边撸代码。其实这次对于新手而言比较有挑战性的是在第五题，前面四题只需要用到一些去噪、切割、滤波、图像增强等方法然后直接搭建一个简单的CNN网络基本上就可以跑到99%+的准确率。而第五道题则是属于one-shot learning不再是简单的classfication问题所以需要引入Siamese Network进行metric learning。在最终的5000张评测图片中，我们取得了98.2%的准确率，相对于自己本地测试的96%提升了2个百分点还是蛮开森的（原因主要是我们在最后把train、validation、test的数据全都丢进去了，所以说得数据者得天下）。在线下决赛阶段与一等奖队伍交流也了解到了第5题最后加上几层的GRU还可以使准确率上升到99%以上。

比赛已经过去了近半年了，也逐渐的了解到了一些OCR的知识。现在回头想想还可以再项目上进行如下的优化：（先立个flag，回头有时间回来优化）

主要还是采用一些目前在OCR领域里面比较work的方法来对模型进行改进：

1.对于端到端的学习方法可以采用CNN+RNN+CTC Loss进行改进，增强文本与标签的对齐关系。

2.还有另外的一种方法也值得尝试：CNN+RNN+attention

3.在图上增强方法也可以尝试采用STN进行仿射变换可以实现类似于attention的效果

感觉好像有点杀猪沿用宰牛刀的感觉-_-，总之，想方设法提升准确率就很有成就感。

补充(2019年11月8日)：最近发现有小伙伴陆陆续续star这个项目，为了方便大家进一步地了解技术的细节，这里把比赛的ppt贴出来了。
![image](https://github.com/SaulZhang/CAPTCHA-Recognition/blob/master/images/1.png)
![image](https://github.com/SaulZhang/CAPTCHA-Recognition/blob/master/images/2.png)
![image](https://github.com/SaulZhang/CAPTCHA-Recognition/blob/master/images/3.png)
![image](https://github.com/SaulZhang/CAPTCHA-Recognition/blob/master/images/4.png)
![image](https://github.com/SaulZhang/CAPTCHA-Recognition/blob/master/images/5.png)
![image](https://github.com/SaulZhang/CAPTCHA-Recognition/blob/master/images/6.png)
![image](https://github.com/SaulZhang/CAPTCHA-Recognition/blob/master/images/7.png)
![image](https://github.com/SaulZhang/CAPTCHA-Recognition/blob/master/images/8.png)
![image](https://github.com/SaulZhang/CAPTCHA-Recognition/blob/master/images/9.png)
![image](https://github.com/SaulZhang/CAPTCHA-Recognition/blob/master/images/10.png)
![image](https://github.com/SaulZhang/CAPTCHA-Recognition/blob/master/images/11.png)
![image](https://github.com/SaulZhang/CAPTCHA-Recognition/blob/master/images/12.png)
![image](https://github.com/SaulZhang/CAPTCHA-Recognition/blob/master/images/13.png)
![image](https://github.com/SaulZhang/CAPTCHA-Recognition/blob/master/images/14.png)
![image](https://github.com/SaulZhang/CAPTCHA-Recognition/blob/master/images/15.png)
![image](https://github.com/SaulZhang/CAPTCHA-Recognition/blob/master/images/16.png)
![image](https://github.com/SaulZhang/CAPTCHA-Recognition/blob/master/images/17.png)
