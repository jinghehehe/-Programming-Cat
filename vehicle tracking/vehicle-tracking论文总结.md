# vehicle-tracking论文总结
***
SCI 三区 三作，提出一种多车辆跟踪算法，主要在目标检测，多目标跟踪及对漏检车辆采取单目标跟踪的方式这三个方面来平衡多车辆跟踪算法的准确率及实时性。
***
## 算法框架
![](https://github.com/jinghehehe/pictures/blob/main/Figure_2_DPI500.jpg)
### 目标检测改进点
目标检测算法采用的是无锚框的基于关键点检测的CenterNet算法，同时针对多车辆跟踪首先采用优化后的Non-local Neural Networks，cv领域即自注意力操作，一方面提升检测指标，但是保证了参数量。

### 多目标跟踪改进点
多目标跟踪采用的是在线跟踪匈牙利算法DeepSort