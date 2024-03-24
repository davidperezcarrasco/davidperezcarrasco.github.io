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

Prior to data visualization, a thorough data cleaning process ensured data integrity and accuracy. This process rectified missing values and addressed inconsistencies stemming from language-specific characters. Additionally, collaborative artist entries in the "Artist(s) Name" field were separated to enable accurate artist-level streaming quantification. This meticulous approach, while time-consuming, significantly bolstered data reliability and precision, leading to a more comprehensive and insightful analysis.

### User-Driven Analysis of Streaming Data

This first dashboard invites an interactive navigation of music streaming trends across artists, songs, and time. A dynamic treemap showcases the most streamed artists, with clicks refining visualizations below. The bar chart transforms to display top streamed songs by selected artist(s) for artist-specific exploration. Similarly, the line plot adjusts, revealing artist streaming popularity over time. User control extends further - selecting a time range refines the treemap based on artist popularity within that period, uncovering era-specific trends. Additionally, users can choose the number of top artists displayed, with all visualizations adjusting accordingly. This facilitates comprehensive analysis, revealing hidden patterns within various timeframes and artist selections.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include video.liquid loading="eager" path="assets/video/tb-streams.mp4" title="Dynamic Streaming Data Dashboard" class="img-fluid rounded z-depth-1" controls=true autoplay=true %}
    </div>
</div>
<div class="caption">
    Dynamic Streaming Data Dashboard
</div>

This interactive dashboard unveils captivating insights into music streaming trends, offering a comprehensive exploration of the who, what, and when of music popularity. By investigating different timeframes, dominant artists of various eras emerge, showcasing the evolution of streaming giants. For instance, while The Weeknd currently reigns supreme with Blinding Lights holding the top spot overall, user interaction reveals intriguing shifts. Selecting specific years might expose how Bad Bunny dominated the early 2020s or Eminem ruled the late 20th century. This exploration empowers users to discover the most streamed artists and songs for any period, alongside their streaming totals. Drilling down on individual artists unveils their cumulative streaming growth over time.

### Artist Collaboration Analysis

The second dashboard focuses on artist collaborations, a key aspect of the music industry. The main view is a dynamic bubble chart, with bubble size and color representing each artist's total streams. Users can explore data for specific timeframes or limit the number of artists displayed. Selecting an artist within the bubble chart unlocks further details. The visualizations below shift to showcase the artist's most frequent collaborators and their most successful collaborations in terms of streaming numbers. This allows for a direct comparison, revealing whether frequent collaborations translate into the most successful ones for each artist.

<div class="row justify-content-sm-center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/tb-featurings.png" title="Featurings Dashboard" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Dynamic Featurings Dashboard
</div>

Exploring collaborations exposes intriguing patterns. An artist might frequently collaborate with another artist, but this doesn't always guarantee the most successful partnership. For example, The Weeknd has collaborated with Gesaffelstein twice, but his biggest hit in terms of streams is with Daft Punk, reaching a massive 2.5 billion streams for a single song. Similarly, Drake's most streamed collaboration involves WizKid, surpassing the combined streams of his eight collaborations with 21 Savage. These insights highlight the potential for unexpected discoveries within the data, revealing collaborations that outperform more frequent pairings.

### Interactive Exploration of Streaming Trends Over Time

Delving deeper, this dashboard delves into how music streaming trends evolve over time. Users can navigate through years, months, and even days using interactive line plots. Selecting a specific year instantly refines the visualizations below. The month and day charts update dynamically, showcasing streaming data only for songs released in that chosen year. This allows for a granular examination of how streaming patterns change throughout the year. Additionally, a dynamic bar chart displays the most streamed artists for the selected timeframe. Uniquely, this bar chart breaks down each artist's performance by their top songs, providing a detailed picture of artist and song popularity within that period. For example, user interaction can reveal which artists dominated specific days, months, or years, like uncovering Justin Bieber's most streamed songs released in June. This level of interactivity empowers users to conduct a thorough analysis of streaming trends across various timeframes.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include video.liquid loading="eager" path="assets/video/tb-streams.mp4" title="Streaming Trends Over Time" class="img-fluid rounded z-depth-1" controls=true autoplay=true %}
    </div>
</div>
<div class="caption">
    Streaming Trends Over Time
</div>

### Exploring Artist and Song Longevity

This final dashboard sheds light on a unique aspect of music popularity - how long songs and artists stay relevant on charts and playlists. Stepping away from pure streaming numbers, we delve into weeks spent on charts across various platforms like Spotify, Deezer, Apple Music, and Shazam. The centerpiece is a dynamic treemap showcasing the top artists based on the total weeks charted by all their songs. Interactive bar charts complement this view, displaying the top songs by weeks in charts and top songs by weeks in playlists. Selecting an artist within the treemap refines the song charts, allowing for a focused exploration of their performance.

<div class="row justify-content-sm-center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/tb-charts.png" title="Popular Artists and Songs by charts and playlists" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Popular Artists and Songs by charts and playlists
</div>

This exploration uncovers fascinating insights that challenge traditional measures of music popularity. An artist might achieve significant streaming success but not necessarily lead the charts. For instance, Taylor Swift might hold the top spot based on chart longevity, while The Weeknd may dominate streaming platforms. Similarly, "Vampire" might top the charts, while "Get Lucky" dominates playlists. These discoveries highlight a key takeaway: most streamed songs don't necessarily translate to songs that stay on charts or playlists the longest. This interactive dashboard enables users to delve deeper, uncovering hidden trends and patterns within music popularity, ultimately revealing the multifaceted nature of achieving success in the music industry.
