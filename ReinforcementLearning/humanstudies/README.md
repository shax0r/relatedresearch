
# Reinforcement Learning

This folder contains research related to the use of reinforcement learning in research involving human subjects.

## 2019

##  [VISCERAL MACHINES: RISK-AVERSION IN REINFORCEMENT LEARNING WITH INTRINSIC PHYSIOLOGICAL REWARDS](McDuff_Kapoor.pdf)

(note: The pages appear to be backwards in this PDF! I downloaded it twice to try to fix it.  Page 11 is the first page of the article, page 10 is the second page, etc.

### Daniel McDuff and Ashish Kapoor

### Authors

[Daniel McDuff](https://www.microsoft.com/en-us/research/people/damcduff/) - Researcher at Microsoft Research in Redmond, WA

[Ashish Kapoor](https://www.microsoft.com/en-us/research/people/akapoor/) [[Google Scholar]](https://scholar.google.com/citations?user=4D1n8scAAAAJ&hl=en) - Senior Principal Research Manager, Aerial Informatics and Robotics Group (AIR) at Microsoft Research in Redmond, WA

---

The body's autonomic nervous system offers a feedback mechanism for the possible consequences of action choices.  For example, people may become nervous when driving fast around a bend, or when they are near a cliff edge.  These physiological changes are meant to protect oneself from danger.  

This paper uses a novel approach to reinforcement learning that leverages a task-independent intrinsic reward function trained on peripheral pulse measurements that are correlated with human autonomic nervous system responses.

The hypothesis is that these reward functions can improve sample efficiency and mitigate the challenges associated with sparse and skewed rewards in reinforcement learning.

The hypothesis is tested in a simulated driving environment.  

The results show that the reward function used in the simulated driving environment can increase the speed of learning and reduce the number of collisions during the learning stage.

### The human sympathetic nervous system (SNS) as both a survival mechanism and motivator of action

The human autonomic nervous system is composed of the sympathetic and parasympathetic branches.  Of these, the sympathetic nervous system or SNS is known as the "fight-or-flight" response system, as it responds to dangerous situations in order to help mobilize resources to respond to immediate threats.  The SNS regulates the cardiovascular system, adrenal system, and other visceral functions.  When someone is confronted with a threat, their heart rate increases, sweat glands dilate, and energy resources are mobilized to support one's ability to escape from the threat (e.g., a predator or a dangerous situation while driving).  While SNS responses are meant as a survival mechanism, they also help us appraise a situation.  SNS responses can motivate us to act to avoid these types of dangerous and aversive situations.  For example, if you are in traffic and you sense that you might get in an accident, the feeling of your heart rate increasing may help you act faster to reduce your feelings of anxiety.

As such, the signals of the human SNS can be used to model reward mechanisms.  People may act to avoid car accidents, for example, and this type of motivated behavior can provide a reinforcement learning framework that uses reward functions to achieve task-specific goals, and also tries to minimize aversive reactions such as SNS activation and feelings of physiological arousal resulting from feeling in danger, for example.


### Modeling human SNS activation in a reinforcement learning paradigm

> We present a novel approach to reinforcement learning that leverages an artificial network trained on physiological signals correlated with autonomic nervous system responses.

The present study trains an artificial network based on the physiological signals associated with SNS responses in a simulated driving paradigm.  The main challenges of this type of work are a large amount of training data required and the high cost associated with failure cases (e.g., bad accidents that can be expensive to recover from and fatal).  

> While much of the work in RL focuses on mechanisms that are task or goal dependent, it is clear that humans also consider the feedback from the body’s nervous system for action selection. For example, increased arousal can help signal imminent danger or failure to achieve a goal. Such mechanisms in an RL agent could help reduce the sample complexity as the rewards are continually available and could signal success or failure before the end of the episode. Furthermore, these visceral signals provide a warning mechanism that in turn could lead to safer explorations.

Many data points are needed because it is difficult to determine which specific action from a sequence was responsible for a success or failure.  When rewards are sparse, this can make reinforcement learning modeling even more difficult.

### The reward function framework 

The reward function framework used in the present study involves both an intrinsic (i.e., human SNS response) and extrinsic (task-specific -- i.e., good performance on the driving task) component.  Specifically, a weighting parameter is used, lambda, which provides a trade-off between extrinsic motivation (the desire to complete the task) and intrinsic motivation (the desire to experience safety-related physiological responses).  The goal of the framework is to complete the task while minimizing the SNS response.  Low levels of lambda indicate risk-averse behavior (i.e., high intrinsic motivation), while mid-range lambda values lead to optimal behavior in learning and desire to accomplish the task.

### Methods

An autonomous driving scenario was used as the task in this study.  Then a deep neural network, a convolutional neural network or CNN, was trained to predict SNS responses to be used in reinforcement learning.

The SNS signal used was the well-validated photoplethysmographic (PPG) signal to capture the volumetric change in blood in the periphery of the skin.  When someone ie fearful or anxious, their blood volume pulse waveform envelope, as measured by PPG, gets smaller.

Four participants completed the study -- two females and two males -- in which they participated in a simulation, lasting about 20 minutes, in which they drove a vehicle around a maze to find an exit point.

### Results and Discussion

This paper presents a new approach to learning in which the reward function is supplemented with a model directly learned from the human sympathetic nervous system.  The model is incorporated into a reinforcement learning paradigm, and the results indicate that the model can improve both safety and efficiency of learning.  Participants who had used the CNN for the intrinsic reward component performed etter than the heuristic, and the researchers believe that the trained CNN is much richer than distance-based measures.

The authors argue that such a function trained on physiological data can improve learning and reduce dangerous failures that could occur during training.
