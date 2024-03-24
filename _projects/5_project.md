---
layout: page
title: Football Data Management with Oracle and SQL
description: Relational database built with Oracle for managing and exploring football data. Advanced SQL queries enable CRUD operations and complex data aggregations.
img: assets/img/db-er.png
importance: 5
category: Data Science
---

[This project](https://github.com/davidperezcarrasco/Football-Data-App-with-Oracle-SQL-Java-and-PHP) delves into the heart of football data, constructing a comprehensive relational database management system tailored for in-depth analysis. Oracle, a leading database engine, provides the project's foundation, ensuring efficient data storage, retrieval, and manipulation for building a rich football data repository. The user interface and backend logic leverage Java and PHP, offering a user-friendly experience for data interaction and exploration.

### Entity-Relationship Modeling

Underpinning the project's functionality lies a meticulously designed Entity-Relationship (ER) diagram.

<div class="row justify-content-sm-center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/db-er.png" title="Entity-Relationship Diagram" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Entity-Relationship Diagram of the Football Database
</div>

This visual representation serves as the database blueprint, explicitly outlining the various entities within the football domain, such as teams, players, coaches, matches, and stadiums. The relationships between these entities, for instance, "plays for" or "scores," are clearly defined, providing a comprehensive understanding of the data structure. Furthermore, cardinalities, specifying the number of occurrences within a relationship (e.g., one player playing for one team at a time), and key constraints, guaranteeing unique identification of each entity within a table (e.g., a player's unique ID), are meticulously specified within the diagram. This meticulous approach ensures data integrity and facilitates efficient querying by the user interface and underlying SQL statements.

### Building the Database with SQL

Leveraging the insights gathered from the ER diagram, the project utilizes Structured Query Language (SQL) to construct the database schema within Oracle. SQL, a powerful and standardized language specifically designed for interacting with relational databases, empowers the project to create all the necessary data tables within the Oracle database.

<div class="row justify-content-sm-center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/db-team.png" title="Team Table Instances" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/db-persons.png" title="Person Works For Relationship Set Instances" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Instances retrieved from team table and person works for relationship set
</div>

These tables serve as the foundation for storing and organizing information about teams, players, leagues, matches, goals, and other relevant entities pertinent to the football domain. Furthermore, the project adheres to best practices for data integrity by implementing appropriate data types, primary and foreign keys to enforce relationships between tables, and constraints to ensure data validity.

### User-Friendly Interface for Data Retrieval

This project transcends a simple data repository by providing a user-friendly interface for interacting with the football data and conducting in-depth analyses. Designed with accessibility in mind, the interface caters to users of varying technical backgrounds. The main menu offers a clear and concise layout, presenting a range of functionalities categorized for intuitive navigation.

<div class="row justify-content-sm-center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/db-menu.png" title="Database Interface Menu" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/db-join.png" title="Select Players by Position" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Interface Menu for the Data Retrieval and Select Players by Position feature using Join
</div>

At its core, the interface offers the fundamental CRUD (Create, Read, Update, Delete) operations on the data tables. These operations empower users to maintain data integrity by adding new teams, updating existing information, deleting outdated data, and retrieving specific player or team details. But the true power lies in the ability to perform advanced data exploration using SQL queries. The interface extends functionality beyond basic operations, allowing users to leverage joins (combining data from multiple tables based on defined relationships), aggregations (grouping and summarizing data) with and without filtering, and even nested aggregations (multi-level grouping) for complex analyses. Imagine a user exploring historical trends in player performance by combining player and match tables through a join operation, or identifying top scorers within a specific league using a nested aggregation – all facilitated by the intuitive interface.

**Seamless Integration**

The PHP and Java user interface seamlessly connects to the Oracle database. This ensures users see immediate updates whenever they interact with the features. Carefully written code translates user actions into specific SQL queries. These queries interact with the database, manipulating and retrieving data as needed. For example, clicking "Show all players of each Nationality" triggers a simple "Select" query to fetch player names and nationalities. A more complex scenario, like finding top scorers in a league, involves a more intricate "Nested Group By Aggregate" query. This query joins multiple tables (player, goal, etc.) and uses nested grouping to deliver the desired results. The user interface then displays these results, giving users immediate feedback and insights from the football data.

<div class="row justify-content-sm-center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/db-nest.png" title="Top Scorers Feature Selection" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/db-nest2.png" title="Top Scorers Feature Results" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Top Scorers Feature, using a Nested Aggregation with Group By operation
</div>
