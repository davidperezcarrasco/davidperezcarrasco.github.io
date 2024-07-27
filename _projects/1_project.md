---
layout: page
title: Efficient Algorithms for Linearly Solvable Markov Decision Processes
description: Study of Linearly Solvable Markov Decision Processes, incorporating novel embedding techniques and scalable solutions.
img: assets/img/grid15.png
importance: 1
category: Research
---

As part of my Bachelor's Thesis, I conducted in-depth research on reinforcement learning (RL) algorithms, addressing their scalability and efficiency in large and complex domains. This thesis explores the application of Linearly Solvable Markov Decision Processes (LMDPs) to tackle these challenges. A significant contribution of my work is the development of novel embedding techniques for creating precise and exact mappings between traditional MDPs and LMDPs. These techniques improve the approximation precision by 99.23% over the approach by Todorov, enabling robust and reliable comparisons across the two frameworks, regardless of the problem's definition or the nature of its dynamics.

This research evaluates and benchmarks the performance of traditional RL models against algorithms leveraging LMDPs, such as Z-learning, within an adaptable reinforcement learning framework. By implementing scalable and efficient versions of these algorithms, I provide a comprehensive comparison that highlights the advantages of LMDP-based approaches. Additionally, the thesis delves into various factors that enhance the decision-making capabilities of RL agents, such as algorithm design and exploration strategies, demonstrating the superiority of the LMDP framework in multiple settings. Moreover, I developed an [RL simulator](https://github.com/davidperezcarrasco/Efficient-Algorithms-for-Linearly-Solvable-Markov-Decision-Processes) that provides a generalized implementation of MDP and LMDP frameworks. This simulator supports optimized core methods and seamless integration with repositories like Minigrid and Gymnasium, allowing researchers to easily extend and apply it to diverse problem definitions without the need to build custom solutions.

## Linearly Solvable Markov Decision Processes

LMDPs are defined as $$\mathcal{L} = (\mathcal{S}, \mathcal{S}^-, \mathcal{T}, \mathcal{P}, \mathcal{R}, \lambda)$$ where:

- $$\mathcal{S}^-$$: Set of non-terminal states.
- $$\mathcal{T}$$: Set of terminal states.
- $$\mathcal{S}: \mathcal{S}^- \cup \mathcal{T}$$: Set of states.
- $$\mathcal{P}: \mathcal{S}^- \to \Delta(\mathcal{S})$$: Passive dynamics.
- $$\mathcal{R}: \mathcal{S} \to \mathbb{R}$$: Reward function.
- $$\lambda$$: Temperature parameter.

The optimality Bellman equation for LMDPs is:

$$
\frac{1}{\lambda} v(s) = \frac{1}{\lambda} \mathcal{R}(s) + \log{\mathcal{G}_{z}(s)} - \min_{\mathbf{u} \in \mathcal{U}(s)} KL \left( \mathcal{P}_{\mathbf{u}}( \cdot | s) \bigg\Vert \frac{\mathcal{P}(\cdot | s) z(\cdot)}{\mathcal{G}_{z}(s)}\right) \quad \forall s \in \mathcal{S}^-
$$

where $$ z(s) = e^{\frac{v(s)}{\lambda}} $$ and $$\mathcal{G}_{z}(s) = \sum_{s' \in \mathcal{S}} \mathcal{P}(s' \mid s) z(s')$$ with  $$v(s) = \mathcal{R}(s) \quad \forall s \in \mathcal{T}$$. 

Using this exponential transformation, the Bellman equation can be reformulated as:

$$
z(s) = e^{\mathcal{R}(s)/\lambda}  \sum_{s' \in \mathcal{S}} \mathcal{P}(s' | s) z(s')
$$

In matrix form, this is expressed as:

$$
\mathbf{z} = G\mathcal{P}\mathbf{z}
$$

where the vector $$\mathbf{z}$$ consists of elements $$z(s)$$, and the diagonal matrix $$G$$ has terms $$e^{\mathcal{R}(s)/\lambda}$$ on its main diagonal.

The optimally controlled transition probabilities can be obtained using the following equation:

$$
\mathcal{P}_{\mathbf{u}^*}(s' | s) = \frac{\mathcal{P}(s' | s) z(s')}{\sum_{s'' \in \mathcal{S}} \mathcal{P}(s'' | s) z(s'')}
$$

The iterative method to solve the final matrix equation is Power Iteration, which is equivalent to Value Iteration in MDPs. However, when a model of the environment is not available, an online algorithm becomes necessary. The analogous online algorithm to Q-learning in LMDPs is Z-learning, introduced by Todorov:

<div class="row justify-content-sm-center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/power-iteration-alg.png" title="Power Iteration Algorithm" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/z-learning-alg.png" title="Z-learning Algorithm" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Power Iteration and Z_learning algorithms.
</div>