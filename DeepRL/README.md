Deep Reinforcement Learning
=====


## 2018
---

### Palmer, et al.

[Lenient Multi-Agent Deep Reinforcement Learning](2018_Palmer.pdf)

  **A summary of Key breakthroughs/Approach Development** 

  [Palmer](https://cgi.csc.liv.ac.uk/~gpalmer/contact.php),[Tuyls](https://www.liverpool.ac.uk/computer-science/staff/karl-tuyls/), [Bloembergen](https://www.cwi.nl/people/daniel-bloembergen), and [Savani](https://www.liverpool.ac.uk/computer-science/staff/rahul-savani/) propose Multi-Agent Deep Reinforcement Learning approaches aimed at efficiently solving highly implicit coordination problems for parallel agents. The proposed approaches are based on two main deep reinforcement learning mechanisms: hysteretic Q-learning and leniency learning. The learning processes are made possible by convolutional neural networks:[Deep Q-Networks (DQNs](https://www.techopedia.com/definition/34032/deep-q-networks)from which agents/learners (hysteretic Q-learners and lenient learners) can update their state-action pairs using stored state transitions in the [Experience Replay Memories (ERMs)](https://datascience.stackexchange.com/questions/20535/what-is-experience-replay-and-what-are-its-benefits).

  The authors develop and empirically evaluate a Lenient Deep Q-Network algorithm in which agents’ state-action pairs mapped in initially optimal temperature values update by decaying or cooling in every visit, therefore transitioning from an optimistic to an average reward learner in an environment that yields [Stochastic reward](https://en.wikipedia.org/wiki/Markov_reward_model).The authors make the leniency learning process more effective by introducing two extended processes: Retroactive Temperature Decay Schedule (TDS) and Greedy exploration strategy. TDS sets a sufficient temperature value at the terminal stages of failed learning processes to avoid repeated decay processes that may lead to the convergence to sub-optimal policy joints by ensuring that agents maintain a lenient disposition to one another. The original amount of leniency is determined by temperature values and is stored in Experience Replay Memories along with transition states. The proposed Lenient Multi-Agent Deep Q-Network architecture entails [autoencoders](https://towardsdatascience.com/deep-inside-autoencoders-7e41f319999f), which help in automatically clustering high dimensional or continuous state spaces using agents’ replay memories. Subsequently, Greedy exploration strategy enables agents to choose a greedy action within frequently visited states while remaining exploratory for less-frequented areas of the environment. The Greedy exploration strategy attains an average temperature of the current state of frequently visited state-action pairs while estimating the reward to the next action using less or unexplored state-action pairs, a process that ensures stability in the deep reinforcement learning process.
	
  According to the authors, the Hysteretic Q-learning process happen in the same way as leniency learning except in hysteretic Q-learning, state-action pairs are originally mapped to optimally predefined Q-values (estimates from the sum of discounted future rewards stored in multi-layer neural networks) stored in agents’ ERMs. The Hysteretic Deep Q-Networks facilitate the [Hysteretic Q-learning process](https://www.semanticscholar.org/paper/Hysteretic-q-learning-%3Aan-algorithm-for-learning-in-Matignon-Laurent/ce8ad8b3dd21ff33c79f249ce85ac5856592a913)in two learning rates: one called alpha where every state-action interaction increases the value estimate (Q-value) and a Beta learning rate where every interaction reduces the value estimate. However, as a result of the Beta learning rate interdependencies with other agents’ exploration strategies, the Hysteretic Q-learning process is most likely to lead to sub-optimal policy joint in environments with stochastic rewards. As a result, the authors proposed and empirically evaluated an improved Hysteretic Deep Q-learning Network algorithm with a pre-computed learning rate schedule called the Scheduled-HDQN, which applies less optimism towards state transitions near terminal states compared to earlier transitions within the episode to avoid overestimation of Q-values in a Stochastic reward environment. Both Leniency and Hysteretic Q-learning approaches use [Double-Deep Q-Networks](https://towardsdatascience.com/double-deep-q-networks-905dd8325412)to induce sufficient optimism in the early learning stages to allow learning agents to converge to an optimal joint policy. The Double-Deep Q-Networks entail current and target networks whereby current state weight values and resulting action-state weight values after n transitions are stored respectively, forming a double Q-learning process. 
	
  **Emperical Validation/Why the developed approach is superior** 
	   
  The authors empirically evaluate each developed approach using the Coordinated Multi-Agent Object Transportation Problem (CMOTP), which is a fully-cooperative multi-agent problem requiring reinforcement learning agents to learn fully-cooperative joint-policies from processing high dimensional and noisy image observations.  To effectively test the distributed problem-solving capacities as well as compare efficiencies between the proposed approaches: Lenient Deep Q-Network (LDQN) algorithm and Schedules-Hysteretic Deep Q-Network, the authors introduces two extensions to CMOTP environment.  The first extension is the narrow passage provision, which allows the testing of lenient agents’ ability to prevent the premature decay of temperature values. The second extension introduces two dropzones yielding stochastic rewards, which aim at testing agents’ ability to converge towards an optimal joint-policy while receiving misleading rewards. The authors compare the developed approaches’ efficiencies in converging to optimal joint policies in standard CMOTP, deterministic CMOTP, and stochastic reward CMOTP, in noisy and non-noisy conditions. They find that LDQNs significantly outperform standard and scheduled-HDQNs within environments that yield stochastic rewards. After performing a LDQN hyperparameter analysis, the authors make a novel finding that the highest performing agents within stochastic reward domains use a steep temperature decay schedule that maintains high temperatures for early transitions combined with a temperature modification coefficient that slows down the transition from optimist to average reward learner, and an exploration exponent that delays the transition from explorer to exploiter. Another notable novel breakthrough by the authors is the introduction of two extensions to leniency, including a retroactive temperature decay schedule that prevents the premature decay of temperatures for state-action pairs and a Greedy exploration strategy that encourages agents to remain exploratory in states with a high average temperature value. The extensions can, in theory, also be used by lenient agents within non-deep settings.
	
  **What to look out for/Pending validations** 
	
  Having successfully merged leniency with a Double-DQN architecture and demonstrated that leniency can help Multi-Agent Deep Reinforcement Learning agents solve a challenging fully cooperative CMOTP using high-dimensional and noisy images as observations, the proposed approach is left to be tested and validated using more sophisticated components like Prioritized Experience Replay Memory and more implicit coordination tasks like the ones having randomly distributed stochastic rewards throughout episodes. 
	
  **Application**
	
  The proposed deep reinforcement learning approach: Lenient Multi-Agent Deep Reinforcement Learning would be novel in solving highly coordinated problems in large tournament stochastic games, stock market predictions, betting odds, manufacturing robotics processes, and human robot cooperation. 





==================

## Value-Decomposition Networks For Cooperative Multi-Agent Learning Based On Team Reward
======


## 2018
---


### Sunehag, et al.,



[Value-Decomposition Networks For Cooperative Multi-Agent Learning Based On Team Reward](2018_Sunehag.pdf)
        
	
   **Authors**


Peter Sunehag-DeepMind sunehag@google.com


Guy Lever-DeepMind guylever@google.com


Audrunas Gruslys-DeepMindaudrunas@google.com 


Wojciech Marian Czarnecki-DeepMindlejlot@google.com


Vinicius Zambaldi-DeepMind vzambaldi@google.com


Max Jaderberg-DeepMind jaderberg@google.com


Marc Lanctot-DeepMind lanctot@google.com 


Nicolas Sonnerat-DeepMind sonnerat@google.com


Joel Z. Leibo-DeepMind jzl@google.com


Karl Tuyls-DeepMind & University of Liverpool karltuyls@google.com


Thore Graepel-DeepMind thore@google.com


  [Sunehag](https://www.apollo.io/people/Peter/Sunehag/54a72ddd7468696de7ca961c?__cf_chl_jschl_tk__=c7844ab9b70c68c97b044638180f6412c241e597-1578940904-0-AcOVavnLn7aANoLktdu1R7xqaEt0v2pxdvLJDlIqTLMvtAcZ7lg5OmIF0qPpjextfYXqSA7xBDrSI0RXJjbKTWJm6jTuiTC7Twt5kjuZfE2vsSDB5s2rGZWSgQGvYqFTS_u_EypFYtkclvJYQU8hnLcd_QHRKJXDk2OLtLZ__WMuNoHjYltwMUyCnGwcr2RpEaxwsXcg-HVrvBzfKys-wRTrXD6J6_cSEH4QTlGdSj2hQ5F7bIyujGIpC8SyOv0qcpPzRE9iWQmtvPuHxfMfnNf_3fzxxbDqfDpOgUtZO7EdqWoZssxNYLWNC4oWZJJxM7UyV9a5ItzkaM1D3Ogo-s2Unb-wdiFYt40XEFFOmXXIzscnsNjd_K6eSasylx9Imw), et al.,in their article, propose and evaluate an intriguing deep reinforced learning approach called ‘learned additive value-decomposition’ approach, specifically enhanced for complex cooperative multi-agent problems. The authors build an additional layer: learned additive value-decomposition layer to the standard [Deep Q-Network](https://pythonprogramming.net/deep-q-learning-dqn-reinforcement-learning-python-tutorial/) architecture, for example, having three standard layers including the low-level layer, the recurrent layer, and the dueling layer that feeds individual agent Q-values to the value decomposition layer. The value-decomposition layer sums individual agent Q-value to get a total Q gradient. 
   
   
  

  **Major Breakthrough/Why the Approach is Superior**
  
  
   The learned additive value-decomposition approach is unique and superior because it converges to an optimal joint policy by learning optimal linear value-decomposition from a team reward signal, which is accomplished by back-propagating the total Q gradient via deep neural networks representing individual component value functions. By so doing, the value-decomposition framework allows continuous centralized learning of agents where agents learn concurrently at training time, t, and can be deployed independently because the implicit value functions learned by each agent are only based on the agent’s local observations. That means that using the total Q gradient to establish/learn an optimal linear value-decomposition function across a number of agents yielding a target reward, t; individual agents can learn their individual decomposed optimal linear value functions and converge at an individual optimal policy/action independently, based on their local observation-action spaces.  After testing this approach against fully centralized framework, fully independent learners framework as well as a two-agent framework where individual agents learn directly from the joint reward signal, the value-decomposition framework outperformed the rest by large margins. The approach avoids sub-optimal policy convergence by interference by spurious rewards as well as time-wasting by idle agents in a centralized system where learning is neither concurrent nor independent.
     
     
  Implicitly, the value-decomposition network aims to learn an optimal linear value-decomposition from the team reward signal, by back-propagating the total Q gradient through deep neural networks representing the individual component value functions.


  **Assumption**


   The learned additive value-decomposition approach leverages on the assumption that the joint action-value function for the system can additively be decomposed into value functions across agents. 
     
     
  The main assumption we make and exploit is that the joint action-value function for the system can be additively decomposed into value functions across agents.


  **Application**


  As highlighted by the authors, the proposed deep RL approach will be effective in solving complex cooperative multi-agent problems in busy intersection traffic transportation systems, complex multi-operational manufacturing processes, complex stochastic games, complex autonomous driving systems, and general robotics for MAS. 




---

## Multi-Agent Reinforcement Learning Via Double Averaging Primal-Dual Optimization
=====


## 2018
---

### Wai, et al.


[Multi-Agent Reinforcement Learning Via Double Averaging Primal-Dual Optimization](Wai et al-2018.pdf)


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

