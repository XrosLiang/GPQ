## Generalized Product Quantization Network for Semi-supervised Image Retrieval
Tensorflow implementation of GPQ    
Accepted to CVPR 2020 - <a href="https://arxiv.org/abs/2002.11281">arxiv</a>  
Young Kyun Jang and Nam Ik Cho  

## Abstract

Image retrieval methods that employ hashing or vector quantization have achieved great success by taking advantage of deep learning. However, these approaches do not meet expectations unless expensive label information is sufficient. To resolve this issue, we propose the first quantization-based semi-supervised image retrieval scheme: Generalized Product Quantization (GPQ) network. We design a novel metric learning strategy that preserves semantic similarity between labeled data, and employ entropy regularization term to fully exploit inherent potentials of unlabeled data. Our solution increases the generalization capacity of the quantization network, which allows overcoming previous limitations in the retrieval community. Extensive experimental results demonstrate that GPQ yields state-of-the-art performance on large-scale real image benchmark datasets.

## How to use

### 1. Install requirements on your environment.
- Ubuntu=16.04
- Tensorflow=1.14
- Tflearn=0.3.2
- Numpy=1.16.6
- Matplotlib=3.2.1

### 2. Preparation.
- Download pretrained model and data from <a href="https://drive.google.com/open?id=1BfyXFvcMMBhD2jWVNF_kFaFE5uNgpqII">here</a>.
- Extract them to the `/path/to/GPQ-master`.
- Make sure the tree seems as:  
```
|--GPQ-master
   |--cifar10
      |--batches.meta
      |--data_batch_1
      |--data_batch_2
      |--data_batch_3
      |--data_batch_4
      |--data_batch_5
      |--test_batch
      |--cifar10_Similarity.mat
   |--models
      |--48bits_example.ckpt.data-00000-of-00001
      |--48bits_example.ckpt.index
      |--48bits_example.ckpt.meta
      |--ImageNet_pretrained.mat
```
### 3. Test
- From cifar10 dataset, we use 1,000 images for query and 54,000 images to build retrieval database.
- We provide 48bits (12 codebooks with 2^4 codewords) pretrained model as an example.
- Make sure to set proper path in `config.py`.
- Run `Demo.py`, it will print mAP and stores one of the visualized ranked-list.
- Examples
 
 
 
### 4. Train
- We employ randomly selected 5,000 images with labels and 54,000 images without labels for semi-supervised learning.
- To control the number of bits used for image retrieval, modify `config.py` to change the number of codebooks, codewords.
- Run `train.py`, and it will save the model parameters for every 20 epochs.


# tSNE Visualization

<p align="center"><img src="figures/tSNE.png" width="900"></p>

## Citation
```
@InProceedings{GPQ,
author = {Young Kyun Jang and Nam Ik Cho},
title = {Generalized Product Quantization Network for Semi-supervised Image Retrieval},
booktitle = {IEEE Conference on Computer Vision and Pattern Recognition (CVPR)},
month = {June},
year = {2020}
}
```
