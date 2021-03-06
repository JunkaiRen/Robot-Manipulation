### OMPL与MoveIt！介绍

**运动规划：**确保机械臂在工作过程中不与工作人员、机器人自身或其他设备发生碰撞。

**路径规划：**是机械臂运动规划问题中的核心问题，目标是在环境空间中寻找一条从机器人起始状态到目标状态的无碰路径。

**环境空间：**是一个三维的欧几里得空间，在该空间内定义了所有物理对象的几何信息，这些物理对象的集合被成为障碍物空间。

#### 一、OMPL

开源运动规划库（Open Motion Planning Library, OMPL[^1]）是由Rice大学的Kavraki实验室开发的专用于基于采样运动规划的一个C++语言开源库。OMPL不仅包含了许多主流的采样规划算法，如PRM，RRT，KPIECE（Kinodynamic Planning by Interior-Exterior Cell Exploration）等，而且以一种期望用户以最小输入即可解决各种复杂运动规划问题的方式进行设计。OMPL将运动规划问题从机器人学和人工智能领域的研究中进行抽象后，认为该问题可以单纯地看作是在连续空间内的搜索问题。

1. **基于采样运动规划**：基本思想是使用图结构近似搜索空间的连续性，然后对搜索空间进行采样病并择样本点作为近似图的顶点，近似图内各顶点之间的连线表示有效路径。

2. **OMPL局限**：只关注于运动规划算法在复杂约束下的高维连续空间的通用性搜索的实现，不包含机器人本体或其工作空间的表述，也不包含碰撞检测器或任何可视化功能。OMPL将状态有效性的定义权留给用户或其他集成OMPL的软件，为他们留出巨大的自由设计的空间。

3. OMPL对目前主流的采样算法进行研究后提出了**五个有关运动规划问题的核心概念**：

   * **状态空间**：状态空间（构型空间）内的点表征着规划系统的特点状态。对于一个自由运动的刚体，其状态空间由三个评议状态和三个旋转状态构成；而对于具有n个转动关键关节的机械臂，状态空间可被表征为一个n维的圆环面。

   * **控制空间**：控制空间表征了控制量空间的参数化。控制空间适用于动力学系统，对于几何层面的规划，不考虑控制量问题。

   * **采样器**：采样器用于从状态空间内生产不同的状态。对于基于控制的二系统，使用独立的控制量采样机对控制空间进行采样。

   * **状态有效性检测器**：是一个用于区分状态空间的有效部分和无效部分的算法程序。例如，使用状态有效性检测器进行避障检测，以及速度和加速度超限检测等。

   * **局部规划器**：在几何层面进行规划时，局部规划期用于进行状态点之间的插补。

下图为OMPL核心运动规划概念的各关键类及相互之间继承关系的架构：![](/assets/Screenshot from 2017-06-20 11:00:05.png)

---

#### 二、MoveIt！简介

MoveIt！是一款由Willow Garage公司开发并推广的应用于移动操作臂的开源软件。它囊括了有关运动规划、操作、3D识别、运动学、控制和导航相关的最新技术[^2]，为促进先进机器人学的应用，评估机器人设计和工业、商业、研究与开发等构建综合性机器人产品提供了一个易用的平台。自2013年10月起，MoveIt！有斯坦福轨迹研究所（SRI International）进行推广和维护，现已陈宫应用于65类机器人产品。

1. MoveIt！与ROS的区别：ROS是一个用于机器人的开源次级操作系统，提供了一些底层功能，如编译系统、消息传递、设备驱动、也提供集成功能，如导航。而MoveIt！提供的是运动学、运动或路径规划，碰撞检测、3D识别、机器人交互等功能。MoveIt！是ROS实现操作功能的一个主程序库，它依赖于ROS消息和编译系统，并使用了一些ROS通用工具，如可视化工具Rviz，机器人描述文件（URDF）等。通过使用MoveIt！助手（MoveIt！ Setup Assistant）配置机器人，可实现从MoveIt！到ROS的快速切入。

2. MoveIt！与OMPL的关系：MoveIt！提供了一个可扩展的插件结构用于集成各种各样的第三方运动规划库以完成机器人的运动规划任务。OMPL是MoveIt默认调用的用于实现运动规划的开源库。

MoveIt主节点架构如下：[http://moveit.ros.org/documentation/concepts/](http://moveit.ros.org/documentation/concepts/)

![](/assets/Screenshot from 2017-06-20 11:25:51.png)

上图为由MoveIt！为其ROS节点movegroup提供的高层系统架构。该节点扮演着一个集成中心的作用，主要负责将图中所示的所有单个组件集成后为用户提供一系列ROS运动指令和服务。用户可以通过C++、Python和GUI三种接口方式获取由move\_group提供的运动信息和服务信息。

---

OMPL：[http://ompl.kavrakilab.org/OMPL\_Primer.pdf](http://ompl.kavrakilab.org/OMPL_Primer.pdf)

[^1]: Sucan, Ioan A., Mark Moll, and Lydia E. Kavraki. "The open motion planning library." IEEE Robotics & Automation Magazine 19.4 \(2012\): 72-82.

[^2]: Chitta, S., 2016. MoveIt!: An Introduction. In Robot Operating System \(ROS\) \(pp. 3-27\). Springer International Publishing.

