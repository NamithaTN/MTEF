MTEFO: Multimodal Transformer Embedding Fusion and Oversampling for Early Prediction of IVIG Resistance in Kawasaki Disease
Overview

This repository contains the implementation of MTEFO, a hybrid machine learning framework designed to predict intravenous immunoglobulin (IVIG) resistance in Kawasaki Disease (KD) using structured clinical data.

The proposed approach integrates semantic embeddings from pretrained transformers with tabular transformer representations, followed by embedding-level oversampling and classical machine learning classification.

The method is designed to address:

Small clinical datasets

Class imbalance

Feature interaction learning

Key Contributions

Transform structured clinical features into semantic sentences and extract embeddings using Sentence Transformers.

Generate tabular feature embeddings using FT-Transformer (AutoGluon).

Fuse both embedding spaces to capture complementary representations.

Apply SMOTE/ADASYN oversampling in the fused embedding space.

Train classical ML models for IVIG resistance prediction.

Framework Overview

Pipeline of the proposed MTEFO model:

Clinical data preprocessing

Sentence transformation of structured features

Sentence Transformer embedding extraction

FT-Transformer tabular embedding extraction

Embedding fusion

Oversampling in embedding space

Classical ML classification

Methodology
1. Sentence Transformer Embeddings

Structured patient data is converted into sentence format and encoded using:

paraphrase-MiniLM-L6-v2

This captures semantic relationships between clinical variables.

2. FT-Transformer Embeddings

Tabular embeddings are generated using AutoGluon's FT-Transformer, which learns feature interactions in structured datasets.

3. Embedding Fusion

The embeddings from both transformers are concatenated to form a fused feature representation.

4. Oversampling

To handle class imbalance, oversampling methods such as:

SMOTE

ADASYN

are applied in the fused embedding space.

5. Classification

The fused embeddings are used to train classical machine learning models such as:

Random Forest

LightGBM

Gradient Boosting
