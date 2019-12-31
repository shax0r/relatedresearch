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


