---
layout: page
title: Data Analytics Web App for Software Dev Salary Predictions
description: Interactive platform leveraging data analytics and machine learning to predict software developers' salaries.
img: assets/img/dev-map
importance: 4
category: Data Science
---

[This project](https://github.com/davidperezcarrasco/Visual-Data-Analytics-Web-App-with-ML-Predictions) is a comprehensive endeavor aimed at providing deep insights into the salary landscape of software developers based on data gathered from the [Stack Overflow Annual Developer Survey](https://insights.stackoverflow.com/survey). By leveraging advanced data analytics techniques and machine learning models, the project provides users with actionable insights into salary trends, enabling them to make informed decisions in talent management and career planning within the tech industry.

### Data Exploration & Analytics

At the core of the project lies its Dashboard feature, serving as a comprehensive hub for data exploration and analysis. Through a variety of visually-rich EDA visualizations, ranging from violin plots illustrating salary distributions per experience level to heatmaps showcasing regional variations in salary ranges, users gain deep insights into the factors influencing salary dynamics across different demographics. Additionally, the Dashboard offers an intuitive interface for navigating through diverse data perspectives, allowing users to explore software developer distribution by country, experience, and salary range with ease. By presenting complex datasets in digestible visual representations, the Dashboard fosters a deeper understanding of the underlying trends shaping the tech job market.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include video.liquid loading="eager" path="assets/video/dev-eda.mp4" title="Exploratory Data Analysis" class="img-fluid rounded z-depth-1" controls=true autoplay=true %}
    </div>
</div>
<div class="caption">
    Exploratory Data Analysis Visualization page
</div>

The interactive web application incorporates two world maps, further enriching the user experience and offering a geographical perspective on developer salaries. One map visualizes the distribution of developers across the globe, highlighting the countries with the highest participation in the Stack Overflow survey. This provides valuable insights into the geographical spread of the software development workforce. The other map focuses on salary variations, depicting the average salary for each country. However, a crucial aspect to consider is data density. The map color-codes the number of developers contributing data from each country. This additional layer unveils interesting patterns. For example, countries like Monaco or Haiti might show anomalously high average salaries. However, the interactive data table at the bottom of the page allows users to see that this is due to a very limited sample size (only one developer responding). This highlights the importance of considering data density alongside averages to draw accurate conclusions

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include video.liquid loading="eager" path="assets/video/dev-map.mp4" title="Visual Analytics World Map page" class="img-fluid rounded z-depth-1" controls=true autoplay=true %}
    </div>
</div>
<div class="caption">
    Visual Analytics World Map page
</div>

### ML Salary Predictions

The web application empowers users to take an active role in exploring their salary potential. It leverages a machine learning model, specifically a Random Forest Regressor, to predict salaries based on user-provided information such as country, education level, and years of experience. This goes beyond a singular prediction, offering data-driven insights for informed decision-making. For example, the application might compare the predicted salary with the average salary for the chosen country and experience level. Furthermore, interactive visualizations like trend plots showcase how predicted salaries might evolve based on varying years of experience. Adding another layer of exploration, the feature allows users to compare salary predictions for multiple countries under the same experience and education level, providing valuable insights into potential salary variations across geographical locations.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include video.liquid loading="eager" path="assets/video/dev-predict.mp4" title="ML Salary Predictions page" class="img-fluid rounded z-depth-1" controls=true autoplay=true %}
    </div>
</div>
<div class="caption">
    ML Salary Predictions page
</div>
