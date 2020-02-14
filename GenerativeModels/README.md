Generative Models
=====

This folder contains research related to the use of generative models in AI.

## 2019
---

### Jin et al.

- [Junction Tree Variational Autoencoder for Molecular Graph Generation](Jin_2019.pdf)

   <a href="http://www.youtube.com/watch?feature=player_embedded&v=QFRv_lOWeKI
" target="_blank"><img src="http://img.youtube.com/vi/QFRv_lOWeKI/0.jpg" 
alt="Molecular Graph Generation using Junction Tree VAE" width="240" height="180" border="10" /></a>
   [Barzilay](https://people.csail.mit.edu/regina/) and [Jaakkola](http://people.csail.mit.edu/tommi/) paired up with [Wengong Jin](http://people.csail.mit.edu/wengong/) to demonstrate the use of variational [autoencoders](https://en.wikipedia.org/wiki/Autoencoder) (VAE) to generate novel molecules by integrating a graph convolution network with the molecule's [junction tree decomposition](https://en.wikipedia.org/wiki/Tree_decomposition). The generation of something like chemical properties is relatively easy using something like Google's [Transformer](https://arxiv.org/abs/1706.03762), but the generation of molecules requires some more work. Jin provides a robust framework for approaching generation of novel discoveries from data space.
   - **Inputs:** SMILES Data
   - **Intermediaries:**
   Graph Convolution, Junction Tree Encoding
   - **Outputs:** SMILES Predictions
   > JT-VAE outperforms previous
models in molecule reconstruction, and always produces
valid molecules when sampled from prior distribution

### Born, et al.

   This research contributes towards enhancing the efficacy of candidate anticancer drug compounds by ensuring their desired chemical properties are specifically tailored to the specific cellular environment or gene expression profile of a tumor cell that the compounds intend to act. The research presents a deep RL-based model for anticancer molecule generation that, for the first time, enables the generation of novel anticancer compounds while taking into account the disease context, which is encoded in the specific gene expression profile (GEP) of a tumor cell. The research demonstrates the possibility of optimizing, using RL optimizing framework, the proposed anti-cancer compound generative model to produce candidate compounds with high predicted efficacy (IC50-the micromolar concentration necessary to inhibit 50% of the cells in a sample) against a given target GEP. 

   The proposed model is reported to have a capacity of proposing novel molecular structures from a chemical space of about 1030 to 1060 molecules. The research successfully validated an estimated 96.2 percent of the generated molecules. 
   - **Inputs:** RNA-Sequence gene expression profiles from cancerous and healthy human tissues ([transcriptomic data](https://www.ncbi.nlm.nih.gov/pubmed/20972753)), test and train molecular datasets from credible databases, IC50 drug sensitivity data, as well as bioactive drug-like molecular data. 
   - **Outputs:** Generated molecular structures, Morgan fingerprints (ECFP) of the generated molecules, and a candidate compound. 
   - **Significant Structure:** The most crucial elements of the presented research model is a conditional generator framework, which entails a bio molecular profile VAE (PVAE) and a sequential compound generator VAE (SVAE), an RL optimization framework, Tanimoto similarity model, and a multimodal IC50 prediction model (PaccMann). 

   This research significantly relates to the overall mission of Emergent Dynamics, Inc., as it develops efficacy curative solutions through deep generative models for Biomedicine. An optimized generative model can design effective drugs closely following cell tissue adaptive sequences and bioactive small molecular structural patterns. The research demonstrates the development of an effective anticancer drug design model through reinforcement learning.
   
   
   
   
   
   
   
 
_____________________________________________________________________________________

# GRAPHAF: A FLOW-BASED AUTOREGRESSIVE MODEL FOR MOLECULAR GRAPH GENERATION


-------------------------------------------------------------------------------------------------------------------------------


### 2020,



### Authors



[Chence Shi]( https://chenceshi.com/)



[Minkai Xu]( https://minkaixu.com/)



[Zhaocheng Zhu]( https://mila.quebec/en/person/zhaocheng-zhu/)


[Weinan Zhang]( http://jhc.sjtu.edu.cn/people/members/faculty/weinan-zhang.html)




[Ming Zhang]( http://net.pku.edu.cn/dlib/mzhang/)




[Jian Tang]( https://www.cifar.ca/bio/jian-tang)





[GRAPHAF: A FLOW-BASED AUTOREGRESSIVE MODEL FOR MOLECULAR GRAPH GENERATION](GenerativeModels/Shi, et al._2020.pdf)



	*Model Overview*



   Multiple models including [Junction Tree Variational Autoencoders (JT-VAE)]( https://www.youtube.com/watch?v=QFRv_lOWeKI), [Graph Convolutional Policy Network(GCPN)]( https://arxiv.org/abs/1806.02473), [MolecularRNN (MRNN)]( https://arxiv.org/abs/1905.13372), [Graph Normalizing Flows (GNF)]( https://arxiv.org/abs/1905.13177), as well as [GraphNVP]( https://arxiv.org/abs/1905.11600) have been developed to generate valid molecular structures applicable in material science and drug discovery. These models fall under multiple approaches including flow-based approaches, VAE-based approaches and/or autoregressive-based approaches. Flow-based approaches work by defining invertible transformations between latent base distributions like the Gaussian distribution and high-dimension observable data such as speech and images. On the other hand, autoregressive based approaches like MRNN and GCPN formulate molecular graph generation as sequential decision processes that aim at dynamically generating edges and nodes based on exiting graph sub-structures in the latent space. All deep generative models act by sampling and/or training. Shi et, al., in their journal article, propose a novel deep generative model that leverages on both flow- and autoregressive-based approaches to generate valid molecular structures with optimized properties. The proposed model, known as GraphAF (Graph Autoregressive Flows) builds on previous models’ (GCPN and MRNN) mechanisms where a molecular graph generation task is formalized as a sequential decision process. 




   Two key processes of normalizing flows in generative models entail: computing data likelihood/density by inverting a transformation of a given datapoint, and sampling variables from, first, a base distribution and then performing a feedforward transformation by masking input molecule graph sub-structure and output latent variable. Given **n** number of nodes, **d** node types, **b** edge types and **D** dimension of observation data, the autoregressive conditional probabilities can be parametized as Gaussian distributions with unconstrained and positive scalar functions of, first, the first sampled variable from a base distribution, and then subsequent variables in sequential steps. The GraphAF model generate molecular graph structures by inferring hidden, discrete node and edge variables from the latent base distribution (Multivariate Gaussian distribution). According to the authors, the computation of base densities in the GraphAF model is learnt by applying, in parallel, all individual scalar affine transformations, in each Relationtional Graph Policy Network layer/step, each of which depends on previous variables.  Given the Jacobian triangular matrix of GraphAF’s  autoregressive flow, molecular base densities/likelihoods can be computed by the change-of-variable formula.






   Just like in preliminary models, the authors represent molecules as graphs: G= (A, X), where X is node features while A denotes adjacency tensor. Starting from an empty graph: G, GraphAF iteratively samples random variables from a Graph Policy Network (autoregressive conditional probabilities parametized as Gaussian distributions) to map them to node/edge features. Specifically, from a sampled sub-graph structure, the authors use a layer of [Relational Graph Convolutional Network](https://docs.dgl.ai/en/latest/tutorials/models/1_gnn/4_rgcn.html) to learn the specific types of node embeddings, for a single node/atom as well as the entire current sub-graph structure, via node multi-Layer Perceptrons, and a specific type of edge/bond using the generated node/atom and current sub-graph embiddings via edge multi-layer perceptrons. The parametized Relational Graph Policy Network and its predicting mechanism define the mean and standard deviation of a Guassian distribution used to generate nodes/atoms and edges/bonds respectively. The authors introduce masking and the breadth-first search criterion (in which the nodes and edges of a training graph are re-ordered in such a way that bonds can only be present between nodes within the same or consecutive BFS depths) to drop input noise while speeding up the graph training process respectively.


>Since both the node type Xi and the edge type Aij are discrete, which do not fit into a flow-based model, a standard approach is to use Dequantization technique (Dinh et al., 2016; Kingma & Dhariwal,2018) to convert discrete data into continuous data by adding real-valued noise. We follow this approach to preprocess a discrete graph G = (A;X) into continuous data z = (zA; zX):
zXi = Xi + u; u _ U[0; 1)d; zAij = Aij + u; u _ U[0; 1)b+1:








   The proposed GraphAF’s sequential sampling mechanism allows incorporation of chemical rules like valency constraint to ensure that the current nodes do not exceed the maximum allowed valency . To further fine-tune the generated molecule’s chemical properties, the authors introduce a reinforcement learning algorithm; Proximal Policy Optimization to train the GraphAF model of constrained and target properties scores.  




*Inputs*



      ++	The number of nodes/atoms in a base distribution-**n**



      ++	The number of node types in a base distribution-**d**



      ++	The number of edge types in a base distribution-**b**




      ++	The dimension of observable data in the base distribution-**D**



      ++	A graph policy neural network like Relation Graph Policy Network



      ++	A Reinforcement Learning Framework: Proximal Policy Optimization framework


*Intermediaries*



      *	Node embeddings from the node multi-layer perceptrons




      *	Current graph sub-structure embeddings




      *	Edge embeddings from the edge multi-layer perceptrons




*Output*



      Molecular graph structure with optimized or constrained properties



*Novelty and Validations*



The authors trained their GraphAF model, first using Zinc250K dataset, and then using two other datasets: QM9 and MOSES.  They then conducted an experiment by comparing their model with four state-of-the-art approaches (JT-VAE, GCPN, MRNN, and GraphNVP) on three standard tasks including *Density Modeling and Generation*, *Property Optimization*, and *Constrained Property Optimization*. The models’ Density Modeling and Generation capacities were evaluated using four key metrics: validity, uniqueness, novelty, and reconstruction, as defined in the paper.  Further, the authors applied their model to generic datasets: EGO-SMALL and COMMUNITY-SMALL. The experimental results revealed the following:


  With its ability to leverage on valency check during sequential generation, GraphAF attained 100% validity rate on generated molecules as opposed to the comparable alternative approach: GraphNVP (one-shot processs), which only attained 42.60%. 





   Even without the valency check constraint being introduced during node sampling and generation process, the GraphAF model attained a 68% validity rate, as opposed to 20% validity rate recorded by a comparable start-of-the-art GCPN model.





 After comparing the efficiency of different models on the same computation environment, GraphAF was found to record the highest efficiency having completed the molecule generation process in only 4 hours. The other two methods compared: JT-VAE and GCPN completed molecular generation in 24 and 8 hours respectively.



Graph AF proved to overcome the *Overfitting* problem other similar models face by consistently generating valid, unique, and novel molecules when trained for high-dimension, complicated datasets like *MOSES* and *QM9*.




 
 
 By modifying the edge and node generating functions: [Edge-Multi-Layer Perceptrons]( https://jermwatt.github.io/machine_learning_refined/notes/13_Multilayer_perceptrons/13_2_Multi_layer_perceptrons.html) and [Node-Multi-Layer Perceptrons]( https://jermwatt.github.io/machine_learning_refined/notes/13_Multilayer_perceptrons/13_2_Multi_layer_perceptrons.html), GraphAF can be applied in generating different types of graphs other than molecular graphs. 





   The proposed model enables efficient molecular property optimization by introducing two key weighted rewards: valency check constraint and targeted-properties scores **e.g QED** during sampling and training respectively. 





  After optimizing the penalized logP (targeted-property score) for 800 molecules in ZINC250k with the lowest scores while adopting the Tanimoto similarity with Morgan fingerprint, the authors found that that their model was able to improve the penalized logP score by a large margin, compared to alternative comparable models, while maintaining a high similarity between the original and modified molecule. 

 


*What to Note/Assumption*


To attain favorable results, the authors had to fine-tune their model at various instances including applying [Dequantization technique]( https://arxiv.org/pdf/1511.01844.pdf) to preprocess a discrete graph into continuous data, applying [Breadth-First Search Order]( https://en.wikipedia.org/wiki/Breadth-first_search) to accelerate the training process, and introducing a feedforward neural network between layers by incorporating the *Masking technique* to prevent the transfer of input noise signal from one layer to the next. 



**Direction for Future Research*


GraphAF can be trained for even larger, complicated datasets to evaluate its capacity to model and generate complex structures like social networks. 


*Application*


   GraphAF is novel in generating molecular graph with optimized and/or constrained properties, which is applicable in drug      discovery. In that case, a Natural Language Processing framework can be incorporated, through the model’s state and policy network, to help reinforce training based on descriptive/text-based drug properties. 



   GraphAF is applicable in the generation of different graph structures, other than molecular graphs, assuming the model’s edge multi-layer perceptrons and the node multi-layer perceptrons can be modified.

 
