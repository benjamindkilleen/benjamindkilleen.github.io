---
title: "\"Good Robot!\": Efficient Reinforcement Learning for Multi-Step Visual Tasks with Sim to Real Transfer"
collection: publications
permalink: /publications/2020-08-01-good-robot
excerpt: 'Current Reinforcement Learning (RL) algorithms struggle with long-horizon tasks where time can be wasted exploring dead ends and task progress may be easily reversed.'
date: 2020-08-01
venue: 'IEEE Robotics and Automation Letters'
paperurl: 'https://dx.doi.org/10.1109/LRA.2020.3015448'
citation: 'A. Hundt, B. Killeen, H. Kwon, C. Paxton, GD Hager. "Good Robot!": Efficient Reinforcement Learning for Multi-Step Visual Tasks with Sim to Real Transfer. IEEE Robotics and Automation Letters, vol. 5, no. 4, pp. 6724–6731, Oct. 2020. doi: 10.1109/LRA.2020.3015448.'
---

## Abstract

Current Reinforcement Learning (RL) algorithms struggle with long-horizon tasks where time can be
wasted exploring dead ends and task progress may be easily reversed. We develop the SPOT framework,
which explores within action safety zones, learns about unsafe regions without exploring them, and
prioritizes experiences that reverse earlier progress to learn with remarkable efficiency. The SPOT
framework successfully completes simulated trials of a variety of tasks, improving a baseline trial
success rate from 13% to 100% when stacking 4 cubes, from 13% to 99% when creating rows of 4 cubes,
and from 84% to 95% when clearing toys arranged in adversarial patterns. Efficiency with respect to
actions per trial typically improves by 30% or more, while training takes just 1-20 k actions,
depending on the task. Furthermore, we demonstrate direct sim to real transfer. We are able to
create real stacks in 100% of trials with 61% efficiency and real rows in 100% of trials with 59%
efficiency by directly loading the simulation-trained model on the real robot with no additional
real-world fine-tuning. To our knowledge, this is the first instance of reinforcement learning with
successful sim to real transfer applied to long term multi-step tasks such as block-stacking and
row-making with consideration of progress reversal. Code is available at
[https://github.com/jhu-lcsr/good_robot](https://github.com/jhu-lcsr/good_robot).

[Read more.](https://dx.doi.org/10.1109/LRA.2020.3015448)

**See also:** [https://youtu.be/dvxqjJBWFD4](https://youtu.be/dvxqjJBWFD4)
