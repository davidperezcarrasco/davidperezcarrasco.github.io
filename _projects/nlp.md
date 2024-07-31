---
layout: page
title: Sentiment Analysis and Contextual Retrieval with LLMs and Transformers
description: Sentiment analysis and contextual retrieval using transformer models, featuring an interactive web interface for input analysis and comment retrieval.
img: assets/img/nlp/wallpaper.png
importance: 3
category: Machine Learning
---

[This project](https://github.com/davidperezcarrasco/Sentiment-Analysis-and-Contextual-Retrieval-with-LLMs-and-Transformers) focuses on implementing a comprehensive Natural Language Processing (NLP) pipeline for sentiment analysis and contextual comment retrieval using state-of-the-art transformer models. The system accepts text or audio input, converts the audio to text, predicts sentiment labels with a fine-tuned BERT text classification model, retrieves similar comments using cosine similarity, and generates summaries using a Hugging Face large language model (LLM). The integration of these components showcases advanced NLP techniques, including sentiment analysis, contextual embeddings, and prompt engineering, within a seamless and interactive web interface.

## BERT's Text Classification Model Fine Tuning

The core of the sentiment analysis component is based on the BERT large uncased emotions model. Fine-tuning this model involved extensive parameter tuning to optimize the precision, recall, and F1 score. Various configurations of maximum sequence length, batch size, learning rate, and epochs were tested to identify the best performing setup. The following table summarizes the results of tuning different hyperparameters for the BERT text classification model. The evaluation metrics include precision, recall, and F1 score for each configuration:

| Max Seq Size | Batch Size | Learning Rate | Epochs | Precision | Recall | F1   |
|--------------|------------|---------------|--------|-----------|--------|------|
| 128          | 32         | 2e-5          | 3      | 0.60      | 0.40   | 0.46 |
| 64           | 32         | 1e-5          | 3      | 0.59      | 0.35   | 0.41 |
| 192          | 32         | 2e-5          | 3      | 0.55      | 0.41   | 0.46 |
| 192          | 32         | 4e-5          | 3      | 0.55      | 0.43   | 0.47 |
| 64           | 64         | 2e-5          | 5      | 0.56      | 0.42   | 0.47 |

The optimal configuration, highlighted by a combination of high precision, recall, and F1 score, was used to fine-tune the BERT model, enhancing its performance for the sentiment analysis task. The optimal threshold for the classes labeling was between 0.2 and 0.3, as highlighted in the [report]](https://github.com/davidperezcarrasco/Sentiment-Analysis-and-Contextual-Retrieval-with-LLMs-and-Transformers/blob/main/NLP_Report.pdf).

#TODO: unmute videos from data analytics, change links from data science projects, check projects interface, finish nlp and cv