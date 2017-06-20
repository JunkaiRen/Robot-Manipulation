机械臂运动规划实现

1. 创建MoveIt！功能包
   为使移动机械臂系统能够使用MoveIt！提供的操作功能，必须为其主节点提供相应的输入即配置文件。为了提高MoveIt！的使用便利性，开发人员为用户提供了一个图形用户界面——MoveIt！配置助手（MoveIt！ Setup Assistant），该助手的主要功能是根据机器人的URDF（Unified Robots Description Format）模型文件创建SRDF（Semantic RObot Description Format）文件。SRDF文件用于在语义层面上表达各种应用需求下的机器人信息，而这些信息是URDF文件无法表述的，如机器人几种特定姿态的关节角信息、运动链等。因此，在使用MoveIt！配置助手之前，需要为本文的移动机械臂创建一个URDF模型文件。
2. 创建URDF模型文件  
   URDF模型文件是描述机器人、传感器和室内环境等模型的XML表述文件。每一个XML表述语句都对应一个基于单一语言或多语言的语法解析器。URDF文件主要由Link标签和Joint标签两部分构成。如图1所示，Joint标签用于表述机器人的关节类型、运动学和动力学特性、连杆间的坐标转换关系等。Link标签用于表述连杆自身的运动学和动力学特性。由Joint标签和Link标签可构成各种形式的运动链，父连杆和子连杆的关系由Joint标签确定，如图1中的Link1作为两个子连杆Link2和Link3的父连杆。通过配置Joint标签和Link标签可构成不同形式的串联型树状结构。  
   ![](/assets/Screenshot from 2017-06-20 17:50:18.png) ![](/assets/Screenshot from 2017-06-20 17:50:39.png)  
   图 1. URDF树状结构

   UR5就是由6个关节和7个连杆构成的串联型树状结构。Joint标签主要有6种子标签用以配置父连杆与子连杆之间的关节类型、相应位姿等属性；Link标签主要由惯性、可视化和碰撞三个子标签构成，用以表述各连杆的惯性属性、可视化属性及碰撞属性。如图2所示：![](/assets/Screenshot from 2017-06-20 17:55:23.png)图 2. Joint标签和Link标签组成示意图

3. 配置MoveIt！

4. 运动规划仿真实验



