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

The core of the sentiment analysis component is based on the BERT large uncased emotions model. Fine-tuning this model involved extensive parameter tuning to optimize the precision, recall, and F1 score. Various configurations of maximum sequence length, batch size, learning rate, and epochs were tested to identify the best performing setup. The following table summarizes the results of tuning different hyperparameters for the [BERT text classification model](https://huggingface.co/google-bert/bert-large-uncased). The evaluation metrics include precision, recall, and F1 score for each configuration:

<div class="row justify-content-sm-center">
    <div class="col-sm-9">
        {% include figure.liquid loading="eager" path="assets/img/nlp/table1.png" title="Hyperparameter Tuning for BERT Text Classification Model" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Hyperparameter Tuning for BERT Text Classification Model
</div>

The optimal configuration, highlighted by a combination of high precision, recall, and F1 score, was used to fine-tune the BERT model, enhancing its performance for the sentiment analysis task. The optimal threshold for the classes labeling was between 0.2 and 0.3, as highlighted in the [report](https://github.com/davidperezcarrasco/Sentiment-Analysis-and-Contextual-Retrieval-with-LLMs-and-Transformers/blob/main/NLP_Report.pdf).

## Retrieval-Augmented Generation

The retrieval-augmented generation process in this project involves using a sentence transformer model from Hugging Face, specifically the [`all-MiniLM-L6-v2`](https://huggingface.co/sentence-transformers/all-MiniLM-L6-v2), to encode the comments. The encoded comments are then compared using cosine similarity to retrieve the most similar ones. The optimal threshold for cosine similarity was found to be around 0.5. 

For complex or lengthy input comments, where the likelihood of finding an exact match in the dataset is lower, a lower threshold can be employed to ensure some relevant outputs are retrieved. Conversely, for very short and straightforward sentences, a higher threshold can be beneficial to filter out only those comments that are strictly similar to the input, thus maintaining high precision. This dynamic adjustment of the threshold based on the input characteristics enhances the robustness and flexibility of the retrieval-augmented generation process.

<div class="row justify-content-sm-center">
    <div class="col-sm-9">
        {% include figure.liquid loading="eager" path="assets/img/nlp/output_career.png" title="Sentiment Analysis and Retrieval-Augmented Generation from a text input" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Sentiment Analysis and Retrieval-Augmented Generation from a text input
</div>

