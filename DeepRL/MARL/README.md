
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

---


## Fully Decentralized Multi-Agent Reinforcement Learning with Networked Agents

### Zhang, et al., 2018b

- [Kaiqing Zhang](https://ece.illinois.edu/directory/profile/kzhang66) - Fellow and Graduate Student, Department of Electrical and Computer Engineering & Coordinated Science Laboratory, University of Illinois Urbana-Champaign (UIUC)
- [Zhuoran Yang](http://www.princeton.edu/~zy6/) - Ph.D. Candidate, Department of Operations Research and Financial Engineering, Princeton University
- [Han Liu](http://magics.cs.northwestern.edu/index.html) - Associate Professor of Computer Science & Statistics, Northwestern University, & Tencent AI Lab
- [Tong Zhang](http://tongzhang-ml.org/) - Professor of Computer Science and Mathematics at Hong Kong University of Science and Technology (affiliated with Tencent AI Lab in this publication)
- [Tamer Basar](http://tamerbasar.csl.illinois.edu/) - Department of Electrical and Computer Engineering & Coordinated Science Laboratory, UIUC

=====

[Fully Decentralized Multi-Agent Reinforcement Learning with Networked Agents](Zhangetal2018b.pdf)

#### The Challenge

Reinforcement learning is a type of learning in which the decisionmaker (also called the agent) seeks to achieve optimal behavior in the presence of uncertainty by interacting with the environment.

Multi-Agent Reinforcement Learning (MARL) is the deep learning discipline that focuses on models that include multiple agents that learn by dynamically interacting with their environment.  MARL systems are intrinsically distributed.  The complexity of MARL scenarios increases with the number of agents in the environment.

There are two main kinds of MARL: centralized and decentralized.  Centralized MARL models, which are easier to implement, use a controlling authority to manage rewards; however, this feature of centralized MARL reduces autonomy of the system.  That's why researchers have looked to decentralized MARL models to improve autonomy.  

Instead of a controlling authority managing the rewards for each one of the agents, [decentralized MARL](https://towardsdatascience.com/smart-incentives-and-game-theory-in-decentralized-multi-agent-reinforcement-learning-systems-58442e508378) relies on agents incentivized to act autonomously.  Agents compute their best-response policies themselves in decentralized MARL.  However, decentralized MARL is more difficult to implement, especially in scenarios with large numbers of agents.

Building an incentive model for large-scale MARL systems remains one of the biggest challenges for the implementation of these novel architectures.

#### Why this paper is important

This paper introduces two decentralized MARL actor-critic algorithms with function approximation.  These algorithms are theoretically proven and then their implementation and real-world performance is discussed.

This work advances foundational knowledge needed to improve decentralized MARL for distributed, highly autonomous systems.  Decentralized MARL is ideal for many real-world scenarios such as sensor networks and intelligent transportation systems, where a central controller either does not exist or is costly to install.  Decentralized MARL's benefits include scalability and robustness to malicious attacks.

MARL systems are one of the most exciting areas of research in deep learning, and as models become more decentralized, robust incentive models will be come more important.

#### Networked multi-agent reinforcement learning

This paper discusses a decentralized protocol in which agents are connected by a possibly time-varying communication network which serves as the channels for agents to exchange information in the absence of any central controller.  This type of MARL seeks to maximize rewards of all agents over the network.

In the described model, the actor step is performed individually by each agent without needing to infer the policies of others.  In the critic step, each agent shares its estimate of the value function with its neighbors on the network so that a consensual estimate is achieved, which is further used in the subsequent actor step.  

#### Benefits of the current approach

For the most part, the benefits of this approach, which relies on actor-critic algorithms, are typical of standard distributed distributed/decentralized algorithms over networked systems.  

- Local information at each agent is able to diffuse across the network, making the network-wide maximum reward achievable.

- Robustness against malicious attacks

- Communication efficiency

- Scalability of algorithms with high-dimensional state-action spaces.  An additional advantage of this particular approach over previous distributed MARL approaches is that by combining decentralized network architecture and function approximation, this approach can be applied to large-scale MARL problems.

#### Contributions of this approach

1. Formulation of the fully decentralized MARL problem for networked agents, and implementation of a version of the policy gradient theorem adapted to this setting.

2. Development of two decentralized actor-critic algorithms with function approximation, which enable the present approach's application to large-scale MARL problems.

3. In the special case of where linear function approximation is used, convergence guarantees are established for the proposed algorithms.  This is in contrast to previous approaches which estimate the reward of all agents to be identical.

> Our work appears to be the first study of fully decentralized MARL algorithms for networked agents with function approximation, with probable convergence guarantees.

In this approach, multiple agents are considered to be heterogeneous with distinct policies and rewards, while some multi-task RL algorithms rely heavily on the assumption that the policies of various tasks are similar to a great extent.

#### Conclusions and Future Directions

In this paper, the problem of MARL with network agents is considered -- specifically, the fully decentralized setting in which each agent makes individual decisions and receives local awards, while exchanging information with neighbors over the network to accomplish optimal network-averaged return.

In this context, two decentralized actor-critic algorithms with function approximation are proposed, theoretically validated, and tested, which can work on large-scale MARL problems with numerous agents and massive state-action spaces.

Future work in this realm, proposed by the researchers, is to extend these algorithms and analyses to a setting with not only collaborative agents, but also competitive ones over the network.  A second future goal is to extend this algorithm to MARL settings with continuous action spaces.
