---
layout: page
title: Anomaly Detection Hierarchical Deep Learning Model
description: Hierarchical Deep Learning Model for Water Consumption Anomaly Detection with Web Visualization.
img: assets/img/Map.png
importance: 2
category: work
giscus_comments: false
---

Water distribution networks in urban environments face the crucial challenge of detecting anomalies like leaks, excessive consumption, or meter errors. These anomalies often go unnoticed until significant water loss occurs. This project tackles this critical issue by presenting a novel, adaptable deep learning meta-model specifically designed for anomaly detection in water meter data.  Our model, leveraging the power of LSTMs and Transformers, effectively captures sequential consumption patterns and identifies deviations from normal behavior.  This enables early detection of anomalies, potentially leading to significant cost savings for both water companies and consumers, while promoting sustainable water usage.

**A Deep Learning Approach**

Traditional machine learning methods like SVMs and Isolation Forests often struggle with large, time-dependent datasets  like water consumption data.  Deep learning methods, on the other hand, have shown promising results in anomaly detection tasks.  [Transformers](https://github.com/imperial-qore/TranAD), in particular, excel at identifying complex patterns in sequential data, making them a strong candidate for this application.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/TranAD.png" title="Transformer AD Architecture" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Transformer AD Architecture. Shreshth Tuli, Giuliano Casale, and Nicholas R. Jennings. Tranad: Deep transformer networks for anomaly detection in multivariate time series data. 2022
</div>

**Multi-Stage Hierarchical Architecture**

The core of this project lies in its hierarchical deep learning architecture, specifically designed for anomaly detection in water consumption data. This multi-stage training approach fosters specialization in the later stages while preserving valuable generalizations learned earlier. This balance between adaptability to specific data patterns and overall robustness in anomaly detection is achieved through the integration of three key components:

- TranAD: This transformer-based model excels at identifying deviations in time series data. It undergoes a two-phase adversarial training process to capture both short-term trends and long-term dependencies within the data. (Full details on the training procedure can be found in section 3.4 of Vaswani et al., 2023: https://arxiv.org/abs/2306.05903)

- Multi-LSTM:  This advanced LSTM architecture tackles the challenge of analyzing data across multiple temporal windows simultaneously. This capability is crucial for capturing complex patterns at various time scales, enhancing the model's accuracy and robustness. Unlike conventional LSTMs, our Multi-LSTM allows for parameterization of both the number of LSTMs and the size of their temporal windows, enabling greater adaptability to diverse data.

- Multi-Layer Perceptron (MLP):  This final component acts as a decision layer, evaluating and combining the outputs from the previous stages.  By integrating the general insights from earlier training stages with the specialized knowledge of later stages, the MLP provides a single, highly accurate prediction while avoiding overfitting.

The synergy between these components lies at the heart of the model's power.  The precise anomaly detection capabilities of TranAD are complemented by the Multi-LSTM's ability to handle complex temporal dependencies.  Finally, the MLP effectively combines these strengths, leading to a robust and versatile solution for anomaly detection in water consumption data.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/water_architecture.png" title="Hierarchical Architecture" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Multi-Stage Deep Learning Meta Model with Hierarchical Training.
</div>
