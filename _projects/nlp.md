---
layout: page
title: Sentiment Analysis and Contextual Retrieval with LLMs and Transformers
description: Sentiment analysis and contextual retrieval leveraging BERT, Hugging Face transformers, fine-tuning techniques and ASR.
img: assets/img/nlp/wallpaper.png
importance: 3
category: Machine Learning
---

[This project](https://github.com/davidperezcarrasco/Sentiment-Analysis-and-Contextual-Retrieval-with-LLMs-and-Transformers) focuses on implementing a comprehensive Natural Language Processing (NLP) pipeline for sentiment analysis and contextual comment retrieval using state-of-the-art transformer models. The system accepts text or audio input, converts the audio to text, predicts sentiment labels with a fine-tuned BERT text classification model, retrieves similar comments using cosine similarity, and generates summaries using a Hugging Face large language model (LLM). The integration of these components showcases advanced NLP techniques, including sentiment analysis, contextual embeddings, and prompt engineering, within a seamless and interactive web interface.

## BERT's Text Classification Model Fine Tuning

The core of the sentiment analysis component is based on the BERT large uncased emotions model. Fine-tuning this model involved extensive parameter tuning to optimize the precision, recall, and F1 score. Various configurations of maximum sequence length, batch size, learning rate, and epochs were tested to identify the best performing setup. The following table summarizes the results of tuning different hyperparameters for the BERT text classification model. The evaluation metrics include precision, recall, and F1 score for each configuration:

<div class="row justify-content-sm-center">
    <div class="col-sm-9">
        {% include figure.liquid loading="eager" path="assets/img/nlp/table1.png" title="Hyperparameter Tuning for BERT Text Classification Model" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Hyperparameter Tuning for BERT Text Classification Model
</div>

The optimal configuration, highlighted by a combination of high precision, recall, and F1 score, was used to fine-tune the BERT model, enhancing its performance for the sentiment analysis task. The optimal threshold for the classes labeling was between 0.2 and 0.3, as highlighted in the [report](https://github.com/davidperezcarrasco/Sentiment-Analysis-and-Contextual-Retrieval-with-LLMs-and-Transformers/blob/main/NLP_Report.pdf).
