# Danish Club Final Project
Hello! We are the Danish Club and velkommen til vores (welcome to our) MATH244 Final Project where we will be analyzing what characteristics made songs successful in the 2010s!

## Overview
The primary objective of this study is to predict the charting success of 2010s songs based on solely their audio characteristics and genre classifications. 

## Project Data
For this project we use 3 main datasets: 

- hits_dataset.csv: Spotify audio features for 11,959 songs that appeared on the Billboard Hot 100.
- nonhits_dataset.csv: Spotify audio features for 899,068 songs by “hit artists” (artists that had at least one charting song) that did not chart.
- artists.csv: Metadata for 11,518 artists, including their associated genres.

This dataset required cleaning, and post-cleaning we were left with a dataset consisting of 7,392 songs (3,696 hits and 3,696 non-hits), which was comprised of all remaining hits and a random sample of non-hit songs equal to the number of hits (post-cleaning). To account for potential bias in the random sample of non-hits selected, the results presented below are an average of model performance across five different random samples of non-hit songs.

## Methodology
To predict song success, we implemented two classification models: LASSO (L1) and Ridge (L2) regression. These models were selected to deal with the multicollinearity between musical features which was observed during our exploratory data analysis. When fitting the models, we use 5-fold cross validation as well as a 80/20 train/test split.

Additionally, to isolate exactly how much the audio characteristics of a song matters versus its genre classification, we compare versions of the models with and without the song's genre as a predictor.


## Results
To evaluate our models we considered 3 primary metrics:
- Accuracy: The percantage of correct hit/non-hit predictions.
- F1 Score: The balance between precision and recall.
- ROC-AUC: The model's ability to distinguish between the two classes across various thresholds.

When genre was included, both our LASSO and Ridge models reached approximately 69% accuracy, and reported average F1 and ROC-AUC scores of 0.72 and 0.75, and 0.73 and 0.75 respectively. We find that when genre is included in the model, the most influential predictors for both models are all genre-based. 

When genre is not included in the model, both our LASSO and Ridge models again perform similarly, but accuracy falls by approximately 3%. Although accuracy falls slightly, this suggests that audio characteristics themselves carry significant weight regardless of how the song is categorized. Under this specification, the most influential predictors for both models in order of importance are: instrumentalness, explicitness, loudness, liveness, speechiness, and valence.

## Want to Know More?
If you are interested in learning more please visit our project website!
