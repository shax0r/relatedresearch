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






---------------------------------------

# Unsupervised Word Embeddings Capture Latent Knowledge from Materials Science Literature

-----------------------------------



### Tshitoyan, et al.,


### 2019,


### Authors 


[Vahe Tshitoyan]( https://www.mathworks.com/matlabcentral/profile/authors/4173395-vahe-tshitoyan)



[John Dagdelen](https://chemistrycommunity.nature.com/users/64392-john-dagdelen)



[Leigh Weston]( http://www.physics.usyd.edu.au/cmt/home.php?x=leigh)




[Alexander Dunn]( https://cheme.stanford.edu/people/alexander-dunn)




[Ziqin Rong](https://publons.com/researcher/2090364/ziqin-rong/)





[Olga Kononova]( http://faculty.uml.edu/vbarsegov/people/kononova/kononova.html)



[Kristin A. Persson]( https://mse.berkeley.edu/people_new/persson/)

[Gerbrand Ceder]( https://dmse.mit.edu/people/gerbrand-ceder)



[Anubhav Jain]( https://eta.lbl.gov/people/anubhav-jain)

[Unsupervised Word Embeddings Capture Latent Knowledge from Materials Science Literature](AutonomousResearch/Tshitoyan, et al-2019, Unsupervised word Embeddings.pdf)



Retrieving scientific information from today’s vast amount of scientific publications is becoming difficult if not cumbersome as the number of publications continue to grow. Unlike previous studies that have demonstrated the retrieval of information from scientific literature using supervised [natural language processing]( https://en.wikipedia.org/wiki/Natural_language_processing), [Tshitoyan]( https://www.mathworks.com/matlabcentral/profile/authors/4173395-vahe-tshitoyan) et al., in their article, prove how materials science knowledge in published literature can efficiently be encoded as *information-dense word embeddings* without human supervision or cumbersome labeling. The authors use previously reported unsupervised natural language processing (**NLP**) models/algorithms (Word2Vec and GloVe) to train word embeddings in materials science with the aim of proving the efficiency of the models in capturing key knowledge. Particularly, **NLP** models like Word2Vec’s [Skip-gram Variation]( https://en.wikipedia.org/wiki/Word2vec) use information about the co-occurrences of words in a text corpus to create word embeddings (vector representations of words).  The authors created a text corpus by collecting and processing about 3.3 million scientific abstracts from over 1000 journal published between 1922 and 2018. In particular, the authors used skip-gram variation of [Word2vec]( https://en.wikipedia.org/wiki/Word2vec) to learn the *200-dimesional embedding* of the target word (*thermoelectric*) to their 500, 000 words text corpus. The Word2vec model expresses and solve analogies by finding the cosine distance of similarity between embeddings through *addition* and subtraction vector operations. In addition, the model uses the [dot product]( https://mathinsight.org/dot_product) (projection vector operation) to find/predict similar words/compounds. 



> To better visualize such embedded relationships, we projected the embeddings of Zr, Cr and Ni, as well as their corresponding oxides and crystal structures, onto two dimensions using principal component analysis.



**Inputs**


-Text corpus (scientific abstracts, which resulted in approximately 500, 000 key words)



-**NLP** model/algorithm (Word2vec, GloVe, ELMo, BERT e.t.c.)



**Output**


200-dimensional embedding of the target word (e.g., thermoelectric, photovoltaics, topological insulator, ferroelectric, e.t.c. )



**Breakthroughs and Validations**


+ The authors observed that the created embeddings supported domain-specific analogies of the target word. Specifically, the authors were able to validate previous findings regarding Word2vec by establishing that the accuracies in representing information in three categories: functional application, crystal symmetries as well as chemical composition were close to 50%, as reported in the previous [Word2vec study]( https://arxiv.org/abs/1310.4546). 


+ The authors established that the embeddings of chemical elements were representative of their positions in the periodic table when projected onto two dimensions. That means that the embeddings could serve as effective feature vectors in quantitative machine learning models like formation energy prediction, thus, outperforming several previously reported curated feature vectors.


>We stress that Word2vec treats these entities simply as strings, and no chemical interpretation is explicitly provided to the model; rather, materials knowledge is captured through the positions of the words in scientific abstracts.


+ The main advantage of the demonstrated representation is that application keywords such as ‘thermoelectric’ had the same representation as material formulae such as ‘Bi2Te3’.


+ The authors found that a number of materials that had relatively high cosine similarities to the word ‘thermoelectric’ never occurred explicitly in the same abstract with the target word: ‘thermoelectric’, or any other word that unequivocally identify materials as thermoelectric. As a result, the authors were prompted to investigate if such instances could be usefully interpreted as predictions of primer thermoelectric materials.


+ The authors identified compounds mentioned their text corpus (abstracts) more than three times that were also present in the computational datasets reporting the thermoelectric power factors of approximately 48,000 compounds calculated using [density functional theory (DFT)]( https://en.wikipedia.org/wiki/Density_functional_theory). 


+ From the 48, 000 compounds,  9,483 compounds were found to overlap between the two datasets, of which 7,663 never occurred alongside thermoelectric keywords the sampled text corpus, which mean they could be considered candidates for prediction. The authors ranked each of the 7,663 compounds by the dot product of their normalized output embedding with the word embedding of ‘thermoelectric.’


> This ranking can be interpreted as the likelihood that that material will co-occur with the word ‘thermoelectric’ in a scientific abstract despite this never occurring explicitly in the text corpus.


+ After plotting the distributions of DFT maximum power factors values for all the overlapping compounds; 9,483 compounds, the authors found that the top ten predictions all exhibit computed power factors significantly greater than the average of candidate materials, and even slightly higher than the average of known thermoelectric materials. 


+ One notable novelty about the created embeddings is that the embeddings were based only on the text corpus and were not modified or trained in any manner using the DFT data.


+ After comparing relative ranking of candidates using Spearman rank correlation for 83 materials that appear both in the sampled text corpus and the experimental set, the authors obtained a 52% and 59% rank correlation of experimental results with the embedding-based ranking for maximum zT  and maximum power factor, respectively. The research model outperformed DFT dataset of power factors, which exhibited only a 31% rank correlation with the experimental maximum power factors.


+ The authors used historical dataset to test whether their model—if trained at various instances in the past—would have correctly predicted thermoelectric materials reported later in the literature. Results indicated that materials from top 50 word embedding-based predictions were on average eight times more probable to have been studied as thermoelectrics within the next 5 years compared to a randomly selected unstudied material from sample corpus at that time, and also three times more probable than a random materials with non-zero DFT bandgap.



> The use of larger corpora that incorporate data from more recent years improved the rate of successful predictions, as indicated by the steeper gradients for later years.


+ After investigating a series of connections that could lead to predictions of materials never mentioned next to the key word; thermoelectric, the authors found that the correlations between key words led to predictions. The authors note that multiple predictions exhibited promising properties despite not being in any well-known thermoelectric material categories, thus, demonstrating that word embeddings go beyond trivial structural or compositional similarities and have the potential to present explicit knowledge not directly accessible to human scientists.


> This direct interpretability is a major advantage over many other machine learning methods for materials discovery.


+ Finally, the authors investigated the generalizability of their research model using different target words, besides ‘themoelectric’ and found similar results.



**Assumptions/What to look out for**



> The success of our unsupervised approach can partly be attributed to the choice of the training corpus.


The above statement means that the quality and domain-specificity of sampled corpus determines the utility of embeddings for domain-specific tasks.



The research model assumes that words with similar meanings often appear in similar contexts, which follows that their corresponding embeddings will also be similar.


Some of the model’s predicted compounds, in materials science might have toxic elements, which calls for discretion while embracing or validating machine-assisted scientific breakthroughs. 



**Future Research Direction**


The methodology described in the article can be generalized to other language models, such that the probability of a material or molecule co-occurring with words that represent a property or a target application can be treated as indicators of performance. As a result, such language-based inference methods can become new direction for research at the intersection between science and natural language processing. 


Future research should sample full texts as sample text corpus to test representation of more negative relationships and in general more complex sentences and variables that will require more powerful methods.


Future research should substitute Word2vec with powerful context-aware embeddings such as ELMo or BERT25, which could lead to improvements for functional material predictions. 
.


**Application**


The presented work is a novel contribution towards developing and validating accurate NLP models that can be applied in the automatic exploration of hypothesis spaces (Automated Research).


> …this work will pave the way towards making the vast amount of information found in scientific literature accessible to individuals in ways that enable a new paradigm of machine-assisted scientific breakthroughs.
