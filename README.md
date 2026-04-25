# LyriScan: A Multi-Dimensional Lyrics-Based Music Recommendation System Using Semantic, Emotion, and Topic Embeddings

LyriScan is a lyrics-based music recommendation system that leverages natural language processing to model songs across multiple dimensions. Unlike traditional approaches that rely on collaborative filtering or audio features, this system focuses on the semantic meaning, emotional tone, and thematic structure of song lyrics to generate more meaningful recommendations.

## Overview

The core idea of LyriScan is that music preference is influenced by multiple aspects of lyrics, including meaning, mood, and themes. To capture this, the system integrates three complementary representations:

* Semantic embeddings generated using a sentence transformer model
* Emotion embeddings derived from a RoBERTa-based emotion classification model
* Topic embeddings obtained through Latent Dirichlet Allocation (LDA)

Each representation captures a different perspective of the lyrics, enabling a more comprehensive recommendation process.

## Methodology

The system constructs separate FAISS indexes for semantic, emotion, and topic embeddings to support efficient large-scale similarity search. A two-stage retrieval process is applied:

1. Candidate songs are retrieved independently from each embedding space
2. Results are re-ranked using a weighted similarity function

The final recommendation is controlled by adjustable weights, allowing users to balance semantic similarity, emotional alignment, and thematic relevance.

## Dataset

The system is built on a large-scale dataset containing over 57,000 songs. Each entry includes song title, artist, and full lyrics. A preprocessing pipeline is applied, including text cleaning, tokenization, stopword removal, and lemmatization.

If the dataset is not included in this repository due to size limitations, it can be accessed here:
[Dataset Link](https://www.kaggle.com/datasets/notshrirang/spotify-million-song-dataset)

## Implementation

The system is implemented in Python and utilizes FAISS for fast similarity search in high-dimensional vector spaces. An interactive interface can be built using Streamlit to allow users to explore recommendations and adjust model parameters.

## How to Run

Install dependencies:
pip install -r requirements.txt

Run the notebook:
Music_Recommendation_System.ipynb

## Results and Insights

Experimental observations show that different weighting configurations produce distinct recommendation patterns. Semantic-focused settings emphasize meaning similarity, emotion-focused settings align songs by mood, and topic-focused settings highlight thematic consistency. A balanced configuration provides a combination of all three aspects.

## Research Status

This project is currently under active development and is being further refined for conference publication. Ongoing work includes improving evaluation methods, enhancing model performance, and extending the system for more robust real-world applications.

## Conclusion

LyriScan demonstrates that combining semantic, emotional, and thematic analysis of lyrics can significantly improve music recommendation systems. The framework provides a scalable and flexible approach to personalized music discovery.

