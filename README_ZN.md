# RL-CBF
此代码在两个基准无模型算法之上实现了RL-CBF算法：信任区域策略优化（TRPO）和深度确定性策略梯度（DDPG）。RL-CBF算法在学习过程中提供安全保障，具体细节可以在论文“End-to-End Safe Reinforcement Learning for Safety-Critical Continuous Control Tasks”中找到。我们展示了在两个模拟任务上的学习：（1）倒立摆控制，（2）在5辆车组成的车队中进行车辆跟随。

在每个问题领域的文件夹中，有4个子文件夹实现了RL算法：
- **TRPO-CBF** - 在TRPO之上运行RL-CBF算法。对于车辆跟随示例，运行`sim.py`开始学习。对于倒立摆示例，运行`main.py`开始学习。
- **DDPG-CBF** - 在DDPG之上运行RL-CBF算法。对于这两个示例，运行`ddpg.py`开始学习。
- **TRPO** - 运行用于比较的基准TRPO算法。对于车辆跟随示例，运行`sim.py`开始学习。对于倒立摆示例，运行`main.py`开始学习。
- **DDPG** - 运行基准DDPG算法。对于这两个示例，运行`ddpg.py`开始学习。

文件`plotResults.m`和`plotCollisions.m`可以在MATLAB中运行，生成论文中所见的奖励和安全违规的图表。然而，由于空间限制，这里未包含数据文件，但所有代码和数据文件可以在以下链接找到：https://www.dropbox.com/sh/23t9ez2ho3wbp7g/AABGjN1GSvYkCEE8xA7cB707a?dl=0

超参数可以在`sim.py`或`main.py`文件中为车辆跟随和倒立摆分别调整。一旦学习完成（指定的迭代次数后），数据将以`.mat`文件的形式输出，其中包括每个回合的奖励和轨迹。关于代码的任何问题/问题，请联系rcheng@caltech.edu。