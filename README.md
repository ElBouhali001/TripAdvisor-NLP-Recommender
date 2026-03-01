# TripAdvisor NLP Recommender System

**Authors:** Houssam ElMouedden & Lucas PIEL
**Course:** M1 Data & AI, ESILV (Paris)

## Project Overview

This project is an Information Retrieval (IR) system designed to act as a recommendation engine for trips and experiences.

The core hypothesis is that **similar places (restaurants, hotels, attractions) are described by users using similar vocabulary**. If this hypothesis is true, we can recommend a similar experience relying entirely on user reviews.

**Key Constraint:** The recommendation model relies *only* on the text of the reviews. Any other metadata (like location, price range, or category) is strictly excluded from the input and is only used to evaluate the model's accuracy.

## Data & Preprocessing

The system uses a TripAdvisor dataset consisting of user reviews and place metadata.

* **Filtering:** Only English-language reviews were processed.
* **Document Aggregation:** Because the number of reviews varies heavily between places, we aggregated all reviews for a specific place into a single document. This provides a single, uniform mathematical representation for each location.
* **Splitting:** The unique places were randomly split 50/50 into a training set (the queries) and a testing set (the search corpus).

## Models Designed

1. **The Baseline (BM25):** We implemented the standard BM25 retrieval algorithm (`rank-bm25`) to establish a baseline for term-frequency matching.
2. **Custom Model (TF-IDF + Cosine Similarity):** We designed a custom model that vectorizes the text using TF-IDF. To eliminate noise and focus on the most impactful descriptive
