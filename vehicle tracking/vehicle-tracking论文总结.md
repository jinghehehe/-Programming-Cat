# vehicle-tracking论文总结
***
SCI 三区 三作，提出一种多车辆跟踪算法，主要在目标检测，多目标跟踪及对漏检车辆采取单目标跟踪的方式这三个方面来平衡多车辆跟踪算法的准确率及实时性。
***
## 算法框架
![](https://github.com/jinghehehe/pictures/blob/main/Figure_2_DPI500.jpg)
### 目标检测改进点
目标检测算法采用的是无锚框的基于关键点检测的CenterNet算法，同时针对多车辆跟踪首先采用优化后的Non-local Neural Networks，cv领域即自注意力操作，一方面提升检测指标，但是保证了参数量。

### 多目标跟踪改进点
多目标跟踪采用的是在线跟踪匈牙利算法DeepSort来实现。
这里介绍两个知识点：1 匈牙利算法可以告诉我们当前帧的某个目标，是否与前一帧的某个目标相同。
2 卡尔曼滤波可以基于目标前一时刻的位置，来预测当前时刻的位置，并且可以比传感器（在目标跟踪中即目标检测器，比如Yolo等）更准确的估计目标的位置。
#### deepsort工作流程
DeepSORT对每一帧的处理流程如下：

检测器得到bbox → 生成detections → 卡尔曼滤波预测→ 使用匈牙利算法将预测后的tracks和当前帧中的detecions进行匹配（级联匹配和IOU匹配） → 卡尔曼滤波更新

Frame 0：检测器检测到了3个detections，当前没有任何tracks，将这3个detections初始化为tracks
Frame 1：检测器又检测到了3个detections，对于Frame 0中的tracks，先进行预测得到新的tracks，然后使用匈牙利算法将新的tracks与detections进行匹配，得到(track, detection)匹配对，最后用每对中的detection更新对应的track。

[deepsort参考](https://zhuanlan.zhihu.com/p/202993073)
