---
layout: page
title: Novel Algorithms for Linearly Solvable Markov Decision Processes
description: Reinforcement learning framework for LMDPs, enabling evaluation of state-of-the-art algorithms for performance and scalability in complex domains.
img: assets/img/grid15.png
importance: 1
category: work
related_publications: false
---

While working for the UPF Machine Learning & AI Research Group, I tackled the challenge of applying reinforcement learning (RL) to increasingly complex decision-making problems. I developed a novel deterministic action simulator specifically designed for sequential decision-making tasks. This simulator seamlessly integrates with popular RL libraries, enabling the evaluation of cutting-edge algorithms within the framework of Linearly-solvable Markov Decision Processes (LMDPs).

<figure class="img-fluid rounded z-depth-1">
    <img src="{{ 'assets/img/grid_sol.gif' | relative_url }}" alt="Optimal grid solution animation" title="Optimal grid solution animation">
</figure>

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/minigrid_plots2.png" title="Throughput Comparison between Z Learning for a LMDP and Q Learning for an embedded MDP" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-4 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/value_function3.png" title="Optimal value function of a 4x4 Grid" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    On the left, a throughput benchmarking of Z Learning and Q Learning using the proper embedding from LMDP to MDP for precise comparison. On the right, the value function of the MDP for a small grid environment of 5 x 5 cells.
</div>



My research focused on enhancing the performance and scalability of state-of-the-art RL algorithms like Q-Learning and Z-Learning. By applying these algorithms to challenging Minigrid environments, I explored and evaluated methods to improve their efficacy in handling complex decision-making tasks. This involved developing efficient computational techniques for optimal action selection and optimizing value function approximation within linear LMDPs. Furthermore, I investigated the impact of exploration decay rates on the performance and convergence of these algorithms.