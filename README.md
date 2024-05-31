# NoSQL Challenge: UK Food Standards Agency Analysis

## Overview

This project analyzes food hygiene ratings of establishments across the United Kingdom using MongoDB. The goal is to assist the editors of "Eat Safe, Love" magazine by evaluating the data to help their journalists and food critics decide where to focus future articles.

## Table of Contents
- [Background](#background)
- [Dataset](#dataset)
- [Project Setup](#project-setup)
- [Project Tasks](#project-tasks)
  - [1. Database and Jupyter Notebook Setup](#1-database-and-jupyter-notebook-setup)
  - [2. Update the Database](#2-update-the-database)
  - [3. Exploratory Analysis](#3-exploratory-analysis)
- [Results Summary](#results-summary)
- [Conclusion](#conclusion)

## Background

The UK Food Standards Agency evaluates various establishments across the UK, providing food hygiene ratings. This project involves analyzing this data to answer specific questions posed by the "Eat Safe, Love" magazine editors.

## Dataset

The dataset provided includes an `establishments.json` file, which contains information about food establishments, including their hygiene ratings, geolocation, and other relevant details.

## Project Setup

1. **Create Repository:**
   - Create a new repository called `nosql-challenge`.
   - Clone the repository to your local machine.
   - Add the Jupyter notebook starter files and the `Resources` folder containing `establishments.json` to the repository.
   - Push the changes to GitHub.

2. **Add .gitignore File:**
   - Add a `.gitignore` file to avoid pushing sensitive data such as API keys or large data files.

## Project Tasks

### 1. Database and Jupyter Notebook Setup

Using `NoSQL_setup_starter.ipynb`:

1. **Import Data:**
   - Import the data from `establishments.json` into MongoDB.
   - Name the database `uk_food` and the collection `establishments`.
   - Document the import command used in a markdown cell.

2. **Initialize MongoDB in Notebook:**
   - Import `PyMongo` and `Pretty Print (pprint)`.
   - Create an instance of the Mongo Client.
   - Verify the database and collection setup:
     - List all databases to confirm `uk_food` is listed.
     - List collections in `uk_food` to confirm `establishments` is present.
     - Use `find_one` to display a document from the `establishments` collection.

3. **Assign Collection Variable:**
   - Assign the `establishments` collection to a variable for further use.

### 2. Update the Database

Using `NoSQL_setup_starter.ipynb`:

1. **Add New Restaurant:**
   - Add a new halal restaurant, "Penang Flavours," to the database with the provided details.

2. **Update Restaurant with BusinessTypeID:**
   - Find the `BusinessTypeID` for "Restaurant/Cafe/Canteen".
   - Update "Penang Flavours" with the found `BusinessTypeID`.

3. **Remove Establishments in Dover:**
   - Count and remove establishments within the Dover Local Authority.
   - Verify the removal by recounting the documents.

4. **Convert Data Types:**
   - Use `update_many` to convert latitude and longitude to decimal numbers.
   - Convert `RatingValue` to integer numbers.

### 3. Exploratory Analysis

Using `NoSQL_analysis_starter.ipynb`:

1. **Hygiene Score of 20:**
   - Find establishments with a hygiene score of 20.
   - Display the count, first document, and convert results to a Pandas DataFrame.

2. **High Rating in London:**
   - Find establishments in London with a `RatingValue` of 4 or more.
   - Use `$regex` for the London Local Authority name search.
   - Display the count, first document, and convert results to a DataFrame.

3. **Top 5 Establishments Near "Penang Flavours":**
   - Find the top 5 establishments with a `RatingValue` of 5 and the lowest hygiene scores near "Penang Flavours".
   - Compare geocodes to find the nearest locations within 0.01 degrees latitude and longitude.

4. **Hygiene Score of 0 by Local Authority:**
   - Count establishments with a hygiene score of 0, grouped by Local Authority.
   - Sort the results from highest to lowest and display the top ten.
   - Convert results to a DataFrame and display the first 5 rows.

## Results Summary

**Key Findings:**
- Identified establishments with the worst hygiene scores.
- Determined the highest-rated establishments in London.
- Found the nearest top-rated establishments to "Penang Flavours".
- Highlighted local authorities with the most establishments having a hygiene score of 0.

**Visualizations:**
- DataFrames and printed outputs in the Jupyter notebooks showcase the results of each query and analysis.

## Conclusion

This project demonstrates the application of MongoDB for analyzing and updating a NoSQL database. The insights gained from the analysis can assist "Eat Safe, Love" magazine in making data-driven decisions for future articles and reviews.

---

This ReadMe case study outlines the methodology and findings of the UK Food Standards Agency analysis, showcasing the use of MongoDB, Python, and data analysis techniques in real-world data analytics.
