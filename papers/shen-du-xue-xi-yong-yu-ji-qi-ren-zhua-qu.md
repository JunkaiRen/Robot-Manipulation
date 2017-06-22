深度学习用于机械臂抓取

> Mahler, J., Liang, J., Niyaz, S., Laskey, M., Doan, R., Liu, X., Ojea, J.A. and Goldberg, K., 2017. Dex-Net 2.0: Deep Learning to Plan Robust Grasps with Synthetic Point Clouds and Analytic Grasp Metrics. arXiv preprint arXiv:1703.09312

抓取的难点：

抓取是manipulation里最常见的问题之一。早期对抓取的研究有很多在判定一个稳定的抓取是否形成，比如是否满足force closure（手指与物体的接触点是否可以产生抵抗任意方向、大小的外力）。除了通常意义上的稳定抓取，另一种限制物体位置的方式是caging，即通过放置手指，让物体无法离开这一区域。
<div align="center"> ![](/assets/image (1).png) </div>