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

This first dashboard invites an interactive exploration of music streaming trends across artists, songs, and time. A dynamic treemap showcases the most streamed artists, with clicks refining visualizations below. The bar chart transforms to display top streamed songs by selected artist(s) for artist-specific exploration. Similarly, the line plot adjusts, revealing artist streaming popularity over time. User control extends further - selecting a time range refines the treemap based on artist popularity within that period, uncovering era-specific trends. Additionally, users can choose the number of top artists displayed, with all visualizations adjusting accordingly. This empowers in-depth exploration, uncovering hidden trends and patterns within various timeframes and artist selections.

<div class="row justify-content-sm-center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/tb-streams2.png" title="Dynamic Streaming Data Dashboard" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Dynamic Streaming Data Dashboard
</div>

This interactive dashboard unlocks fascinating insights into music streaming trends. Users can explore the who, what, and when of music popularity. By investigating different timeframes, we can identify dominant artists of various eras and witness the evolution of streaming giants. For example, while The Weeknd currently reigns supreme with Blinding Lights holding the top spot overall, user interaction can unearth fascinating shifts. Selecting specific years might expose how Bad Bunny dominated the early 2020s or Eminem ruled the late 20th century. This exploration empowers users to uncover the most streamed artists and songs for any period, along with their streaming totals. Drilling down on individual artists unveils their cumulative streaming growth over time.

### Artist Collaboration Analysis

The second dashboard focuses on artist collaborations, a key aspect of the music industry. The main view is a dynamic bubble chart, with bubble size and color representing each artist's total streams. Users can explore data for specific timeframes or limit the number of artists displayed.  Selecting an artist within the bubble chart unlocks further details.  The visualizations below shift to showcase the artist's most frequent collaborators and their most successful collaborations in terms of streaming numbers. This allows for a direct comparison, revealing whether frequent collaborations translate into the most successful ones for each artist.

<div class="row justify-content-sm-center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/tb-featurings.png" title="Featurings Dashboard" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Dynamic Featurings Dashboard
</div>

Exploring collaborations exposes intriguing patterns.  An artist might frequently collaborate with another artist, but this doesn't always guarantee the most successful partnership.  For example, The Weeknd has collaborated with Gesaffelstein twice, but his biggest hit in terms of streams is with Daft Punk, reaching a massive 2.5 billion streams for a single song.  Similarly, Drake's most streamed collaboration involves WizKid, surpassing the combined streams of his eight collaborations with 21 Savage.  These insights highlight the potential for unexpected discoveries within the data, revealing collaborations that outperform more frequent pairings.
