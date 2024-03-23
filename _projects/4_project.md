---
layout: page
title: Data Analytics Web App for Software Developer Salary Predictions
description: Interactive platform leveraging data analytics and machine learning to predict software developers' salaries, offering actionable insights for talent management.
img: assets/img/dev-map
importance: 4
category: work
---

This project is a comprehensive endeavor aimed at providing deep insights into the salary landscape of software developers based on data gathered from the Stack Overflow Annual Developer Survey. By leveraging advanced data analytics techniques and machine learning models, the project provides users with actionable insights into salary trends, empowering them to make informed decisions in talent management and career planning within the tech industry.

At the core of the project lies its Dashboard feature, serving as a comprehensive hub for data exploration and analysis. Through a variety of visually-rich EDA visualizations, ranging from violin plots illustrating salary distributions per experience level to heatmaps showcasing regional variations in salary ranges, users gain deep insights into the factors influencing salary dynamics across different demographics. Additionally, the Dashboard offers an intuitive interface for navigating through diverse data perspectives, allowing users to explore software developer distribution by country, experience, and salary range with ease. By presenting complex datasets in digestible visual representations, the Dashboard fosters a deeper understanding of the underlying trends shaping the tech job market.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/dev-StreamlitEDA.png" title="Exploratory Data Analysis" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Exploratory Data Analysis Visualization page
</div>

Complementing the Dashboard, the Interactive Maps feature provides users with a captivating visualization of global salary distributions and developer density. Through interactive world maps, users can discern regional disparities in mean salary distributions and developer concentrations, gaining valuable insights into geographical variations in salary dynamics. By overlaying mean salary data with the density of survey respondents, the maps offer a nuanced perspective on regional tech job markets, enabling users to identify emerging trends and opportunities for growth in specific regions.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/dev-StreamlitMap.png" title="Visual Analytics World Map" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Visual Analytics World Map page
</div>

The Prediction Tools embedded within the web app offer users personalized salary estimates based on diverse parameters such as country, education, and experience. Leveraging sophisticated machine learning algorithms, the Prediction Tools empower users to make informed decisions regarding career opportunities and salary negotiations. Whether estimating individual salary projections or comparing salary differentials between two countries, the Prediction Tools provide users with actionable insights to navigate the complexities of the tech job market with confidence and precision.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/dev-StreamlitPredict.png" title="ML Salary Predictions" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    ML Salary Predictions page
</div>
