# exploring-falls-insights

# Exploring Insights and Tagging Medical Narratives Using Unsupervised Learning

## Overview

This repository contains the implementation and findings of the project **"Exploring insights and tagging medical narratives using unsupervised learning"** by Siddharth Rayabharam, as part of his Master's in Computer Science at Pennsylvania State University.

The project focuses on applying unsupervised learning techniques to classify and gain insights from medical narratives, specifically related to fall-related injuries. The research aims to leverage Natural Language Processing (NLP) and Machine Learning (ML) to uncover hidden insights from unstructured clinical text data.

## Introduction

Falls are a leading cause of injury-related deaths among older adults. This project explores the potential of unsupervised learning techniques to extract insights from medical narratives related to fall injuries. Using clinical text data collected from emergency departments across the United States, the project aims to classify narratives into different injury types and extract useful insights that can aid in improving patient care and safety interventions.

## Methodology

### Dataset

The dataset used in this project is the **National Electronic Injury Surveillance System (NEISS)**, a publicly available dataset maintained by the Consumer Product Safety Commission (CPSC). It contains over 115,000 cases of unintentional falls among older adults, with information about patient demographics, clinical diagnoses, and incident descriptions.

### Preprocessing

The preprocessing step involves translating medical abbreviations into their full forms and transforming numerical codes into textual columns. The narratives are then enhanced with additional contextual information extracted from the dataset, resulting in more descriptive and structured narratives. These processed narratives are fed into a transformer model to answer specific questions about the incidents (e.g., cause, diagnosis, location).

### Topic Modeling

We use **Latent Dirichlet Allocation (LDA)** for topic modeling. The LDA model is trained on the detailed narratives to discover hidden patterns and classify the narratives into different injury types. Hyperparameters such as the number of topics, bigram and trigram counts, and chunk sizes are optimized using the **Optuna** framework.

### Clustering

Several clustering models are also evaluated as baselines for comparison with LDA. **K-Means** clustering, **DBSCAN**, and **HDBSCAN** are applied to the narratives, with feature vectors generated using the **word2vec** model.

### Classification

The narratives are classified into 8 distinct injury types based on the injury keywords identified by the CDC. Each cluster of narratives is associated with one of the injury types, such as fractures, sprains, and lacerations.

### Evaluation

The performance of the LDA and clustering models is evaluated using metrics such as **perplexity**, **coherence**, **Silhouette Score**, **Calinski-Harabasz Index**, and **Davies-Bouldin Index**. Human-assisted evaluation is also conducted to assess the models' classification accuracy.

## Results

The LDA model achieved an overall classification accuracy of **81%**, outperforming the K-Means clustering model, which had an accuracy of **72%**. Both models demonstrated notable challenges in classifying specific injury types, particularly sprains, due to limited data representation.

## Conclusion

This project demonstrates the feasibility of using unsupervised learning techniques to extract insights and classify injury-related medical narratives. The insights gained from these narratives could inform healthcare interventions, such as safety programs and educational initiatives. Future work should focus on improving model performance for underrepresented injury types and exploring automated evaluation methods using advanced language models.

## References

1. Siddharth Rayabharam, Dr. Sayed Mohsin Reza, and Dr. Md Faisal Kabir. *Exploring insights and tagging medical narratives using unsupervised learning*. COMP594 Final Paper, Pennsylvania State University.
2. [National Electronic Injury Surveillance System (NEISS)](https://health.gov/healthypeople/objectives-and-data/data-sources-and-methods/data-sources/national-electronic-injury-surveillance-system-all-injury-program-neiss-aip)
