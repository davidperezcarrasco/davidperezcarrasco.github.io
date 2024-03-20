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

**Deep Learning Approach**

Traditional machine learning methods like SVMs and Isolation Forests often struggle with large, time-dependent datasets  like water consumption data.  Deep learning methods, on the other hand, have shown promising results in anomaly detection tasks.  [Transformers](https://github.com/imperial-qore/TranAD), in particular, excel at identifying complex patterns in sequential data, making them a strong candidate for this application.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/TranAD.png" title="Transformer AD Architecture" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Transformer AD Architecture. Shreshth Tuli, Giuliano Casale, and Nicholas R. Jennings. Tranad: Deep transformer networks for anomaly detection in multivariate time series data. 2022
</div>

