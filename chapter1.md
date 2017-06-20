# 

MoveIt！是一款由Willow Garage公司开发并推广的应用于移动操作臂的开源软件。它囊括了有关运动规划、操作、3D识别、运动学、控制和导航相关的最新技术[^1]，为促进先进机器人学的应用，评估机器人设计和工业、商业、研究与开发等构建综合性机器人产品提供了一个易用的平台。自2013年10月起，MoveIt！有斯坦福轨迹研究所（SRI International）进行推广和维护，现已陈宫应用于65类机器人产品。



MoveIt！与ROS的区别：ROS是一个用于机器人的开源次级操作系统，提供了一些底层功能，如编译系统、消息传递、设备驱动、也提供集成功能，如导航。而MoveIt！提供的是运动学、运动或路径规划，碰撞检测、3D识别、机器人交互等功能。MoveIt！是ROS实现操作功能的一个主程序库，它依赖于ROS消息和编译系统，并使用了一些ROS通用工具，如可视化工具Rviz，机器人描述文件（URDF）等。通过使用MoveIt！助手（MoveIt！ Setup Assistant）配置机器人，可实现从MoveIt！到ROS的快速切入。

MoveIt！与OMPL的关系：MoveIt！提供了一个可扩展的插件结构用于集成各种各样的第三方运动规划库以完成机器人的运动规划任务。OMPL是MoveIt默认调用的用于实现运动规划的开源库。

MoveIt主节点架构如下：[http://moveit.ros.org/documentation/concepts/](http://moveit.ros.org/documentation/concepts/)

![](/assets/Screenshot from 2017-06-20 11:25:51.png)

上图为由MoveIt！为其ROS节点movegroup提供的高层系统架构。该节点扮演着一个集成中心的作用，主要负责将图中所示的所有单个组件集成后为用户提供一系列ROS运动指令和服务。用户可以通过C++、Python和GUI三种接口方式获取由move\_group提供的运动信息和服务信息。







[^1]: Chitta, S., 2016. MoveIt!: An Introduction. In Robot Operating System \(ROS\) \(pp. 3-27\). Springer International Publishing.

