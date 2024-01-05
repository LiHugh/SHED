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
Unsupervised Environment Design (UED) is a paradigm for training generally capable agents to achieve good zero-shot transfer performance. This paradigm hinges on automatically generating a curriculum of training environments. Leading approaches for UED predominantly use randomly generated environment instances to train the agent. While these methods exhibit good zero-shot transfer performance, they often encounter challenges in effectively exploring large design spaces or leveraging previously discovered underlying structures, To address these challenges, we introduce a novel framework based on Hierarchical MDP (Markov Decision Processes). Our approach includes an upper-level teacher's MDP responsible for training a lower-level MDP student agent, guided by the student's performance. To expedite the learning of the upper leavel MDP, we leverage recent advancements in generative modeling to  generate  synthetic experience dataset for training the teacher agent. Our algorithm, called Synthetically-enhanced Hierarchical Environment Design (SHED), significantly reduces the resource-intensive interactions between the agent and the environment.
To validate the effectiveness of SHED, we conduct empirical experiments across various domains, with the goal of developing an efficient and robust agent under limited training resources. Our results show the manifold advantages of SHED and highlight its effectiveness as a potent instrument for curriculum-based learning within the UED framework. This work contributes to exploring the next generation of RL agents capable of adeptly handling an ever-expanding range of complex tasks.



## 2. Background
### 2.1 Unsupervised Environment Design, UED
In UED, we train a student agent to perform well across a set of in-distribution and out-of-distribution environments. To accomplish this, UED utilizes a teacher agent that provides a sequence of environment parameter values and generates the corresponding environment to train the student to generalize well to unseen environment levels.

### 2.2 Diffusion model
In a diffusion probabilistic model, we assume a $D$-dimensional random variable $\vx \in \R^D$ with an unknown distribution $q_0(x_0)$. Diffusion Probabilistic model involves two Markov chains: a forward chain $\displaystyle q(\vx_t|\vx_{t-1})$ that perturbs data to noise, and a reverse chain that converts noise back to data. The forward chain is typically designed to transform any data distribution into a simple prior distribution (e.g., standard Gaussian) by considering perturb data with Gaussian noise of zero mean and $\beta_t$ variance for $T$ steps:    
$$q(\vx_t|\vx_{t-1}) =  \mathcal{N} ( \vx_t ; \sqrt{1-\beta_t}\vx_{t-1} , \beta_t \mI) \quad q(\vx_{1:T}|\vx_{0}) = \Pi_{t=1}^T q(\vx_t|\vx_{t-1})


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


