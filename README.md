# Music Clustering Project

## 1. Project Overview

*Objective*
The objective of this project is to cluster songs based on their audio characteristics in order to discover groups of musically similar tracks. This unsupervised learning approach helps in understanding musical patterns and can be used for playlist generation, music recommendation systems, and exploratory analysis.

*Problem Statement*
Given a dataset containing audio features of songs belonging to a single genre, we aim to:

* Clean and preprocess the data
* Select meaningful audio features
* Apply clustering algorithms
* Evaluate and interpret the resulting clusters
* Visualize and export the results for further use

---

## 2. Dataset Description

The dataset (single_genre_artists.csv) contains song-level audio features and metadata. Each row represents a song, and the columns include:

* Audio features: danceability, energy, loudness, speechiness, acousticness, instrumentalness, liveness, valence, tempo, duration_ms
* Metadata (removed for clustering): track_name, artist_name, track_id

These audio features numerically describe rhythm, mood, energy, and instrumentation, making them suitable for clustering.

---

## 3. Data Exploration & Preprocessing

### Steps Performed

* Loaded the dataset using Pandas
* Inspected shape, column names, and data types
* Checked and handled missing values
* Removed duplicate rows
* Dropped non-numeric and identifier columns not required for clustering
* Visualized feature distributions to understand scale and skewness
* Normalized numerical features using StandardScaler

*Reasoning*
Clustering algorithms are distance-based, so feature scaling is essential to prevent variables with larger ranges from dominating the results.

---

## 4. Feature Selection

### Selected Features

The following features were selected to represent the musical characteristics of each song:

* danceability
* energy
* loudness
* speechiness
* acousticness
* instrumentalness
* liveness
* valence
* tempo
* duration_ms

*Justification*
These features collectively describe rhythm, mood, intensity, and acoustic properties, which are ideal for grouping similar songs.

---

## 5. Dimensionality Reduction

### Techniques Used

* *PCA (Principal Component Analysis)* for 2D visualization
* *t-SNE* for capturing non-linear relationships

*Note*
Dimensionality reduction was used only for visualization and interpretation, not as input to clustering algorithms.

---

## 6. Clustering Techniques

### K-Means Clustering

* Used the Elbow Method to identify the optimal number of clusters
* Validated cluster quality using Silhouette Score
* Applied K-Means with the selected number of clusters

### Alternative Methods

* *DBSCAN* for identifying noise and arbitrary-shaped clusters
* *Agglomerative (Hierarchical) Clustering* for hierarchical structure analysis

---

## 7. Cluster Evaluation

### Metrics Used

* *Silhouette Score* – measures cluster cohesion and separation
* *Davies–Bouldin Index* – lower values indicate better clustering
* *Inertia (K-Means)* – measures compactness of clusters

---

## 8. Cluster Interpretation

Cluster profiles were created by computing the mean of each feature per cluster.

*Example Interpretations*:

* High energy & high danceability → Party / Dance tracks
* High acousticness & low energy → Chill / Acoustic tracks
* High instrumentalness → Background / Instrumental music

---

## 9. Visualization Summary

The following visualizations were created:

* 2D scatter plots using PCA and t-SNE with color-coded clusters
* Bar charts showing average feature values per cluster
* Heatmaps comparing feature intensities across clusters
* Distribution plots (danceability, tempo, energy) within each cluster

These visualizations help both technical and non-technical stakeholders understand cluster behavior.

---

## 10. Final Output

* Cluster labels added to the original dataset
* Clustered dataset exported as CSV
* Results ready for dashboarding or recommendation use cases

---

## 11. Conclusion

This project successfully demonstrates how unsupervised learning can be applied to music data to uncover meaningful patterns. The clustering results can be leveraged for playlist generation, music discovery, and further analytics.
