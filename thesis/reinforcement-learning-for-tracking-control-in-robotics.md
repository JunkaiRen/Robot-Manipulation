### 背景：

* 传统的机械臂控制：基于模型的前馈控制器来预测并弥补非线性因素，如重力、科氏力+反馈控制器用于弥补残余误差。
* 缺陷：获得机器人精确模型上存在难度；机器人的物理特性易于发生变化。这些会导致需要对机器人进行系统辨识。

### 工作：

* addresses the aforementioned problem from the point of view of model-free, learning controller which improves the tracking performance safely in an online fashion. 
* Improvement to the control performance is done by feeding an additive compensation signal given by a learned policy function to the robot’s nominal controller.



