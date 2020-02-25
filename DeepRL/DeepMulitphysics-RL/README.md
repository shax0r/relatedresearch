
---------------------------------------------------------------------------------------------------------------------
# Deep multiphysics: Coupling discrete multiphysics with machine learning to attain self-learning in-silico models replicating human physiology

-----------------------------------------------------------------------------------------------------



### 2019,




### Author




[Alessio Alexiadis](https://www.birmingham.ac.uk/staff/profiles/chemical-engineering/alessio-alexiadis.aspx)






[Deep multiphysics: Coupling discrete multiphysics with machine learning to attain self-learning in-silico models replicating human physiology](DeepRL/DeepMulitphysics-RL/Alexiadis_2019.pdf)




**Proposed Approach**



In-silico modeling of biological systems/human physiology is key to solving physical science problems in medicine. [Alexiadis]( https://www.birmingham.ac.uk/staff/profiles/chemical-engineering/alessio-alexiadis.aspx), in his article, proposes a novel methodology combining Discrete Multi-physics (DMP) and Reinforcement Learning (Q-learning) to device a self-learning in-silico model replicating Autonomic Nervous System (ANS)-regulated human physiological processes. The author demonstrates how possible and efficient it is to model ANS-regulated human physiological activities using [Discrete Multi-physics](), coupled in parallel with Reinforcement Learning algorithm. Particularly, Discrete Multi-physics, unlike traditional [multi-physics]( https://en.wikipedia.org/wiki/Multiphysics), leverages on a combination of particle techniques like Discrete Element Method and Lattice-Spring Model to compute and model solid/liquid particle behaviors. Specifically, the author models the peristalsis activity of the human oesophagus using DMP: the [Lattice Spring Model (LSM)]( https://link.springer.com/article/10.1007/s11242-012-9955-6) for the oesophagus and the [Discrete Element Model (DEM)]( https://www.sciencedirect.com/topics/materials-science/discrete-element-method) for the interaction between the tube and the bolus.


The author divides the membrane/wall of a flexible tube (representing an oesophagus tract) into 480 computational particles of mass *m* and then links each of the particles with a computational neuron. The 480 particles are divided into 20 ‘slices’ with 24 particles each. The author then links each of the computational particles to an equilibrium point using a tethered spring. The equilibrium positions of the tethered springs are arranged in a cylindrical manner to represent the flexible tube at zero stress conditions. 
According to the author, when the tube-particle, immediately under the bolus, is displaced from its equilibrium, the spring reacts with a [Hookean force]( https://en.wikipedia.org/wiki/Hooke%27s_law) that opposes displacement *x* and is proportional to the spring stiffness. In the case where the bolus is larger than the tube’s diameter, the tube deforms and reacts with a radial elastic force pointing towards the tube’s axis. The author modeled oesophagus contractions by adding radial forces (acting in the radial direction and pointing towards the tube’s axis) acting on the membrane particles. The applied forces are equally distributed to all particles in the same slice, at a given axial position. The tube’s computational particles interact with the central particle by Hertzian contact force consisting of normal contact force. 


With the DMP particles constituting the initial state (position of the bolus in the tube), they act as sensory neurons by feeling bolus pressure. The particle/neuron ring at an estimated center of the bolus fires-up and its state transitions to *s=1* at time *t*. At that point, the Reinforcement Learning framework establishes the action vector, first using the exploratory approach, then using a greedy approach at later simulation runs. In the article, the author used [Q-learning]( https://en.wikipedia.org/wiki/Q-learning) where the maximum Quality action matrix is populated from zero by solving the [Bellman equation](https://en.wikipedia.org/wiki/Bellman_equation), which determines the optimal reward through comparative recursive simulation runs. Once the RL framework establishes ‘quality action,’ the DMP implements it as a muscle contraction (Hookean force and Radial elastic force). Muscle contraction (action) changes the bolus position within the tube, from which displacement is calculated and reward determined. Notably, simulation of a single time step repeats many times to obtain the best action/reward before evolving to the next time step. 


**Input**


-	Particles associated with neurons




-	Spherical central mass/bolus



-	A flexible tube with smooth muscle membrane




-	Applied forces: Hertzian contact force consisting of normal contact force





**Intermediaries**



•	Reinforcement Learning Framework e.g. Q-Learning




•	Reactionary forces: Hookean force (tethered Spring) and Radial elastic force (flexible tube)





**Output**



-	A shift in bolus position/displacement




**Novelty/Validations**



-	The DMP-RL hybrid method mimics the human Autonomic Nervous System feedback loop as close as possible by associating each membrane particle with a computational neuron (**Parallel coupling**). The particle-neuron duality allows **Reinforcement Learning** to train the computational neurons as simulation progresses, unlike preliminary approaches where training is in series. 



- As highlighted in the article, the proposed model is the first to couple multiphysics and machine learning in parallel rather than in series. The parallel integration reduces the bulkiness of the system by presenting the model as a hybrid model with combined components and not two separate models (First-principles model + Machine learning)




- The author sufficiently validated his hybrid DMP-RL approach using the well-known and simple peristalsis in the oesophagus. After comparing the ‘human policy’ and the policy derived by RL, the author not only observed that the bolus advanced 5% further with ‘machine policy’ than ‘human policy,’ but also that the machine learns by itself to propagate the bolus. 




**Assumptions**


-The Hertzian contact forces describing interaction of both the membrane particles and the central bolus particle does not account for gravitational force that may way in during collision. In that case, the DMP model assumes that gravitational forces insignificantly influence particle interactions.



-Also, the Discrete Element Method particle technique, which is part of the DMP model, does not account for tangential forces.



-Simulation of a single time step repeats many times to obtain the best policy/action/reward before evolving to the next time step.




**Direction for Future Research**


- Future research work can integrate the proposed DMP model, at a deeper level, with deep reinforcement learning algorithms to determine efficiency. 


- Also, future work can test the proposed model using even more complex human physiological feedback loops like blood clotting in the human cardiovascular system. 



**Application**



The proposed approach can act as a general methodology of modeling and optimizing human/animal physiological processes facilitated by Autonomic Nervous Systems. That is particularly applicable in resolving Autonomic Nervous System-related breakdowns/problems in medicine.

