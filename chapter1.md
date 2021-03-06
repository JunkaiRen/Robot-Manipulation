为体现机械臂碰撞检测与运动规划的效果，为机器人构建一个工作场景。如下图所示，红色物体为模拟桌面，两个橘色柱状物体为放置在模拟桌面上的障碍物，橙色小长方体为机械臂抓取的目标物。仿真实验有两个目的：

检验机械臂在笛卡尔空间内运动规划的可行性

检验机械臂抓取与防止目标物体的行为以及在此过程中的避障运动规划可行性。

仿真实验设置了三个目标位姿，分别为运动规划的起始位姿，目标物的抓取位姿以及放置位姿。如图b）、c）、d）中夹持器的位姿所示，为验证避碰运动规划的效果，将三个目标位置用两个障碍物隔离，从起始位姿开始的运动规划过程中，对末端位姿添加了与抓取姿态相一致的姿态约束，使夹持器在机械臂运动过程中保持朝下的姿态。实验证明，基于正确的配置，MoveIt！可以实现机械臂的避碰运动规划。机械臂从起始位姿运动到抓取位姿的过程中成功地避开了第一障碍物，如图c）所示，深绿色线条为机械臂末端的夹持器中心点的轨迹。在机械臂抓取目标物体后，需要将其安全地送达放置位置，如图d）所示，由于对工具坐标系姿态的约束，机械臂为避开较高的障碍物，规划了一条将夹持器抬起到较高位置的路径，保证机器人本体和抓取的目标物体都不与障碍物发生碰撞。

