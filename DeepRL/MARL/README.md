
---
## 2019
---

## Distributed Multi-Agent Reinforcement Learning by Actor-Critic Method

### Paulo C. Heredia and Shaoshuai Mou


- [Paulo Heredia](https://www.cerias.purdue.edu/site/people/students/view/1918) - B.S. from MIT, studying PhD at Purdue University in Shaoshuai Mou's Lab

- [Shaoshuai Mou](https://engineering.purdue.edu/AIMS) - Professor, Purdue University and Director, Autonomous & Intelligent Multi-agent Systems (AIMS) Lab

=====


[Distributed Multi-Agent Reinforcement Learning by Actor-Critic Method](Heredia2019.pdf)

#### The Challenge
Multi-agent reinforcement learning or MARL has been subject to much attention due to its applications in a variety of fields such as mobile sensor networks, robotics, drone swarms, cybersecurity, and more.  The primary research challenges in MARL stem from the fact that each agent has its own local and private reward, and can only coordinate with nearby agents, which usually result in conflicts with other agents in credit assignment and coordinating actions.

This challenge has led to the rapid emergence of a new area of research -- the development of distributed algorithms for MARL in which there is no centralized coordination, and instead, local coordination among nearby neighbors are allowed.  Recently, researchers have also started to develop distributed MARL based on actor-critic methods in single-agent cases.

The problem in MARL is that each agent only can access a local reward, and can communicate with its nearby neighbors.  The solution to this problem that is championed by the authors of this paper is a distributed algorithm that uses the actor-critic method to enable all agents to cooperatively learn a control policy that maximizes the global objective function.  In this paper, the authors also describe simulations that serve to validate the proposed algorithm.

#### The Approach

This paper outlines a distributed algorithm for MARL which is based on the actor-critic methods.  In this framework, each agent is tasked with the development of an actor to generate a control input, given the state, and a critic to output a scalar value for the performance of the current policy, given a state and input pair.  The study adds to the body of knowledge in this realm by considering the expected sum of discounted rewards over an infinite time horizon.  This work extends previous findings by Wai et al. (2018) to help apply that research to both action-value functions and state-value functions, which suggests that such policy evaluation algorithm can potentially be used in an actor-critic framework.

For the case in which a network of many autonomous agents operate in an unknown environment or plant, the system can be described as a function of the state of the plant and the control inputs.  The goal of MARL in this paper is to achieve a globally optimal control policy to maximize the objective function.  The objective function is assumed to be a sum of discounted rewards, when a stochastic control policy is applied to the plant.

The paper's distributed algorithm for MARL introduces an actor and critic at each agent -- in other words, each agent trains an actor to generate a control input given the state (control policy), and a critic to output a scalar value for the performance of the current control policy.  The paper presents mathematical formulas which underlie the critic and actor training in this model.

#### Results

The main results of the paper relate to what the proposed algorithm can achieve under 9 assumptions outlined in the paper (please see pages 3-4).  The paper's novel actor-critic algorithm allows agents to use information from their neighbors in order to improve policies so that the globally averaged reward is maximized.

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

