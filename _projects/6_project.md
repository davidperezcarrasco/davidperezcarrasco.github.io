---
layout: page
title: Data Visualization of Spotify Streaming Trends with Tableau
description: Interactive Tableau dashboards for analyzing Spotify streaming data, including artist co-occurrence networks and time series decomposition for identifying emerging trends.
img: assets/img/tb-streams.png
importance: 6
category: Data Science
---

This project utilizes Tableau to analyze a dataset of Spotify streaming information. The dataset encompasses various attributes of songs, including track names, artist(s), release dates, streaming counts, and musical characteristics like tempo and key. This data allows exploration of diverse musical trends, such as identifying top songs and artists, analyzing platform preferences, and uncovering temporal patterns through data analysis, ultimately revealing valuable insights into music consumption habits.

**Data Preprocessing for Accurate Analysis**

Prior to data visualization, a thorough data cleaning process ensured data integrity and accuracy. This process involved meticulously addressing issues like missing values and inconsistencies arising from language-specific characters within the data. Additionally, a crucial aspect of the preprocessing focused on separating artist names listed as collaborations within the "Artist(s) Name" field. By meticulously dissecting these entries, the project accurately quantifies streaming data on a per-artist basis. This approach eliminates potential misinterpretations caused by aggregated artist data and ensures a more granular understanding of artist performance. While this process was time-intensive, it significantly strengthens the project's foundation by leading to a more robust analysis and ultimately, more reliable and insightful conclusions.

### User-Driven Analysis of Streaming Data

This first dashboard invites users on an interactive journey to explore music streaming trends across artists, songs, and time. The centerpiece is a dynamic treemap showcasing the most streamed artists. Clicking on any artist within the treemap instantly refines the visualizations below. The bar chart transforms to display the top streamed songs by the selected artist(s), allowing for artist-specific song exploration. Similarly, the line plot dynamically adjusts, revealing the evolution of streaming popularity for the chosen artist(s) over the years. 

But the exploration doesn't stop there! Users can delve deeper by selecting a specific time range. This custom time frame filters the data, updating the treemap to reflect artist popularity within that period. This unveils valuable insights, such as identifying artists who gained significant traction during a specific era. This interactivity extends to the number of artists displayed. Users can choose to visualize a specific number of top artists, with the treemap and subsequent visualizations adjusting accordingly. This level of user control empowers in-depth exploration of music streaming data, uncovering hidden trends and patterns within various timeframes and artist selections.

<div class="row justify-content-sm-center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/tb-streams2.png" title="Dynamic Streaming Data Dashboard" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Dynamic Streaming Data Dashboard
</div>

This interactive dashboard unlocks fascinating insights into music streaming trends. Users can explore the who, what, and when of music popularity. By investigating different timeframes, we can identify dominant artists of various eras and witness the evolution of streaming giants. For example, while The Weeknd currently reigns supreme with Blinding Lights holding the top spot overall, user interaction can unearth fascinating shifts. Selecting specific years might expose how Bad Bunny dominated the early 2020s or Eminem ruled the late 20th century. This exploration empowers users to uncover the most streamed artists and songs for any period, along with their streaming totals. Drilling down on individual artists unveils their cumulative streaming growth over time.

