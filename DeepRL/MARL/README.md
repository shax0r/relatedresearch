
---


## 2018
---

## Multi-Agent Reinforcement Learning Via Double Averaging Primal-Dual Optimization

### Wai, et al.

=====


[Multi-Agent Reinforcement Learning Via Double Averaging Primal-Dual Optimization](2018_Wai.pdf)


**Approach Development** 


[Wai]( http://www.se.cuhk.edu.hk/people/academic-staff/prof-wai-hoi-to/), [Yang]( http://www.princeton.edu/~zy6/), [Wang]( https://www.mccormick.northwestern.edu/research-faculty/directory/profiles/wang-zhaoran.html), and [Hong]( https://people.ece.umn.edu/~mhong/mingyi.html) propose a double averaging policy evaluation method in which agents iteratively perform averaging over both time and space to incorporate local reward information and neighboring gradient information, respectively. In their article, they demonstrate collaborative multi-agent RL with local rewards in a setting where all agents share a joint state. The transition dynamics of the shared joint state is determined together by each individual agent’s local actions. With each agent observing their local rewards, which may differ across agents, the agents aim at collectively maximizing the global sum of local rewards. The proposed ‘double averaging’ update scheme works by agents locally tracking full gradient estimates and incrementally updating the gradient using two main sources of information: local estimates of the full gradient tracked by neighboring agent and stochastic gradient evaluated on a new pair of joint state-action along the trajectory as well as the corresponding local reward. Each agent then updates its local copy of the primal parameter, based on the updated estimate of the full gradient. A global consensus is reached by agents iteratively exchanging local information via the network to collectively attain the desired primal parameter, which provides an optimal estimation of the global value function. The authors develop and empirically evaluate a primal-dual distributed incremental aggregated gradient method, which denotes a novel decentralized algorithm that provides saddle-point solution by combining dynamic consensus technique along with stochastic/incremental average gradient technique. The primal-dual distributed incremental aggregated gradient (PD-DistIAG) algorithm is built upon a primal-dual reformulation of the mean squared projected Bellman error minimization problem, which gives rise to decentralized convex-concave saddle-point problems. 


**Major Contributions/Why the approach is Superior**


1. Reformulation of the multi-agent policy evaluation problem using Fenchel duality 


2. Development of a decentralized primal-dual optimization algorithm with a double averaging update scheme. The scheme eliminates the complexities related to sharing and updating the primal variable across N-agents by using a double gradient tracking approach for the primal variable update and an incremental update approach for the local dual update.


3. The proposed algorithm is of independent interest for finding saddle-point solutions to broader classes of decentralized convex-concave saddle-point problems with sampled observations.


4. Establishment of the global geometric rate of convergence for the proposed algorithm, making it the very first algorithm to attain fast linear convergence for MARL.


5. The convergence analysis of the proposed PD-DistIAG method is the first to characterize the linear convergence of delayed and coupled system of inequalities.


>A distinguishing feature of our analysis is that it handles the worst case convergence of the proposed method, rather than the expected convergence rate popular for stochastic / incremental gradient methods.



**Storage and Computation complexities of the PD-DistIAG method**


Since the PD-DistIAG method necessitates access of previously evaluated gradients, each agent has to store about 2M gradient vectors to avoid re-evaluation. Besides, the PD-DistIAG method requires exchange of information between agents at every [iteration]( https://www.techopedia.com/definition/3821/iteration), which calls for a communication overhead. In that case, the authors argue that performing multiple local updates at the agent using different samples without really exchanging information with neighboring agents would be a natural solution aimed at reducing the communication overhead. Such modification to the PD-DistIAG method can be demonstrated using time varying weight matrix. According to the authors:


>The convergence of PD-DistIAG method in ‘time varying weight matrix’ scenario is part of the future work.


**Optimal convergence Assumption**


Since the PD-DistIAG method utilizes a gradient estimator tracking gradient over time (across M samples) and space (across N agents), it is assumed, during convergence, that every sample is selected at least once for every number of iterations. That is enforced using  a [cyclical selection rule]( http://www.manualsdir.com/manuals/579995/rockwell-automation-arena-users-guide.html?page=68). 


**Application**


The proposed RL scheme is highly applicable in multi-agent convex-concave optimization case scenarios where agents are coupled by state transition matrix; in large scale application like power grids, sensor networks and swarm robotics. 

