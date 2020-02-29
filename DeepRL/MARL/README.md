
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















----------------------------------------------------------------------------------------------

# Precision medicine as a control problem: Using simulation and deep reinforcement learning to discover adaptive, personalized multi-cytokine therapy for sepsis

--------------------------------------------------------------------------------------------------------------------


### Authors


[BRENDEN K. PETERSEN]( https://www.researchgate.net/scientific-contributions/2052798158_Brenden_K_Petersen)





 [JIACHEN YANG]( https://www.cc.gatech.edu/~jyang462/)




[WILL S. GRATHWOHL]( http://www.cs.toronto.edu/~wgrathwohl/)




[CHASE COCKRELL]( https://directory.uchicago.edu/organizations/61?type=departments)



[CLAUDIO SANTIAGO]( https://people.llnl.gov/santiago10)



[GARY AN]( https://directory.uchicago.edu/organizations/61?type=departments)



[DANIEL M. FAISSOL]( https://people.llnl.gov/faissol1)



###2018,



[Learning to Control Random Boolean Networks: A Deep Reinforcement Learning Approach](DeepRL/MARL/Petersen et, at._2018.pdf)




**Approach Overview/Why the Research is Important**

Any abnormality in living organisms’ immune systems directly result in tissue damage, which negatively impact mortality rates. In humans, dysregulation of the body’s immune system causes a condition known as [Sepsis] leading to a 28-50% mortality rate. [Petersen et, al.]( https://www.researchgate.net/scientific-contributions/2052798158_Brenden_K_Petersen), in their article, propose a novel approach that building on a previously developed agent-based model: Innate Immune Response Agent-Based Model (IIRABM) by combining it with a deep RL framework to device novel treatment policy for Sepsis. Particularly, the authors use a deep RL framework to control the simulation of a biological system (the human inflammatory signaling network responding to injury). According to the authors, the previously developed IIRABM reproduces general clinical trajectories of Sepsis by simulating the human inflammatory signaling network response to injuries. The model simulates the interaction of multiple cell types and is initiated by setting five physiological parameters defining sizes and nature of the injuries/infections as well as measures of the host’s resilience: microbial invasiveness, initial injury size, environmental toxicity, microbial toxigenesis, and host resilience. As explained by the authors, the control/mediation problem underlying sepsis is dysregulation of Cytokine signaling, which they propose a novel solution by casting the IIRABM as a deep RL environment. Their proposed approach exploits systemic cytokine and immune cell measurements during the course of treatment.



**Inputs**



		*Structural Input*



-	Innate Immune Response Agent-Based Model (**IIRABM**) implemented in C++ and exposed to Python using Boost C++ libraries.




-	OpenAI Gym Environment.




-	Deep RL framework (Deep Deterministic Policy Gradient (DDPG) algorithm) implemented in Python. 400 nodes for the Actor network and 300 nodes for the Critic network. For the critic network, the authors added a hyperbolic tangent activation to the output layer whereas in the critic network, the authors added actions at the second hidden layer. Further, for exploration purpose, the authors added uncorrelated Gaussian noise with a standard deviation of 0.1 independently to each dimension of the selected action vector. The standard deviation was decreased 10-fold every 1,000 episodes.



-	NVIDIA Titan X GPU (for training).




*Parametric Inputs* (21 real-valued state variables of interest at IIRABM’s grid points)
		

•	Concentrations for 12 cytokines.



•	 Concentrations for2 cytokine receptors.



•	Counts for 5 cell types.




•	 A measure of tissue damage.





•	A measure of infection.




**Intermediaries**


	Potential-based reward signal: to focus the learning process to terminal rewards as a result of long episodes.




	Terminal reward Signals ( -/+ 250), which denotes death and health outcomes.




	Action penalty function: to counter the implication of action implementation i.e drugs side-effects.





**Output**



An adaptive learned healing policy that significantly reduces parameterized patients’ mortality rates




**Breakthrough/Novelty**




•	The proposed strategy led to a learned policy resulting to 0% patient mortality during test time for the patient parameterization on which DDPG was trained.




•	After analyzing the generalizability of the learned policy by testing it over a set of 500 different patient parameterizations with 1-99% baseline mortality rates, the authors established that the overall mortality rate across all the 500 patient parameterizations reduced from 46.0 percent (without intervention) to 0.8 percent under the learned policy. 



>Additionally, under the learned policy, 460 of the 500 patient parameterizations (92%) have a mortality rate of 0%, 39 patient parameterizations (7.8%) exhibited reduced mortality rate (with an average reduction of 87%), and 1 patient parameterization resulted in no change in mortality rate compared to baseline.




•	The learned policy did not cause an increase in mortality for any patient parameterization and, from the results, it appears to generalize quite well despite being trained on a single patient parameterization. 



•	After testing the learned policy using patient parameterization with recurrent injury values, the authors found that the policy’s actions were adaptive; actions were able to switch from down-regulation to up-regulation during treatment in actions prescribed for certain cytokines like PAF. In an experiment, the authors proved the learned policy’s adaptive transition between up-regulation and inhibition, as well as dependence on the severity of patients’ initial injury.

**What to Note/Challenges/Assumptions**



-	The sepsis environment is inherently and deeply stochastic, mimicking the heterogeneity of the clinical setting. 


>Stochasticity leads to a substantially more challenging RL problem, in part because it causes the “signal” used for learning to be very noisy. That is, under the same conditions, a given action is
sometimes “good” and sometimes “bad.” This problem is exacerbated by the fact that episodes are relatively long (up to 4,603 steps, or 90 days of simulated time) and the IIRABM provides only one natural reward: a binary life or death outcome at the end of the episode. This results in a very difficult credit assignment problem, i.e. it is difficult to determine which of the many actions taken in a single episode are responsible for the observed outcome.





-	The clinical problem of sepsis and its representation in the sepsis environment have not been solved by humans, and therefore such techniques as seeding the Deep Reinforcement Learning Agent with demonstrations of ‘good’ and ‘bad’ episodes are not applicable in efforts to overcome sparse rewards. 



-	The authors assume that the spatially aggregated state space in IIRABM (each state variable summed across all grid points) provides sufficient information for learning a near-optimal policy.




-	The IIRABM environment is computationally expensive.



**Direction for Future Research**



Future  research studies should seek to further validate the generalizability of the proposed strategy using clinically diverse patients’ parameterization. 




Also, further experiments should be conducted using more clinically relevant observation space dimensions for Sepsis. 


**Application**


The proposed strategy is novel in drug discovery. It can act as a general strategy applicable in the formulation of specific, individual strategies aimed at solving continuously changing, immune-system-dependent health conditions in living organisms. 








# Learning to Control Random Boolean Networks: A Deep Reinforcement Learning Approach





### Authors

[Georgios Papagiannis]( https://www.researchgate.net/profile/Georgios_Papagiannis3)





 [Sotiris Moschoyiannis](https://www.surrey.ac.uk/people/sotiris-moschoyiannis)



### 2020,



[Learning to Control Random Boolean Networks: A Deep Reinforcement Learning Approach](DeepRL/MARL/Papagiannis and Moschoyiannis_2020.pdf)




**Approach Overview/Why the research is Important**


Cell behavior in living organisms is at the center of normal genetic processes that ensure normal biological growth and functionality. Cell perturbation as result of malfunctions of other cells or environmental causes like climate change lead to cell state transition: from current normal state to other states that may exhibit undesirable behavior.  For instance, Apoptosis and Proliferation behaviors exhibited by cancerous cells. According to [Papagiannis]( https://www.researchgate.net/profile/Georgios_Papagiannis3) and [Moschoyiannis]( https://www.surrey.ac.uk/people/sotiris-moschoyiannis), [Gene Regulatory Networks (GRNs)]( https://en.wikipedia.org/wiki/Gene_regulatory_network) have been observed to exhibit sudden emergence of ordered *undesirable behavior/collective behavior*, which are manifested as *attractors* in [Random Boolean Networks]( https://arxiv.org/pdf/nlin/0408006.pdf). In that context, developing a strategy aimed at causing desirable perturbation (towards desirable behavior) by targeted interventions to specific genes of a cell, becomes crucial in controlling cell behavior to ensure they cease to exhibit *undesirable/collective behavior*. 



[Papagiannis]( https://www.researchgate.net/profile/Georgios_Papagiannis3) and [Moschoyiannis]( https://www.surrey.ac.uk/people/sotiris-moschoyiannis), in their paper, apply a [Deep Q Network (DQN) with Double Q Learning (Double DQN)]( https://towardsdatascience.com/double-deep-q-networks-905dd8325412); which they refer as agent, that is trained by probabilistically sampling experiences from the environment. The environment being a Random Boolean Network (RBN), the proposed strategy samples experiences using [Prioritized Experience Replay (PER)]( https://arxiv.org/abs/1511.05952) with the aim of determining a near optimal control policy that drives the RBN from any state towards the *target attractor*. 





>The proposed approach makes no assumptions and requires no knowledge about the underlying structure, connectivity, dynamics or Boolean functions of the RBN. The agent learns how to control the network merely by direct interaction and observation of the RBN’s state transitions. In order to ensure that an intervention is as less intrusive to the network as possible we limit the number of interventions allowed per time step to a maximum of one and attempt to control the RBN in a restricted specified time frame.




**Inputs**



•	A set of RBN states





•	Target attractor(s)





•	A set of actions i.e. possible RBN interventions or allowed interventions



    		**Structural Input Elements**



•	Random Boolean Network (*Environment*) with a defined number of nodes; the nodes carry binary gene expression function in a Gene Regulatory Network context.



•	Double Deep Q Network with an input layer of size n corresponding to the observed state of the RBN. The Double DQN is also with a set size experience replay buffer for prioritized experience replay. The prioritized sampling function is probabilistic, which means it entails  a small constant ‘c’ to prevent experience without interventions from ever being sampled. According to the authors, the c constant and other Importance Sampling Weights are folded in the differentiation equation aimed at minimizing the loss function.



With c and Sampling Weights in loss function equation, >   Prioritized Experience Replay replays some experiences more than others according to how big the actual versus the predicted Q value was, with the assumption that the function approximator has ‘more’ to learn from experiences whose best action expected reward it predicted wrongly with greater margin.



		

**Intermediaries**

•	A deterministic transition matrix 



•	Stochastic rewards (weighted rewards denoting: non-attractor state, non-target attractor state or, target attractor/terminal state)



**Output**


Near optimal policy controlling an RBN towards the target attractor





**Breakthrough(s)/Novelty**



•	After training the Double Deep Q Network for 2.5 million episodes and using a greedy policy with the highest expected reward to control the RBN, the Double Deep Q Network attained 100% controllability.





•	Even though the authors increased the state space by a factor 1048576 (2power20) the proposed approach determined a control strategy that required only about 2.5 more interventions than [XCS]( https://pythonhosted.org/xcs/) needed for RBNs with 5 nodes. The strategy arrives at a near optimal policy from few time stems comparative to existing comparable strategies.



•	The proposed strategy is the first approach to use Double Deep Q Network and Prioritized Experience Replay as learning agent to directly control an RBN without any prior knowledge of the RBN’s structure, connectivity, Boolean functionality, or transition matrix knowledge. 




•	The proposed approach has higher scalability (25 nodes) compared to previous comparable approaches.





**Assumptions/What to note**



•	The proposed strategy’s probabilistic Prioritized Experience Replay assumes that the Double DQN’s non-linear function approximator has ‘more’ to learn from experiences whose best action expected reward itpredicted wrongly with greater margin.




	>practically training can be very time consuming, as training a Double DQN to find a control strategy for RBNs can require a large number of experiences to be sampled.




	>the use of non-linear function approximator (Double DQN) does not guarantee arrival at near optimal policy at every time step.






**Direction for Future Research**




•	The authors aim to investigate further the application of Deep Reinforcement Learning algorithms on the problem of control of RBNs, where they intend to focus on whether they can use the proposed strategy to determine a network’s driver nodes and attempt to control RBNs that are updated asynchronously.




•	The authors also aim to improve our current control implementation to scale to significantly larger RBNs as well as study other approaches to address the current limitations of the approach: 




> practically training can be very time consuming, as training a Double DQN to find a control strategy for RBNs can require a large number of experiences to be sampled.



> the use of non-linear function approximator (Double DQN) does not guarantee arrival at near optimal policy at every time step.




•	The generalizability of the proposed approach can be validated by 
applying the strategy to the  problem of controlling Probabilistic Boolean Networks.





**Application**




The proposed strategy can be applied in learning near optimal drug discovery policies based on interventions aimed at perturbing cell activity towards desirable target behavior (attractors).  Specifically, the strategy can output near optimal policies for correcting/controlling abnormal cell behavior of cancerous cells. 



Generally, the proposed strategy is novel in solving control problems in cases where the underlying dynamics, structure as well as transition mechanism of a system is unknown. 



