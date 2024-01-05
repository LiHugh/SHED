# A Hierarchical Approach to Environment Design with Generative Trajectory Modeling

<p align="center">
  <h3 align="center">Dexun Li, Pradeep Varakantham</h3>
  <p align="center">
    Singapore Management University
    <br>
    <a href="https://arxiv.org/pdf/2310.00301.pdf">[Paper]</a>
    ·
    <a href="https://github.com/LiHugh/SHED">[Codes]</a>
    
  </p>
</p>

![image](Figures/framework.PNG#pic_center)

## 1. Abstract
Training generally capable Reinforcement Learning agents in complex environments is a challenging task that involves designing appropriate distributions of environments. Recent research has highlighted the potential of the Unsupervised Environment Design framework, which generates environment instances/levels at the frontier of the agent’s capabilities through adaptive curriculum learning using regret-based measures. While regret-based approaches have shown great promise in generating feasible environments, they can produce difficult environments that are challenging for an RL agent to learn from. This is because regret represents the best-case learning potential of an environment, without indicating how much the agent can actually learn from it. To address this limitation, we propose an alternative objective that employs marginal benefit, focusing on the improvement in the agent policy associated with the environment. This new objective is agent-focused and ensures that the environment is generated at a suitable pace for the agent's learning, resulting in rapid convergence. More importantly, we provide a closed-loop controlled environment generation approach that employs the Marginal Benefit and a new notion of environment diversity to improve the generalizability of the agent. Finally, we provide detailed experimental results and ablation analysis to showcase the effectiveness of our new methods.



## 2. Background
### 2.1 Unsupervised Environment Design, UED
In UED, we train a student agent to perform well across a set of in-distribution and out-of-distribution environments. To accomplish this, UED utilizes a teacher agent that provides a sequence of environment parameter values and generates the corresponding environment to train the student to generalize well to unseen environment levels.



## 3. Method
We propose the Marginal Benefit and Diversity driven Environment Design (MBeDED) approach to address UED problems. Our algorithm, MBeDED, relies on the teacher-student framework, which consists of an environment generator (teacher) and two student agents which help compute the marginal benefit of a generated environment. Top Figure provides the overall framework. The MBeDED algorithm incorporates two key components that differentiate it from existing research in solving UED problems
* Marginal benefit-based environment generator
* Diversity guided environment selection


## 4. Experiment Domain
we present our experimental results in the domains of BipedalWalker, Minigrid, and CarRacing to demonstrate the superior performance of our approach when a trained agent is transferred to new environments.


<div align=center>  <img title="BipedalWalker" src="Figures/walker_example_new.PNG" width=30%>   <img title="Minigrid" src="Figures/maze_example.PNG" width=30%> <img title="CarRacing" src="Figures/car_example.PNG" width=30%> </div>

We show some results here
![image](Figures/results_walker_ijcai.png#pic_center)


## BibTeX
> @article{li2023diversity,  
  title={Diversity Induced Environment Design via Self-Play},  
  author={Li, Dexun and Li, Wenjun and Varakantham, Pradeep},  
  journal={arXiv preprint arXiv:2302.02119},  
  year={2023}  
}


