# Robust Fingerprint Verification Dataset for Siamese Networks

## Overview
In the realm of biometric verification, `fingerprints` stand out as a unique identifier for individuals, offering a high level of security and reliability. With the advent of machine learning, particularly `Siamese networks`, the need for comprehensive and balanced datasets has become paramount. This repository delves into the development of a robust and balanced dataset, named `dataset.csv`, tailored for fingerprint verification tasks using Siamese networks, based on  the `SOCOFing dataset` [[1](https://www.kaggle.com/datasets/ruizgara/socofing)][[2](https://arxiv.org/abs/1807.10609))].
<p align="center">
<img src="Samples-of-fingerprint-images-in-SOCOFing-dataset.ppm" alt="Sample fingerprints" width="900px">
</p>

## Getting started
#### Requirements
1.Python

## Steps to generate the dataset 
#### **1. Data Collection: The SOCOFing Dataset**

The foundation of our dataset creation process is the SOCOFing dataset, a rich repository of synthetic fingerprint images. This dataset is chosen for its diversity in fingerprint patterns, alterations, and the inclusion of various labels indicating different characteristics like gender, hand, and finger type.

#### **2. Generating Positive and Negative Pairs**

The core of our dataset comprises two types of image pairs: **positive (matching fingerprints)** and **negative (non-matching fingerprints)**.
- #### *`Positive Pairs:`*
 
  - For each individual in the SOCOFing dataset, we generate positive pairs. This involves pairing different images of the same fingerprint from different fingers.
  - By using combinations of different fingers for the same individual, we ensure that each pair consists of fingerprints from the same person, albeit from different fingers.
  - These pairs are labeled as **1**, indicating a **match**.
    
- #### *`Negative Pairs:`*
  
  - Negative pairs are created by pairing fingerprints from different individuals.
  - We systematically generate all possible combinations of fingerprints from different people, ensuring a diverse representation of non-matching pairs.
  - These pairs are labeled as **0**, indicating **no match**.

#### **3. Balancing the Dataset**

A critical step in our methodology is balancing the number of positive and negative pairs. We calculate the required number of pairs per individual to ensure an equal representation of both positive and negative pairs. This balance is crucial to avoid bias in the Siamese network training process.

#### **4. Dataset Compilation and Preprocessing**

With the pairs generated, we compile them into a single CSV file, **dataset.csv**. This file includes the filenames of the fingerprint images in each pair and their corresponding labels. Additionally, we ensure that the images are preprocessed appropriately, including resizing and normalization, to suit the input requirements of the Siamese network.

