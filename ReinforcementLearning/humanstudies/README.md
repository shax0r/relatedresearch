
# Reinforcement Learning

This folder contains research related to the use of reinforcement learning in research involving human subjects.

## 2019

### Daniel McDuff and Ashish Kapoor

[VISCERAL MACHINES: RISK-AVERSION IN REINFORCEMENT LEARNING WITH INTRINSIC PHYSIOLOGICAL REWARDS](McDuff_Kapoor.pdf)

### Authors

[Daniel McDuff](https://www.microsoft.com/en-us/research/people/damcduff/) - Researcher at Microsoft

[Ashish Kapoor](https://www.microsoft.com/en-us/research/people/akapoor/)[Google Scholar](https://scholar.google.com/citations?user=4D1n8scAAAAJ&hl=en) - Senior Principal Research Manager, Aerial Informatics and Robotics Group (AIR) at Microsoft Research Redmond, WA

---
 
 > “Recent developments in cutting-edge live microscopy and image analysis provide an unprecedented opportunity to systematically investigate individual cells’ dynamics and quantify cellular behaviors over an extended period of time. Systematic single-cell analysis of *Caenorhabditis elegans* has led to the highly desired quantitative measurement of cellular behaviors.”

### About [*Caenorhabditis elegans*](https://cbs.umn.edu/cgc/what-c-elegans)

The primitive worm *Caenorhabditis elegans (C. elegans)*, is very small -- only 1 mm long – and has a lifespan of about 2-3 weeks.  However, *C. elegans* shares many essential characteristics with humans in terms of biology, especially as related to development.  *C. elegans* has a nervous system, a brain, exhibits behavior, and can even learn.  *C. elegans*’ processes of embryogenesis, morphogenesis, development, nerve function, behavior and aging are determined by genes which researchers have sought to understood for decades.  The worm’s similarity to humans, and likewise, its great complexity, has made *C. elegans* an attractive target for developmental studies.  Researchers have been interested in how the genetic information stored in *C. elegans* translates to its development.  In 2002, Salk Institute researcher Sydney Brenner, MIT Professor H. Robert Horvitz, and British researcher John E. Sulston were awarded the [Nobel Prize in Physiology or Medicine](https://www.nobelprize.org/prizes/medicine/2002/summary/) for work identifying and analyzing molecular and cellular pathways linked to the development and behavior of *C. elegans*, particularly as related to ”genetic regulation of organ development and programmed cell death.”

### Powerful 3D imaging methods can be used to track *C. elegans* development

Advances in 3D live microscopy and live image analysis have made it possible to record the activity of hundreds to thousands of cells over hours to days of their development.  3D time-lapse imaging can also be used to trace an entire cell lineage, and each cell in the lineage can be quantitatively measured to understand the cells’ developmental activities.

More specifically, corresponding author Zhirong Bao has [sought to determine](https://www.sloankettering.edu/research-areas/labs/zhirong-bao/overview) how the information stored in the genome of *C. elegans* leads to the orchestration of the worm’s development.  As a result of his work, he has developed a lineaging system that uses both 3D time-lapse microscopy and automated image analysis.  The information that is captured by these methods was used in the present study, in which deep reinforcement learning was used to investigate cell movement to come up with several models that can explain various aspects of *C. elegans*’ developmental behavior.

### Why is this research important?

In this paper, Wang and colleagues examine cell movement in the early phases of C. elegans development using the methods developed by Bao, and use deep reinforcement learning to identify patterns in this data.  Based on this rich dataset regarding *C. elegans*' developmental behaviors, Wang and colleagues propose several models that characterize the early developmental behavior of C. elegans.  This work is important as it demonstrates the validity of computational learning methods -- in this case, deep reinforcement learning -- to perform modelling of complex biological data.   The ultimate goal of this work is to model individual cell behaviors with regulatory mechanisms.

> This paper presents a new approach to study cell movement by adopting deep reinforcement learning approaches within an agent-based modeling framework. Deep reinforcement learning is good at dealing with high-dimensional inputs and can optimize complex policies over primitive actions, which naturally aligns with the complex cell movements patterns that occur during *C. elegans* embryogenesis. 

### The Modelling Approach  

The authors used an agent-based modelling (ABM) approach, a powerful approach for the analysis of complex tissues and developmental processes, in which each individual cell is modeled as an agent.  The authors also modeled collective cell migrations.  Deep reinforcement learning was used to train neural networks from 3D time-lapse imaging using information on cell locations, neighbors, and cell-cell interactions gleaned from lineage tracing.  Following training of the neural networks, a feasible and optimal cell migration path is determined and constrained by underlying regulatory networks and the cell's physical environment.

> In our modeling framework, an individual cell is modeled as an agent that contains a variety of information on its fate, size, division time and group information.

Two kinds of individual cell movements were examined -- directional movement (in which a particular pattern of movement is observed) and passive movement (in which no explicit patterns are observed).  Collective cell migrations were also examined and looked at in terms of leading and following cells in the group.


> The neural network takes information from 3D time-lapse images as direct inputs, and the output is the cell’s movement action optimized under a collection of regulatory rules. Since deep reinforcement learning can optimize the cell migration path over considerable temporal and spatial spans in a global perspective, it overcomes the local optimization problem encountered by traditional rule-based, agent-based modeling that uses greedy algorithms.

### Results and Discussion

The model was tested via two representative scenarios that occur very early on in *C. elegans* development/embryogenesis: namely, (1) the anterior movement of [Cpaaa](https://www.wormatlas.org/SulstonembCellLin_1983/SulstonembCellLin1983.html#fig5) (a progenitor cell of *C. elegans*) via intercalation and (2) the rearrangement of the superficial left-right asymmetry.  Each scenario was assigned a different model based on the deep reinforcement learning data.

> Simulation results indicated that Cpaaa experienced an active directional movement towards the anterior, which is caused by the continuous effects from a longer distance, rather than a passive process in which it is squeezed to the target location by its neighbors’ movements.

> In the second scenario, the frequently occurring ‘leader-follower’ mechanism was also supported by the simulation results of the asymmetry rearrangement.

### How this research relates to Emergent

This work demonstrates the use of neural networks powered by deep reinforcement learning to model the movements of *C. elegans*.  Thanks to the richness of data being collected using 3D imaging in this organism, artificial intelligence concepts are being applied and finding useful patterns that can be used to create new developmental models for *C. elegans.*
