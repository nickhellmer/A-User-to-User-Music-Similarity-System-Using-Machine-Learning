# A User-to-User Music Similarity System Using Machine Learning

This project builds a user-user recommendation system to match listeners with similar music preferences using only playlist data. Based on the Million Playlist Dataset (1M playlists, 2M unique tracks), the system generates synthetic user preference vectors and evaluates multiple similarity models to identify musically aligned users.

## Problem Statement
To match users with similar musical taste based solely on co-occurrence patterns in playlist data.

## Approach
- Clustered playlists using K-means to form synthetic user vectors (1k, 10k, 50k tested)
- Computed user-to-user similarity using:
  - Standard cosine similarity
  - Scaled cosine similarity
  - Soft cosine similarity with adjustable α weighting
- Evaluated matching performance using recall@N, Precision, and F1-score across different k-values

## Repository Contents

| File/Folder                                                               | Description                                                                        |
|---------------------------------------------------------------------------|------------------------------------------------------------------------------------|
| `notebooks/psuedo_user_creation_10000_playlists.ipynb`                   | Creates synthetic user vectors from playlist co-occurrence data (10k user version) |
| `notebooks/User-to-user-similarity-output.ipynb`                         | Computes similarity scores using multiple metrics                                  |
| `notebooks/User-to-user-similarity-evaluation.ipynb`                     | Evaluates model performance with precision, recall@N, and F1 metrics               |
| `reports/A_User_to_User_Music_Similarity_System_using_Machine_Learning.pdf` | Final project report                                                           |

##  Notes
- Due to file size limits, the 10k-user output dataset (~200MB) is not included. To reproduce it, run `psuedo_user_creation_10000_playlists.ipynb`.
- The two similarity notebooks use similar code; the evaluation version adds support functions and metrics to validate similarity matches.
- The `User-to-user-similarity-output.ipynb` notebook is currently configured to run on the 1k synthetic user dataset.
  To evaluate the 10k or 50k versions, you'll need to update the filepaths and variable names used when loading input data.

## Tools & Technologies
- Python (NumPy, pandas, scikit-learn, Matplotlib)
- K-means clustering
- Similarity-based recommendation modeling

## Key Insights
- Soft cosine similarity improved recall and F1 over standard cosine
- Optimal recall@N varied with the number of synthetic users and neighbors k
- The class-based implementation enabled clearer evaluation and modular tuning

## Full Report
See the final project summary and results here:  
- [MusicSimilarity_FinalReport.pdf](A_User_to_User_Music_Similarity_System_using_Machine_Learning.pdf)
