# Music Recommendation System 🎵

This project is a lightweight, vector-based music recommendation engine built in Python. It uses audio feature data from over 1.2 million Spotify tracks (reduced for memory efficiency) to recommend similar songs using cosine similarity.

## Features

- Cleans and consolidates musical attributes into a usable dataset
- Converts audio feature sets into vector representations using `CountVectorizer`
- Computes song similarity with `cosine_similarity` from `scikit-learn`
- Includes a `recommend()` function to retrieve similar tracks by name
- Saves preprocessed data and model for future use with `pickle`

## Tech Stack

- Python, pandas, scikit-learn, pickle
- Jupyter Notebook for prototyping

## Notes

Due to hardware limitations, the dataset was sampled down to 1,000 songs. However, the system architecture supports larger datasets if run on more capable machines.

