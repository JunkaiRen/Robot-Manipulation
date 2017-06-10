拓展到实际机器人

* 机器人不在是一个点，需要将机器人的体积考虑在内。
* 机器人的自由度更高，原本的算法是否都还可用？

理论基础——C空间/构型空间

* Configuration Space
* 用向量描述机器人构型
* 在C空间内，机器人是一个点

  * 平面机器人$$\left (x,y,\theta   \right )^{T}$$
  * 七轴机器人$$\left (\theta _{1},\theta _{2},\theta _{3},\theta _{4},\theta _{5},\theta _{6},\theta _{7}  \right )  ^{T}$$

    ![](/assets/Screenshot from 2017-06-10 12:23:10.png)

    ![](/assets/Screenshot from 2017-06-10 12:24:55.png)

高维度

* 蚁群等优化算法：收敛慢，更多局部极值点
* 可视图法：在高维空间中，算法不成立
* 栅格法
  * 理论上可行
  * 但计算量太大
  * 一般在高于3维的问题上不使用该方法
* 人工势场
  * 在C空间内建立势场不方便
  * 只对个别控制点进行计算，折算到每个关节上
  * 不完备且不最优，但对于简单问题很实用
* PRM和RRT

  * 不需要知道C空间的具体情况，只对**随机采样点**进行碰撞检测（判断是否在C空间的可执行区域内）
  * 两点之间采用简单的局部规划器（如Walk to）进行连接
  * PRM：获得一个图，采取图搜索算法求解
  * RRT：获得一个连接到终点的树，反向搜索即可
  * 在高维空间可行，概率完备且不最优
  * 现状
    * **主要使用PRM和RRT等基于采样的方法**
    * 这些算法计算的结果一般需要进行后处理（smoothing等）
  * PRM和RRT变种

    * C空间
    * 随机采样（平均采样、高斯采样等各种采样算法，T-RRT）
    * 有效性判断（如碰撞检测算法AABB、减少碰撞检测 Lazy-RRT）
    * 局部规划器连接（各种连接方法、重新连接RRT\*、PRM\*）

      ![](/assets/Screenshot from 2017-06-10 12:37:10.png)  
      ![](/assets/Screenshot from 2017-06-10 12:38:32.png)

**理论学习**

* Couseara：宾大 Robotics: Computational Motion Planning （简单编程）
* Choset, Howie M. Principles of robot motion: theory, algorithms, and implementation. MIT press, 2005.
* 经典论文+编程实现经典算法。

**实践**

* ROS MoveIt!：[http://moveit.ros.org/](http://moveit.ros.org/)
* 容易上手+容易修改

研究方向

* 理论现状
  * 从运动规划角度
  * 给定**足够多**的时间，一定能够最优且完备地求解到轨迹
* 从理论角度而言，这个问题已经解决了
* 研究方向
  * 新问题
  * 实用化

重规划 re-paln

考虑系统动力学

考虑接触动力学

**运动规划+任务规划**

实用化

**深度强化学习DRL**

* 在给定信息满足系统状态可观性的前提下，CNN强大的环境理解能力（observe→state
  ）
* RL可以进行路径规划 
  * 通过value Iteration等方式建立表格（s→
    a，v）
  * 用神经网络NN你和这个映射（）
* DQN

问题

1. 可观性怎么保证？
2. 需要多少数据？
3. 能不能拟合？



