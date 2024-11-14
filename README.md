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

1. [`BBC News`](https://drive.google.com/file/d/1TU8mkfBuqmPh8xoAxMuAY8icvRyK_eVn/view?usp=sharing): Contains 2250 categorized news articles [[3]](#3).
2. [`20 Newsgroups`](https://drive.google.com/file/d/1ARU6-0R9HWBRHBwr3AHzJkA1oOZvRdfG/view?usp=sharing): Contains about 18,000 categorized emails [[6]](#6). \
   We modified the initial dataset **20 Newsgroups** by reducing the number of labels from 20 to 7. This adjustment was made to investigate whether it would improve the performance of the models, particularly the traditional and pre-trained models

These datasets allow us to see how well each model works with different types of content and complexity.

## Preprocessing
In our topic modeling experiment, we applied several preprocessing techniques tailored to the specific requirements of each modeling approach, including lowercasing, punctuation removal, stopword elimination, and handling URLs and email addresses. In the table below, you can see which preprocessing steps were applied to each model.
- ### Preprocessing Summary

| **Preprocessing Step**         | **Classic Models (LDA, NMF)** | **Pre-trained Models (ETM, BERTopic)** | **LLMs**  |
|---------------------------------|-------------------------------|----------------------------------------|-----------|
| Lowercasing                     | ✔                             | ✔                                      | ✘         |
| Removing Punctuation            | ✔                             | ✔                                      | ✘         |
| Removing Numbers                | ✔                             | ✔                                      | ✘         |
| Replacing URLs with Placeholders| ✔                             | ✔                                      | ✘         |
| Replacing Email with Placeholders| ✔                             | ✔                                      | ✘         |
| Removing Stopwords              | ✔                             | ✔ (only for ETM)                       | ✘         |
| Stemming                        | ✘                             | ✔ (only for ETM)                       | ✘         |
| Lemmatization                   | ✔                             | ✘                                      | ✘         |


## Model Training

We trained three types of topic models:
1. **Classic Models**: Latent Dirichlet Allocation (LDA) and Non-negative Matrix Factorization (NMF).
2. **Pre-trained Models**: Embedded Topic Model (ETM) and BERTopic, which use word embeddings for better topic grouping.
3. **Large Language Models (LLMs)**: Gemini and Hermes-3-Llama, advanced models for more accurate topic understanding.

## Evaluation

### Metrics
We evaluated each model using these measures:
- **Purity**: Checks how well topics align with true categories.
- **accuracy**: Measures the proportion of correctly classified documents.
- **Normalized Mutual Information (NMI)**: Measures similarity between predicted topics and actual categories.
- **F1 Score**: Balances precision and recall for topic assignment.
- **Training and Response Times**: Measures how much time each model takes to train and make predictions.

## Results and Discussion

### Key Takeaways:
- **Classic Models**: Fast and efficient for simpler data but less accurate with complex topics.
- **Pre-trained Models**: Good accuracy with some extra computational cost.
- **LLMs**: Highest accuracy, especially with complex topics, but very resource-intensive and slow.

This shows a trade-off between accuracy and speed, where simpler models work well for basic needs, but LLMs perform better on challenging data if resources are available.

## References

1. Derek Greene and Pádraig Cunningham. BBC News Dataset. http://mlg.ucd.ie/datasets/bbc.html, 2006. Accessed: 2024-09-18.
2. Ken Lang. 20 Newsgroups Dataset. http://qwone.com/~jason/20Newsgroups/, 1995. Accessed: 2024-09-18.

