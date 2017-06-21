Gu, Shixiang, et al. "Deep Reinforcement Learning for Robotic Manipulation with Asynchronous Off-Policy Updates." arXiv preprint arXiv:1610.00633 \(2016\).

# 深度增强学习用于异步off-policy更新的机械臂

> 强化学习有望在较少人工干预的情况下帮助机器学得大量的行为技巧。但是**实际机器人在应用RL的时候，常常需要折中学习过程的自动化程度**，比如人为设计的策略或者人类辅助的验证，**以争取获得更短的训练时间**，这一点在实际物理系统中很重要。
>
> 深度增强学习通过训练通用目的的神经网络策略（general-purpose neural network policies）可以缓解这种限制，但是由于直接的深度增强学习算法显著的**高复杂的采样**，导致其目前的**应用仅限于仿真环境和完成一些简单的任务**。

这篇文章中，作者采用**基于off-policy训练深度Q-functions的深度增强学习算法**可以解决复杂的三维抓取动作，并且可以学到可以高效地在实体机器人上训练的**深度神经网络策略**。此外，通过将算法在多台机器人上同时运行，异步地推动策略更新，可以进一步缩短训练时间。

实验验证了算法可以在仿真环境中和真实机器人开门动作中学到大量3D抓取技巧，这些都不需要先验知识或人工设计的表达。

* **Markdown和扩展Markdown简洁的语法**
* **代码块高亮**

```flow
st=>start: Start
op=>operation: Your Operation
cond=>condition: Yes or No?
e=>end

st->op->cond
cond(yes)->e
cond(no)->op
```

| 项目 | 价格 | 数量 |
| --- | ---: | :---: |
| 计算机 | $1600 | 5 |
| 手机 | $12 | 12 |
| 管线 | $1 | 234 |

```flow
st=>start: Start
op=>operation: Your Operation
cond=>condition: Yes or No?
e=>end

st->op->cond
cond(yes)->e
cond(no)->op
```

$$E=mc^2$$  
$$E=mc^2$$

```python
class SomeClass:
    pass

if __name__ == '__main__':
    # A comment
    print 'hello world'
```

23323232

