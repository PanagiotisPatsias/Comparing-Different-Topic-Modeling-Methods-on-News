# Comparing Different Topic Modeling Methods on News

## Project Overview
In this project, we were inspired by the paper titled "Mapping climate themes from 2008-2021: An analysis of business news using topic models" [[11]](#11). Based on their approach, we decided to compare various topic modeling methods on news data to gain insights into their performance across different datasets. Specifically, we examine different methods for grouping topics in news articles, exploring traditional models, contextual models, and large language models (LLMs) like LLama. Our goal is to identify which models perform best in terms of accuracy, speed, and resource efficiency. To achieve this, we used two datasets, BBC News and 20 Newsgroups, to test and evaluate these methods.

### Authors
- Panagiotis Patsias
- Darya Zaremohazabiyeh
- Elias Suter


## Table of Contents
- [Introduction](#introduction)
- [Datasets](#datasets)
- [Preprocessing](#preprocessing)
- [Model Training](#model-training)
- [Evaluation](#evaluation)
- [Results and Discussion](#results-and-discussion)
- [Future Work](#future-work)
- [References](#references)

---

## Introduction

In natural language processing (NLP), organizing large text collections is important for tasks like content recommendation and trend analysis. This project explores different topic modeling methods to find the best approach for grouping and categorizing text in a way that is accurate and efficient. We tested a range of methods, from simple models like LDA to advanced models like LLMs, and evaluated them on two datasets.

## Datasets

We used two datasets:
1. `BBC News`: Contains 2250 categorized news articles [[3]](#3).
2. `20 Newsgroups`: Contains about 18,000 categorized emails [[6]](#6). \
   We modified the initial dataset **20 Newsgroups** by reducing the number of labels from 20 to 7. This adjustment was made to investigate whether it would improve the performance of the models, particularly the traditional and pre-trained models

These datasets allow us to see how well each model works with different types of content and complexity.

## Preprocessing

To prepare the data, we performed these steps:
- **Text Cleaning**: Removed punctuation, URLs, and email addresses.
- **Stopword Removal**: Removed common words that don't add much meaning.
- **Tokenization** and **Bag of Words (BoW)**: Prepared the text for modeling.
- Additional processing for specific models, like converting words to their root forms and preparing embeddings for FastText.

## Model Training

We trained three types of topic models:
1. **Classic Models**: Latent Dirichlet Allocation (LDA) and Non-negative Matrix Factorization (NMF).
2. **Pre-trained Models**: Embedded Topic Model (ETM) and BERTopic, which use word embeddings for better topic grouping.
3. **Large Language Models (LLMs)**: Gemini and Hermes-3-Llama, advanced models for more accurate topic understanding.

## Evaluation

### Metrics
We evaluated each model using these measures:
- **Purity**: Checks how well topics align with true categories.
- **Normalized Mutual Information (NMI)**: Measures similarity between predicted topics and actual categories.
- **F1 Score**: Balances precision and recall for topic assignment.
- **Training and Response Times**: Measures how much time each model takes to train and make predictions.

## Results and Discussion

### Key Takeaways:
- **Classic Models**: Fast and efficient for simpler data but less accurate with complex topics.
- **Pre-trained Models**: Good accuracy with some extra computational cost.
- **LLMs**: Highest accuracy, especially with complex topics, but very resource-intensive and slow.

This shows a trade-off between accuracy and speed, where simpler models work well for basic needs, but LLMs perform better on challenging data if resources are available.

## Future Work

1. **Improving LLM Prompts**: Testing better prompts to help LLMs understand topics more accurately.
2. **Expanding to More Data Types**: Trying models on other types of content, like product reviews or social media posts.
3. **Using Feedback to Improve Models**: Allowing users to give feedback on topics to refine the model.
4. **Adding More Evaluation Metrics**: Using additional metrics, like topic coherence, to get a more complete view of model performance.

## References

1. Twitter dataset. https://trec.nist.gov/data/tweets/, 2011. Accessed: 2024-11-12.
2. Adji B. Dieng, Francisco J. R. Ruiz, and David M. Blei. Topic modeling in embedding spaces. In Proceedings of the 22nd International Conference on Artificial Intelligence and Statistics (AISTATS), pages 1446–1456, 2019.
3. Derek Greene and Pádraig Cunningham. BBC News Dataset. http://mlg.ucd.ie/datasets/bbc.html, 2006. Accessed: 2024-09-18.
4. Maarten Grootendorst. BERTopic: Neural topic modeling with a class-based TF-IDF procedure. arXiv preprint arXiv:2203.05794, 2022.
5. Daniel Jurafsky and James H. Martin. Speech and Language Processing. Draft, 3rd edition, 2023.
6. Ken Lang. 20 Newsgroups Dataset. http://qwone.com/~jason/20Newsgroups/, 1995. Accessed: 2024-09-18.
7. Nils Reimers and Iryna Gurevych. Sentence-BERT: Sentence embeddings using Siamese BERT-networks. arXiv preprint arXiv:1908.10084, 2019.
8. Kaitao Song, Xu Tan, Tao Qin, Jianfeng Lu, and Tie-Yan Liu. MPNet: Masked and permuted pre-training for language understanding. In Proceedings of the 34th Conference on Neural Information Processing Systems (NeurIPS), pages 16857–16867, 2020.
9. Gemini Team and Petko Georgiev et al. Gemini 1.5: Unlocking multimodal understanding across millions of tokens of context, 2024.
10. Ryan Teknium, Jeffrey Quesnelle, and Chen Guang. Hermes 3 technical report, 2024.
11. Swarnalakshmi Umamaheswaran, Vandita Dar, Eliza Sharma, and Jikku Susan Kurian. Mapping climate themes from 2008-2021—an analysis of business news using topic models. IEEE Access, 11:26554–26565, 2023.
