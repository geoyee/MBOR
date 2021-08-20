# MBOR

基于遥感图像的建模白模的快速生成，用到了Rhino（Grasshopper）参数化建模以及深度学习的建筑轮廓提取（基于paddlepaddle），可在Rhino 6中运行。

![](https://user-images.githubusercontent.com/71769312/130177046-d95c029a-f2e3-47b4-b532-f85ddb963bcc.gif)

## GH配置

1. 需要下载ghcpython，Grasshopper自带python为基于.net的ipython，要做深度学习的预测需要用到原生的python，ghcpython可以满足。

2. 对拖入ghcpython电池，选择菜单栏的Python->Choose Interpreter，将使用的python设置为虚拟环境下的pdseg环境（第二步配置的环境）下的python.exe。

## 使用

1. 下载.gh电池文件以及模型参数。
2. 打开.gh修改图像和参数路径。

## 训练信息

基于Aerial imagery dataset。该数据来自新西兰土地信息服务网站，包括187000座建筑物，被下采样为0.3m地面分辨率，并将其裁剪为8189块512×512像素的图块。这里将原始的训练集、验证集和测试集进行了合并。

<!--**ps：原始数据来自武汉大学摄影测量与计算机视觉小组（GPCV）----季顺平. 智能摄影测量学导论[M]，科学出版社，2018年4月.*-->

训练使用PaddleSeg提供的UNet++训练了10000个iters，得到的精度如下：

```
[EVAL] #Images=910 mIoU=0.9143 Acc=0.9773 Kappa=0.9085 
[EVAL] Class IoU: [0.8549 0.9738]
[EVAL] Class Acc: [0.935  0.9843]
```

## 交流与反馈

Email：[Geoyee@yeah.net](mailto:Geoyee@yeah.net)
