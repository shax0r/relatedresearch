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
