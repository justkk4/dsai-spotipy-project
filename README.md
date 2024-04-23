# Spotify-Popularity-Score Repository
---
## Overview
This is a submitted mini project for SC1015 (Introduction to Data Science and Artificial Intelligence) that predicts track/artist popularity scores using data extracted using the [Spotify API 'Spotipy'](https://developer.spotify.com/documentation/web-api). 

To follow the project in its sequential order, please view the notebooks in the following order:
1. [Data Extraction & Cleaning](data-extraction-and-cleaning.ipynb)
2. [Data Visualisation](data-visualisation.ipynb)
3. [Data Resampling](data-resampling.ipynb)
4. [Predicting Artist Popularity using Artist Genres & Album Release Decade](predicting-popularity-from-genre-date.ipynb)
5. [Predicting Song Popularity using Audio Features](predicting-popularity-from-audio-features.ipynb)

---
## Contributions List
- @justkk4 - Data Extraction & Cleaning, Data Visualisation
- @ YUKI - Data Resampling, Predicting Song Popularity using Audio Features
- @ WESLEY - Predicting Artist Popularity using Artist Genres & Album Release Decade

---
## Problem Definition
- Can we predict if an artist is popular (artist popularity > 50) using artist genres & album release decade?
- Can we predict if a song is popular (track popularity > 50) using its audio features?

---
## Dataset Files
- dataset.csv (extracted using API)
- time.csv ([Kaggle](https://www.kaggle.com/datasets/joebeachcapital/top-10000-spotify-songs-1960-now?resource=download) dataset)
- merged20k.csv (dataset.csv + time.csv, cleaned)
    - used for [predicting artist popularity](predicting-popularity-from-genre-date.ipynb)
- merged200k.csv (merged20k.csv + [Kaggle](https://www.kaggle.com/datasets/zaheenhamidani/ultimate-spotify-tracks-db) dataset, cleaned)
    - used for [predicting song popularity](predicting-popularity-from-audio-features.ipynb)

---
## Resampling Methods Used
- SMOGN
- Random Oversampling
- Random Undersampling
- NearMiss

---
## Models Used
- Predicting Artist Popularity
    - Regression Models
        - Linear Regression
        - Lasso Regression
        - Random Forest Regression
        - Neural Network
        - Gradient Boosting w/ Decision Trees
    - Classification Models
        - Logistic Regression
        - Logistic Lasso Regression
        - Random Forest Classifier
        - Support Vector Machines

- Predicting Track Popularity
    - Regression Models
        - Linear Regression
        - Ridge Regression
        - Lasso Regression
        - Decision Tree
        - Random Forest
        - Gradient Boosting
        - Extra Tree Regression
    - Classification Models
        - Logistic Regression
        - K-Neighbours Classifier
        - Decision Tree Classifier
        - Random Forest Classifier
        - Gradient Boosting Classifier

---
## Overview of Each Notebook
### <u>**data-extraction.ipynb**</u>
This notebook demonstrates how each of the four dataset files were created. The original base dataset (dataset.csv) is formed purely from extracting songs from Spotify using its web API. Helper functions utilising the API were written to extract the variables necessary for this project from Spotify. This data was then written to [dataset.csv](datasets/dataset.csv).

[time.csv](datasets/time.csv) is a Kaggle dataset appended with its respective artist popularity values. The retrieval of artist popularity values was done using the API.

[merged20k.csv](datasets/merged20k.csv) is the combination of time.csv and dataset.csv. Duplicate and null tracks were removed. A new column 'Decade Released' was also added. This column was formed by mapping 'Album Release Date' values to their respective decades using datetime.

[merged200k.csv](datasets/merged200k.csv) is the combination of merged20k.csv and another Kaggle dataset. Duplicate tracks were also removed.

### <u>**data-visualisation.ipynb**</u>
This notebook visualises the predictor and response variables of merged20k.csv and merged200k.csv. Both response and predictor variables are visualised independently. Predictor variables are also visualised with their respective response variable.

> This notebook is also where the problem of an unbalanced dataset was discovered which motivated us to conduct data resampling.

### <u>**data-resampling.ipynb**</u>
This notebook demonstrates the process of data resampling for merged200k.csv. Both regression and classificatio and sampling methods are demonstrated. The success of resampling is visualised in a countplot at the end of the notebook.

### <u>**predicting-popularity-from-genre-date.ipynb**</u>
This notebook demonstrates the use of both regression and classification models to predict artist popularity using artist genres and album release decade. It illustrates how regression models may not be suitable for this problem and shows the conversion of the original regression problem into a classification problem.

> Random Forest Regression was deemed to be the best regression model as it had the greatest explained variance and lowest RMSE. Logistic Lasso Regression was deemed to be the best classification model due to its high accuracy and low false positive rate.

A predictor model is also demonstrated at the end of the notebook to demonstrate the ability of the two models.

### <u>**predicting-popularity-from-audio-features.ipynb**</u>
This notebook demonstrates the use of both regression and classification models to predict track popularity using audio features. Since data resampling was conducted for this analysis, non-sampled are compared against resampled datasets to see which performs better in the standard regression and classification models.

The datasets that perform better are then fitted onto various regression/classification models. In the conclusion of the notebook, different conclusions for the best model are drawn for different contexts.

---
## Conclusions
I HAVE NO IDEA WHAT TO WRITE HERE CAN YOU GUYS LET ME KNOW WHAT YOU GUYS CONCLUDED

---
## New Knowledge gained from project
- Use of Spotify API 'Spotipy'
- Managing unbalanced datasets using resampling methods
- Using datetime to convert specific dates to decades
- ???? (can talk about new models)

---
## References
- https://spotipy.readthedocs.io/en/2.22.1/
- https://towardsdatascience.com/extracting-song-data-from-the-spotify-api-using-python-b1e79388d50
- https://developer.spotify.com/documentation/web-api
- (add all references pls)