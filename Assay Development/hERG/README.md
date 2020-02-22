### Negatives of QSAR Modeling in hERG

#### What is hERG? [source](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC4593700/)

The human ether-à-go-go related gene (hERG) encodes the subunit of a delayed rectifier voltage-gated K+ channel. These channels are expressed in a wide array of tissues, but their physiological function is best characterized in cardiac cells.  In heart cells, these channels are important in repolarization of the cardiac action potential.  Reduced function of hERG channels lengthens the QT interval, a measure of the duration of ventricular depolarization and repolarization in an electrocardiogram. QT interval prolongation can evolve into a lethal cardiac arrhythmia. Many drugs covering a broad spectrum of pharmaceutical classes have been withdrawn from the market or have had their usage limited due to blockage of the hERG.  hERG is known to interact with these drugs, which results in cardiotoxic effects, because of hERG’s notorious ligand promiscuity, mainly due to its large hydrophobic intracellular binding pocket and its multiple states (open, inactive, and closed).

There are a variety of in vitro hERG assays, ranging from high throughput binding assays to time-consuming patch clamp electrophysiology measurements.

### What is QSAR modeling? [source](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC4074254/), [source](https://ntp.niehs.nih.gov/iccvam/meetings/commprac-2016/tropsha-508.pdf)
Quantitative Structure-Activity Relationship or QSAR modeling is a type of regression or classification modeling.  The goal of QSAR is to relate a set of predictor variables to a response variable.  In regression QSAR, the predictor variables are related to the potency of the response variable.  In categorical QSAR, the predictor variables are related to the categorical value of the response variable.  QSAR is widely used in drug discovery to model how different compounds would interact and, for example, whether toxicity would result.  QSAR can be used to model the interaction of the hERG receptor with various candidate heart drugs to check for cardiotoxicity, which can serve as a way to reduce risk in drug discovery and save time and money for pharma companies.
The predictors typically consist of physico-chemical properties or theoretical molecular descriptors of chemicals.  QSAR models first summarize a supposed relationship between chemical structures and biological activity in a data-set of chemicals. Second, QSAR models predict the activities of new chemicals.

Relevant to hERGs and cardiotoxicity, QSAR can be used to predict a given chemical response of various drugs.  QSAR studies can also reduce animal experimentation during preclinical drug development which is why global authoritative bodies such as the US EPA and others have proposed QSAR as an alternative to in vivo experiments.

### What are the downsides of QSAR modeling for hERG? [source](https://www.sciencedirect.com/science/article/pii/S1359644617304762?via%3Dihub)
  
-	Arcane descriptors can affect the results of biological activity prediction or classification
-	Redundancy and overfitting in QSAR studies can make prediction and/or classification unreliable
-	In neural network based QSAR-based high throughput virtual screening approaches (HTVS), thousands of molecules and descriptors inevitably lead to the selection of networks with more than one hidden layer and many nodes in each layer.
-	In neural network QSAR models, models can get stuck in local minima and become vulnerable to overfitting

### FLAWS IN STUDIES USING DEEP LEARNING/NEURAL NETWORK (NN) ALGORITHMS IN CHEMOINFORMATICS

Briefly, the flaws include redundancy, overfitting, and having thousands of ligands.  There is an emphasis on data dependency and data quality.

#### DATA QUALITY AND DEPENDENCY

Data must be high quality to make predictions.  As the famous saying in computer science goes, "garbage in, garbage out."  If the input data is of poor quality, the predictions will be wrong.  Other common errors relating to data include:

-	Failure to take account of data heterogeneity
-	Use of inappropriate endpoint data
-	Use of collinear descriptors
-	Use of incomprehensible descriptors
-	Error in descriptor values
-	Poor transferability of QSAR/QSPR
-	Inadequate/undefined applicability domain
-	Unacknowledged omission of data points
-	Use of inadequate data
-	Replication of compounds in dataset
-	Too narrow a range of endpoint values
-	Over-fitting of data
-	Use of excessive numbers of descriptors in a QSAR/QSPR
-	Lack of/inadequate statistics
-	Incorrect calculation
-	Lack of descriptor auto-scaling
-	Misuse/misrepresentation of statistics
-	No consideration of distribution of residuals
-	Inadequate training/test set selection
-	Failure to validate a QSAR/QSPR correctly
-	Lack of mechanistic interpretation

#### SOLUTIONS FOR DATA QUALITY/DEPENDENCY

Rapid accumulation of data highlights the need for data curation - accurate datasets should be used for modeling.

####	REDUNDANCY AND GETTING STUCK IN LOCAL MINIMA 

- Existence of thousands of descriptors, as well as the correlation between them, leads to redundancy problems and, inevitably, ‘getting stuck’ in local minima. By contrast, various unknown descriptors exist that affect the results of QSAR models. Thus, feature selection algorithms have been suggested for reducing the number of descriptors.

- Redundancy negatively affects network efficiency and can originate from duplicate input data, or when some of the input variables of the network are repeated in the input variable.
-	In QSAR, redundancy refers to the similarity and correlation between descriptors.

#### SOLUTIONS TO REDUNDANCY

Solutions to Redundancy and Getting Stuck in local minima include (1) manual descriptor selection and (2) using data-mining techniques to extract the best features of descriptors as variables for network input.  These models are called hybrid models and have an unsupervised step, based on the molecular descriptors, and a supervised step via NNs, which is based on both descriptors and the biological activities.

#### OVERFITTING 

It is difficult to apply optimized essential network parameters to obtain the best prediction without overfitting. To avoid this issue, various regularization learning techniques have been proposed (e.g., ReLU and dropout in DL algorithms, and Bayesian methods in shallow NNs).

#### SOLUTIONS TO OVERFITTING

To combat overfitting, one can use (1) the simplest network structure, universal approximation theorem, based on the one hidden layer and the few neurons in the hidden layer; and (2) various learning approaches such as back propagation (BP), radial basis function NN (RBFN), and counter propagation (CP).

#### THOUSANDS OF LIGANDS 

Having thousands of ligands requires a computational model with a large number of elements.  

#### SOLUTIONS TO THOUSANDS OF LIGANDS 

That’s why QSAR focuses on finding the best model based on deep architecture to avoid getting stuck in local minima and being prone to overfitting.  DL algorithms are naturally complex and time-consuming, though, and so GPU or CPU clusters must be used in a parallel procedure.  Data mining to reduce molecule features can also help reduce redundancy.

Neural networks appear more suitable than deep learning, but both NNs and DLs have a role in the future of drug discovery, and combined approaches may be the most effective in the search for the best drug candidates from libraries with large numbers of biochemical compounds.
