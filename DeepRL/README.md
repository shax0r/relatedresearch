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
  
  
  
  
  
-------------------------------------------------------


## Primal-Dual Algorithm for Distributed Reinforcement Learning: Distributed GTD


******************


### Lee, Yoon, and Hovakimyan,



### 2018,


### [Primal-Dual Algorithm for Distributed Reinforcement Learning: Distributed GTD](Lee, Yoon, and Hovakimyan-2018.pdf)





**Learning Scheme Overview**


[Lee](https://www.apollo.io/people/Donghwan/Lee/5dcdce8185a5d000012061ca?__cf_chl_jschl_tk__=a229ba5cd92c164b536a7dfb63a277aac209f17f-1579379950-0-AWhYgKRpo_9z2z4LhKOLRQQAcpbXz33QALApNkWO9LPHVCYyzrEexOYTlAGi2l7NdXkEgH1rGYWWGkCOTUtrF7DCpTkfihs59GKQRf1bFFOTD4IX0g07ocktAw5byMJCFGsBM_XBLv8OvpWmXwREabQnXMwEHmlys5d1eWwi48Kn7ERa44DPQ-QUQnQz47b8UwfUrNGGQliYvK3rCP1VaXNWU3E4C8EvBG2tiSJQFVAiVkVrD6Oa0Eywmk7_yAAehKfsHAyYVgyo58yUM0wYbFHsFifEnI_uFIfpazQlVvn_wDc2v3iBnOOfEtuq88bjRzKUcQm3U0c_Z9O7n0jOtFgRY_gHgYXTRtg2kXGi4G3DY35_xLkhVRwGov-uIsySpA), [Yoon](http://naira.mechse.illinois.edu/sciencex_teams/hyung-jin-yoon/), and [Hovakimyan](http://naira.mechse.illinois.edu/sciencex_teams/naira-hovakimyan/) present an improved overview of a distributed version of the gradient temporal-difference (GTD) learning algorithm for multi-agent Markov decision processes. It is an intriguing proposal that needs further validation because it aims at learning a global infinite horizon discounted cost function or the global value function for fixed policies without the model knowledge (statistics of the state transitions and rewards). The algorithm, which is a primal-dual distributed GTD algorithm, works by converting case problems into constrained convex optimization with consensus constraints. In that case, the problem is viewed as a constrained optimization and is therefore solved using a primal-dual saddle point algorithm.


**Inputs and Outputs**


1.	**Inputs**


      -fixed policy and a Markov Decision Process Quadruple (infinite state space, infinite action space, a tensor representing an unknown state transition probability matrix, a reward function, and discounting factor)


2. **Output**


-Infinite horizon discounted value


With all the parameters characterizing linear function approximation including infinite state space, infinite action space, a tensor representing an unknown state transition probability matrix, a reward function, and discounting factor; the infinite-horizon discounted value function with a defined fixed stochastic policy ‘pie’ can be calculated from pre-selected basis functions by minimizing the mean square projects Bellman error loss function.  That means that for each agent to learn an approximate value of the global reward ( an averaged summation of individual agent’s local rewards) without the knowledge of their transition models, a solution to the projected Bellman equation has to be found using [consensus optimization]( https://www.cvxpy.org/examples/applications/consensus_opt.html). The authors  add ‘consensus box constraints’ to the unique solution of the projected [Bellman equation]( https://en.wikipedia.org/wiki/Bellman_equation), which is represented as stationary points of the [Ordinary Differential Equaltion (ODE)]( https://en.wikipedia.org/wiki/Ordinary_differential_equation) to establish a stochastic approximation algorithm that takes advantage of the ODE properties. The constraints are added to guarantee the stability and convergence of the proposed algorithm.  In that case, it is assumed that each agent’s learning parameter is exchanged via a communication network defining associate relations among agents. With a fixed focus on the value evaluation problem with fixed local policies, the authors can prove; using ODE-based methods that the proposed algorithm partially converges to a set of stationary points of the optimization problem in distributed multi-agent Markov decision process cases with sampled observations and fixed policies.

**Why the Learning Scheme is Novel**


+ One main advantage of the proposed scheme is its off-policy learning proponents; without the knowledge of individual agent’s transition model.


+Learning tasks and consensus are unified into a single ODE, thus, simplifying convergence validation using ODE-based methods; as proved  by the authors validation analysis. Unlike previously proposed algorithms, it incorporates consensus tasks into equality constraints.


+The algorithm is a stochastic primal-dual method for solving saddle point problems, which allows application of optimization analysis tools for improving convergence speed as well as the complexity of the algorithm.


+The proposed learning scheme can be extended directly in cases with stochastic communication networks. 

**Assumptions/What to look out for**


.The proposed algorithm lacks theoretical guarantee that it improves previously proposed consensus-based algorithms.


.The proposed approach assumes that every agent in a distributed multi-agent fixed-policy setting can observe the entire combination of global joint state-actions and local rewards.


.The learning scheme assumes that each agent’s learning parameter is exchanged via a communication network defining associate relations among agents.

.Optimal convergence of the proposed scheme depends on if the added constraints are sufficiently large and satisfy the authors set assumption for the constraint sets


> The constraint sets satisfy ¯_∗ ∈ C¯_, ¯v∗ ∈ C¯v, ¯ w∗ ∈ C¯ w, and C¯μ ∩ F 6= ∅.



**Application**


The proposed RL scheme is applicable in distributed multi-agent saddle point problems with fixed policies and an unknown transition models e.g in Stock market value projections and sales projections in departmentalized business organizations with different product lines.








_________________________________________

# Putting An End to End-to-End: Gradient-Isolated Learning of Representations

----------------------------------------




**Authors**



[Sindy Löwe](https://loewex.github.io/)




[Peter O’Connor]( https://scholar.google.co.uk/citations?user=oVnU6OsAAAAJ&hl=en)



[Bastiaan S. Veeling](https://scholar.google.com/citations?user=qStzdQsAAAAJ&hl=fr)




### 2019,



[Putting An End to End-to-End: Gradient-Isolated Learning of Representations](Lowe, O’Connor, and Veeling_2019.pdf)



**Approach Overview**



Minimizing the error or loss in learning processes is vital in all deep learning schemes. [Lowe]( https://loewex.github.io/), [O’Connor]( https://scholar.google.co.uk/citations?user=oVnU6OsAAAAJ&hl=en), and [Veeling]( https://scholar.google.com/citations?user=qStzdQsAAAAJ&hl=fr) develop and test an improved deep learning scheme in which agents/modules reduce noise by greedily confining learning locally to modules and blocking the transfer of gradients from module to module; as observed in the biological neural networks. The authors develop a novel, module-local, self-supervised learning using the brain analogy theorizing that the human brain learns to process perceptions by optimally preserving information of input activities in each layer. Primarily using the brain analogy and the [Greedy InfoMax principle]( https://www.groundai.com/project/greedy-infomax-for-biologically-plausible-self-supervised-representation-learning/1), the authors come up with the Greedy InfoMax (GIM) approach. In their approach, the authors restructure the conventional deep neural network by dividing it into stacked, gradient-isolated modules and develop a learning scheme that works by optimizing, in isolation, mutual information between representations of temporally nearby module-patches at each layer. With the *feature module* at the top of the stack, the proposed gradient-isolated learning of representations only works best for downstream tasks like object identification and voice recognition. Unlike [Contrastive Predictive Coding]( https://arxiv.org/pdf/1807.03748.pdf) and greedy supervised learning approaches, which uses labeled datasets and end-to-end backpropagation of global error signals, the proposed module-local, self-supervised greedy InfoMax approach enforces learning of unlabeled data using module-local [InfoNCE loss]( https://arxiv.org/pdf/1807.03748.pdf). Specifically, the InfoNCE loss function is what optimizes mutual information between the input and output of each module in a deep neural network stack. The proposed Greedy InfoMax model has a deep encoding model in every module and an optional autoregressive model in the final module/feature module. The deep encoding model obtains a pair of encodings (*positive sample* and *negative sample* drawn uniformly from all available encoded input sequences) by extracting mutual information between representations of temporally nearby patches, then optimizing the mutual information using [Noise Contrastive Estimation (NCE)]( http://proceedings.mlr.press/v9/gutmann10a/gutmann10a.pdf). Optimization of the encoded pairs in each module occurs as a log-bilinear function (scoring model) with unique weight-matrix for every k-steps-ahead prediction; which leads to the [InfoNCE loss]( https://arxiv.org/pdf/1807.03748.pdf). Optimization extracts features consistent over neighboring patches with the scoring function learning to use the features to correctly classify the matching pair.



> In practice, the loss is trained using stochastic gradient descent with mini-batches drawn from a large dataset of sequences, and negative samples drawn uniformly from all sequences in the mini-batch. Note, that no min-max issues arise as found in adversarial training.


Each encoding module maps the output from previous module to ‘GradientBlock’ to prevent gradient from being transferred from module to module. The ‘GradientBlock’ is also mapped to the autoregressive model that ensures context-aggregate representations at the feature module, without gradient flow from previous modules. 


**Inputs**


	* Input signal



	* Encoded sample pairs (positive and negative from all available encoded input sequences)




	* Optimized output from previous modules (for module M+1)



**Output**


	* Optimized encoded pairs




	* Classified features from the downstream linear classifier



**Assumption**


It is theorized that *slow features* in downstream tasks like speech recognition and object detection is vital in ensuring effectiveness in the maximization of mutual information between representations of neighboring patches. The Greedy InfoMax learning model assumes that natural datasets exhibit *slow features*. 



**Breakthroughs and Validations**



1. Unlike Contrastive Predictive Coding and greedy supervised learning approaches, which use labeled datasets and end-to-end backpropagation of global error signals, the proposed GIM approach mitigates against various disadvantages related to [end-to-end backpropagation] and labeled data sets like vanishing gradients by optimizing inputs as well as predicted outputs of each module using module-local InfoNCE loss, and unlabeled data sets respectively. 



2. The proposed Greedy InfoMax algorithm enforces memory-efficient asynchronous distributed training.


> enables asynchronous, decoupled training of neural networks, allowing for training arbitrarily deep networks on larger-than-memory input data. 




3. The proposed learning approach utilizes greedy self-supervised training, which makes the model less vulnerable to overfitting.

> achieves strong performance on audio and image classification tasks despite greedy self-supervised training.




4. The authors: 



>show that mutual information maximization is especially suited for layer-by-layer greedy optimization, and argue that this reduces the problem of vanishing gradients.




5. In an experiment that compared GIM’s linear classifier accuracy score of its final (frozen module) feature representations against Contrastive Predictive Coding and other supervised, end-to-end training approaches, the authors found that the *Greedy InfoMax* approach outperformed *Randomly initialized* and *MFCC features*,  *Supervised*, and *Greedy Supervised* approaches in the speaker classification accuracy. 


**What to Note**


The autoregressive module aggregates inputs over multiple patches and utilizes [BPTT (Backpropagation Through Time)]( https://en.wikipedia.org/wiki/Backpropagation_through_time) to enable context-aggregated representations. The authors carry out an ablation study to establish the difference in their GIM linear classification accuracies when the autoregressive model is excluded and when BPTT is excluded. The authors note a small decrease in accuracies when the BPTT is excluded and a further decrease when the autoregressive module is excluded entirely; both in speaker and phone classification. 



**Direction for Future Research**


There was a slight disparity in the reported Contrastive Predictive Coding linear classifier accuracy, compared to previously reported accuracy by [Oord, et al.]( https://arxiv.org/pdf/1807.03748.pdf). That calls for more experiments to be conducted with the aim of further validating the proposed GIM’s accuracy against CPC and other supervised, end-to-end backpropagation approaches. 



**Application**


The proposed self-supervised gradient-isolated learning approach is most applicable perceptual and downstream tasks like high-dimension speech recognition as well as high-dimension object detection/classification tasks. 
















