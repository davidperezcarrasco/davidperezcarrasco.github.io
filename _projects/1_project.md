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

- $$\mathcal{S}$$: Set of states.
- $$\mathcal{S}^-$$: Set of non-terminal states.
- $$\mathcal{T}$$: Set of terminal states.
- $$\mathcal{P}: \mathcal{S}^- \to \Delta(\mathcal{S})$$: Passive dynamics.
- $$\mathcal{R}: \mathcal{S} \to \mathbb{R}$$: Reward function.
- $$\lambda$$: Temperature parameter.

<!-- The optimality Bellman equation for LMDPs is:
$$
\frac{1}{\lambda} v(s) = \frac{1}{\lambda} \mathcal{R}(s) + \log{\mathcal{G}\left[z\right](s)} - \min_{\mathbf{u} \in \mathcal{U}(s)} KL \left( \mathcal{P}_{\mathbf{u}}( \cdot | s) \bigg\Vert \frac{\mathcal{P}(\cdot | s) z(\cdot)}{\mathcal{G}\left[z\right](s)}\right)
$$
where $$\mathcal{G}\left[z\right](s) = \sum_{s' \in \mathcal{S}} \mathcal{P}(s' \mid s) z(s')$$ and $$z(s) = e^{\frac{v(s)}{\lambda}} \quad \forall s \in \mathcal{S}$$, 
and 
$$v(s) = \mathcal{R}(s) \quad \forall s \in \mathcal{T}$$. -->


<!--### Z-learning Algorithm

\begin{algorithm}
\caption{Z-learning}
\label{alg:z-learning}
\begin{algorithmic}[1]
\State \textbf{input:} learning rate $$ \alpha \in (0,1] $$, temperature parameter $$ \lambda > 0 $$, LMDP with $$ \mathcal{R} $$, $$ \mathcal{P} $$, $$ \mathcal{S} $$, $$ \mathcal{S}^- $$, $$ \mathcal{T} $$
\State \textbf{output:} $$ \hat{Z}: S \rightarrow \mathbb{R} $$
\State \textbf{initialize} $$ \hat{Z}(s) \leftarrow 1 $$ for all $$ s \in \mathcal{S}^- $$, $$ \hat{Z}(s) \leftarrow e^{\mathcal{R}(s)/\lambda} $$ for all $$ s \in \mathcal{T} $$, $$ \hat{\mathcal{P}_{\mathbf{u}}} \leftarrow \mathcal{P} $$
\Repeat
\State $$ s_t \gets s_0 $$ (sample state from initial state distribution)
    \While{$$ s_t \notin \mathcal{T} $$}
    \State Take reward $$ r_t $$ from the current state $$ s_t $$.
    \State $$ G[z](s_t) \leftarrow \sum_{s' \in \mathcal{S}} \mathcal{P}(s' \mid s)\hat{Z}(s') $$
    \State $$ \hat{Z}(s_t) \leftarrow \hat{Z}(s_t) + \alpha [ e^{r_t/\lambda} G[z](s_t) - \hat{Z}(s_t) ] $$
    \State Update $$ \hat{\mathcal{P}_{\mathbf{u}}} $$ derived from $$ \hat{Z} $$
    \State Sample a next state $$ s_{t+1} $$ according to $$ \hat{\mathcal{P}_{\mathbf{u}}} $$
    \State $$ s_t \leftarrow s_{t+1} $$
    \EndWhile
\Until{convergence}
\end{algorithmic}
\end{algorithm} 

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

My research focused on enhancing the performance and scalability of state-of-the-art RL algorithms like Q-Learning and Z-Learning. By applying these algorithms to challenging Minigrid environments, I explored and evaluated methods to improve their efficacy in handling complex decision-making tasks. This involved developing efficient computational techniques for optimal action selection and optimizing value function approximation within linear LMDPs. Furthermore, I investigated the impact of exploration decay rates on the performance and convergence of these algorithms.-->