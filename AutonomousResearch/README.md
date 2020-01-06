# Autonomous Research

This folder contains research related to the use of autonomous agents in experimental research.

## 2019

### Coley et al.

[Autonomous Discovery Part I](Coley_2019.pdf)

[Autonomous Discovery Part II](Coley_2019_PartII.pdf)

### Authors
[Connor W. Coley](http://cwcoley.com/) (B.S., Caltech; Ph.D., MIT; currently Assistant Professor of Chemical Engineering at MIT)

[Natalie S. Eyke](http://greengroup.mit.edu/natalie-eyke) (B.S., University of Michigan; working on Ph.D. at MIT)

[Klavs F. Jensen](https://jensenlab.mit.edu/) (Professor, Chemical Engineering, MIT)

> “We should embrace the divergence of human versus machine tasks.”
 
Data Science and machine learning can be used to automate chemical science experiments to both reduce subjectivity and speed up the process of drug discovery.  The inputs in such automation can be, for example, a given drug or model; correspondingly, the outputs can be the drug’s performance on chemical assays, or the model’s predictive performance.  
As scientists seek to speed up the synthesis and testing of candidate drugs, automatable experiments have emerged as a new method of drug discovery in the chemical sciences.  This research is important because human-guided drug discovery research is exceptionally slow and prone to errors, and though a computer model cannot identify a good therapeutic, automation can speed up certain aspects of drug discovery and help hone in on more promising candidate drugs (e.g., those which exhibit strong activity on a number of predetermined assays).  An automated discovery step which seeks to identify promising compounds can save a lot of time and money for researchers and companies -- not to mention shed light on new drugs which human scientists either did not have time to test or did not consider for testing.

This paper reflects on a selection of studies (summarized in Table 1) that focus on the discovery of physical matter or processes rather than models.  These studies exemplify the strengths of automated discovery, and offer guidance on how to surmount major challenges that remain.  Namely, future directions in automated experiments should seek to improve the ability to work with complex data, build empirical models, automate both physical and computational experiments for validation, select experiments, and help determine whether we are progressing toward the ultimate goal of autonomous discovery.

#### The authors provide a framework for autonomous discovery by considering the following questions:

##### 1.	How broadly is the goal defined?

This can be a lofty goal in autonomous discovery -- it’s not possible to request that the autonomous discovery process identify a good therapeutic, come up with an interesting material or a new reaction, or propose an interesting model.  As a result, the goal of discovery is narrowly defined in most studies – for example, an expert defines a specific scalar performance objective that an algorithm seeks to optimize (e.g., finding strong activity for any of 20,000 compounds in any of 177 assays).

##### 2.	How constrained is the search/design space?

The search space for automated discovery can vary greatly.  Human input is required for this step, and some studies have constrained the search space to a greater degree than required for automated validation experiments.

##### 3.	How are experiments for validation/feedback selected?

The field of autonomous discovery has excelled in experiment selection.  Many frameworks exist for quantifying the value of an experiment in a model-guided design.  Model-free experiment selection also exists, but requires more human intervention from domain experts.  

##### 4.	How superior to a brute force search is navigation of the design space?

Computer-assisted experiment selection’s benefits include the ability to conduct a brute force search (usually not prohibitively expensive with a sufficiently small design space, but an ill-defined endeavor with larger design spaces).

##### 5.	How are experiments for validation/feedback performed?

Experiments for validation/feedback are performed in a manner relating to the nature of the design space and whether the experiments are physical or computational.

##### 6.	How are results organized and interpreted?

Organization and interpretation of results can be achieved computationally for iterative workflows (e.g., workflows that proceed through several iterations of batched experiments).  There is no benefit for automated organization and interpretation for non-iterative workflows for manual validation.

##### 7.	Does the discovery outcome contribute to broader scientific knowledge?

While a lofty goal, it is important that autonomous discovery studies do, indeed, advance the field and contribute to the greater body of scientific knowledge.  The studies listed in Table 1 focus on discovery campaigns with a primary outcome of identifying a molecule, material, or set of process conditions that achieve or optimize a human-defined performance objective.  Autonomous discovery can be used to specify a high-level goal (e.g., find compounds that react strongly in a given set of assays) to receive human-interpretable, generalized conclusions that can advance the drug discovery process.  This reduces the mental burden for humans and speeds up the process.

Human intervention is required, of course, to impose constraints on design spaces so that unproductive exploration can be avoided.  Widening the design space risks making the experiments non-automatable.  
As the paper notes, public databases of chemical structures, biological data, chemical reactions, molecular properties, materials, and journal articles (such as those listed in Table 2) can be used to facilitate autonomous discovery in the chemical sciences.

### The authors define the following outstanding challenges in this field:

##### 1.	Working with complex data 

> “The discovery of complex phenomena requires a tight connection between knowledge and data.”  

Complex data – as opposed to “Big Data” -- refers to both the size or volume of data, and its content.  Complex data is used to reflect the idea that it would be impossible for a human to identify the same conclusions or relationships as an algorithm – either due to dataset size, lack of structure, or dimensionality.  

> “We intentionally use “complex data” rather than “big data”–the latter generally refers only to the size or volume of data, and not its content. Here, we mean “complex data” when it would be difficult or impossible for a human to identify the same relationships or conclusions as an algorithm. This may be due to the size of the dataset (e.g., millions of bioactivity measurements), the lack of structure (e.g., journal articles), or the dimensionality (e.g., a regression of multidimensional process parameters).”

Virtually any dataset of (input, output) pairs describing a performance metric of a molecule, material, or process can serve as the basis for supervised learning of a surrogate model.  Unsupervised techniques can be used to infer the structure of complex data sets, forming the basis of deep generative models that propose new physical matter.

Many studies rely on open access datasets to facilitate discovery.  The authors of this paper propose that a challenge in this field should be the establishment of open access databases with standardized data representations.  Existing data may not contain all of the information needed for a given task, or data may even be missing or misentered.  Data curation should be a priority in maintaining such open-access databases.

Other studies seek to build empirical models from raw data.  Machine learning has been highly influential here, and is now the go-to “for developing empirical models that describe nonlinear structure-function relationships to estimate the properties of new physical matter and serve as surrogate models for expensive calculations or experiments.”  Many tools now exist to streamline model training and deployment, though adoption of these tools has been met with mixed success.  A challenge in this regard, as identified by the paper’s authors, is to improve representations of molecules and materials.  This requires a better understanding of why different techniques work well in different settings, as well as a need for techniques to better capture relevant information about input structures (or validated on or extended to situations for which only limited information or examples are available).

Other challenges in this domain include the incorporation of physical invariance and equivariance properties; unification and use of heterogeneous datasets; and improvement of interpretability of machine learning models.  

##### 2.	Automating validation and feedback 

Many discoveries can be validated through computational means alone.  Iterating between hypothesis generation and validation, which can be easily achieved via computational means, can be fundamentally helpful to the discovery process.  Bad predictions can be quickly corrected to improve the hypothesis.  Automation of small-scale screening, synthesis, and characterization, which enables validation via physical experiments, have helped pave the way for automated validation and feedback mechanisms.  Software advancements have improved computational validation, making it faster and more robust, as well.

The authors, also, call for the expansion of the scope of automatable experiments, facilitation of integration through systems engineering, and automation of the planning of multistep chemical syntheses (e.g., for the particularly challenging on-demand synthesis class of experiments).  Figure 2 shows a workflow for automated synthesis, purification, and testing which requires the scheduling of many different operations handled by different hardware and software.

Automated validation remains costly, though it is often used as a proxy for more expensive evaluations.  The proxy and true metric must be aligned.  Also, for maximum benefit, the newly acquired data should be compared to previous data in the literature.

##### 3.	Selecting experiments

Challenges in experiment selection include the quantification of model uncertainty and the domain of applicability of models.  Experiment selection criteria should be able to account for the difficulty of an experiment in a quantitative way.  Discovery goals should be high-level, broad objectives.  Figure 4 of the paper provides an overview of knowledge discovery from databases.

Strategies for choosing molecules and materials for validation in discovery workflows are important.  Generative models can be useful for designing molecules on-the-fly with minimal human input, informed by knowledge of the chemical space in which the models are trained.  Figure 5 shows some typical ways to select molecules to fulfill design objectives, and Figure 6 discusses a timeline of generative model development.

##### 4.	Evaluation

Computer-aided discovery must extrapolate beyond what is known.  Design-make-test must be demonstrated beyond proof-of-concept in a limited chemical space.

Currently, there are no unified strategies for the use of existing data and the acquisition of new data for discovering functional physical matter, processes, or models.  Benchmarks would make the evaluation step easier, and would encourage method development and improvement.

### Conclusions

Computer assistance and automation have become ubiquitous in accelerating scientific discovery by improving throughput and reducing manual effort.  Very few studies have achieved a high level of autonomy, however, and the search space definition for autonomous discovery requires significant human input.
At the current moment, it remains unclear to what extent the computer is doing the discovery or simply serving as a tool to accelerate human discovery.  The human developer’s role is still significant -- to formulate the discovery problem, an effective representation, and transform the output into meaningful scientific results.  The paper touts the promise of computer-aided or autonomous discovery while discussing the many remaining challenges in this field.  Public and private sector efforts have significant investments in this type of discovery and the field is poised to be part of a larger revolution in automation of scientific discovery.

This work relates to Emergent.Bio as the company seeks to predict markers by querying markers rather than behaviors.  An empirical computer engine could run experiments and simulations (based on public information available from drug discovery databases, for example) and crunch the numbers to yield novel insights and advance the field.  This work could occur in conjunction with research labs (e.g., with Professors Coley or Jensen, who are authors on this article and also MIT Chemical Engineering professors) to speed up drug discovery and help accelerate drug discovery. 
