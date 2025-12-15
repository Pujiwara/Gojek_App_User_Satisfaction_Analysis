# Gojek_App_Reviews
Project Title:
Gojek App User Satisfaction Overview-Based On User Reviews & NLP Sentiment Analysis

Dashboard Preview:
![page1](https://github.com/Pujiwara/Pictures/blob/main/gojek%20app%20reviews_page-0001.jpg)
![page2](https://github.com/Pujiwara/Pictures/blob/main/gojek%20app%20reviews_page-0002.jpg)
![page3](https://github.com/Pujiwara/Pictures/blob/main/gojek%20app%20reviews_page-0003.jpg)

Description:
This project analyzes customer satisfaction and user sentiment based on 215,000+ user reviews of the Gojek mobile application written in Bahasa Indonesia.
The objective is to go beyond star ratings by extracting implicit customer sentiment from review text and combining it with explicit ratings to uncover hidden dissatisfaction, UX issues, and product quality risks.
An end-to-end analytics pipeline was built using PostgreSQL, Python (NLP), and Power BI, transforming raw unstructured text into actionable business insights through an executive-level dashboard.

Tools Used:
1. PostgreSQL: data storage, cleaning, and modeling
2. Python: NLP-based sentiment analysis. Pandas, SQLAlchemy, NLTK (stopwords)
3. Power BI: data modeling, DAX measures, and dashboard visualization

Key Insights:
1. User ratings remain relatively high, while textual sentiment indicates weaker emotional satisfaction.
2. A strong correlation exists between ratings and sentiment, validating the effectiveness of the NLP approach.
3. Negative feedback is dominated by recurring issues such as order cancellations, driver behavior, and system errors. These issues are not isolated incidents, but rather indicate systemic UX and policy problems that require product and policy-level intervention, not merely customer service handling.
4. Certain app versions show extreme spikes in negative reviews. Some versions record negative review rates exceeding 20%, and in some cases reaching 100% (although likely with smaller review volumes). This strongly indicates instability in the app release quality control process.

Dataset:
https://www.kaggle.com/datasets/ucupsedaya/gojek-app-reviews-bahasa-indonesia

1. Data Ingestion & Profiling (PostgreSQL)
- Loaded raw review data into PostgreSQL
- Performed data validation: Row count consistency, Missing value checks, Rating distribution analysis, Review text length analysis
- Added a unique review_id as a primary key

2. Data Cleaning & Preparation
- Standardized text format: Lowercasing. URL, symbol, and punctuation removal
- Removed Indonesian stopwords
- Applied stemming using Sastrawi
- Prepared cleaned review text for sentiment scoring

3. Sentiment Analysis (Python NLP)
- Implemented a lexicon-based sentiment scoring approach tailored to Bahasa Indonesia
- Defined positive and negative word dictionaries
- Converted review text into: Numeric sentiment scores, Sentiment labels (positive / neutral / negative)
- Optimized text processing to handle large-scale data efficiently
- Stored enriched sentiment results back into PostgreSQL

4. Data Modeling & Feature Engineering
- Combined rating, sentiment score, sentiment label, and app version into a curated analytical view
- Created satisfaction categories based on rating thresholds
- Prepared data for time-series, correlation, and segmentation analysis

Power BI Dashboard Structure:
The dashboard is organized into two main pages:
1. Executive Overview
2. Sentiment & Rating Deep Dive
3. Negative Feedback Analysis



