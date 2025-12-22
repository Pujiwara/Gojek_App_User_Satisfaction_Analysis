# Gojek App User Satisfaction Analysis
Project Title:
Gojek App User Satisfaction Overview-Based On User Reviews & NLP Sentiment Analysis

Dashboard Preview:
![page1](https://github.com/Pujiwara/Pictures/blob/main/gojek%20app%20reviews_page-0001.jpg)
![page2](https://github.com/Pujiwara/Pictures/blob/main/gojek%20app%20reviews_page-0002.jpg)
![page3](https://github.com/Pujiwara/Pictures/blob/main/gojek%20app%20reviews_page-0003.jpg)

Description:
This case study analyzes **user satisfaction** of the Gojek mobile application based on more than **215,000 user reviews** written in Bahasa Indonesia. The analysis aims to move beyond star ratings by extracting **implicit user sentiment from review text** and combining it with explicit ratings to uncover hidden dissatisfaction, user experience (UX) issues, and potential product quality risks.
The project was developed as an **end-to-end analytics pipeline** using **PostgreSQL, Python (Natural Language Processing), and Power BI**. It covers the entire workflow from data ingestion and cleaning, text-based sentiment analysis, to the delivery of **executive-level dashboards** that translate unstructured text data into actionable business insights. The results are intended to support product teams and stakeholders in identifying systemic issues and prioritizing improvements that directly impact user experience.

Dataset:
https://www.kaggle.com/datasets/ucupsedaya/gojek-app-reviews-bahasa-indonesia

# Analytical Approach
### Methods
The analysis follows a structured, end-to-end analytical methodology designed to transform unstructured text data into actionable insights.
- **Data Profiling & Validation**
    Raw app review data was ingested into PostgreSQL and validated through row count checks, missing value analysis, rating distribution assessment, and review text length evaluation to ensure data quality and consistency.
- **Text Pre-processing**
    Review text was standardized through lowercasing, removal of URLs, symbols, and punctuation, followed by stopword removal and stemming using Sastrawi to normalize Bahasa Indonesia text.
- **Sentiment Analysis (NLP)**
    A lexicon-based sentiment analysis approach was implemented to convert review text into numeric sentiment scores and categorical sentiment labels (positive, neutral, negative). This method enabled scalable sentiment extraction while maintaining interpretability.
- **Feature Engineering & Data Modeling**
    Sentiment results were combined with ratings, timestamps, and app version information to create a curated analytical dataset suitable for trend analysis, correlation analysis, and segmentation.
- **Insight Generation & Visualization**
    Key metrics and relationships were explored using aggregations, time-series analysis, and cross-dimensional comparisons, with insights delivered through an executive-level Power BI dashboard.

### Dashboard Structure
1. **Executive Overview**
    Provides a high-level view of overall user satisfaction, sentiment distribution, key KPIs, and temporal trends.
2. **Sentiment & Rating Deep Dive**
    Examines the relationship between star ratings and textual sentiment, including correlation patterns and satisfaction segmentation.
3. **Negative Feedback Analysis**
    Focuses on negative reviews to identify recurring issues, problematic app versions, and actionable user feedback through raw review text exploration.

### Tools
- **PostgreSQL**
    Used for data ingestion, cleaning, validation, and analytical data modeling.
- **Python (NLP)**
    Utilized for text processing and sentiment analysis using libraries such as Pandas, NLTK, and Sastrawi.
- **Power BI**
    Employed for data modeling, DAX-based metrics, and the development of interactive, executive-level dashboards.

# Key Insight
- **High Ratings Do Not Fully Reflect Emotional Satisfaction**
    While the average user rating remains relatively high, textual sentiment analysis reveals weaker emotional satisfaction. This indicates that users continue to use the app but do not consistently express positive experiences, suggesting latent dissatisfaction that is not captured by star ratings alone.
- **Certain App Versions Exhibit Disproportionately High Negative Sentiment**
    Specific app versions show sharp spikes in negative reviews, with some versions exceeding 20% negative sentiment and, in extreme cases, reaching 100% (likely with lower review volumes). This highlights instability in the app release and quality assurance process.
- **Strong Alignment Between Ratings and Sentiment Validates the NLP Approach**
    A clear correlation exists between star ratings and sentiment scores, where lower ratings consistently align with negative sentiment and higher ratings with positive sentiment. This confirms that the NLP-based sentiment analysis reliably captures user perception from unstructured text.
- **Large User Volume Masks Underlying Experience Risks**
    Despite the large number of reviews and a high proportion of positive sentiment overall, persistent negative themes and low emotional intensity signal potential long-term risks to user trust and retention if issues remain unaddressed.
- **Negative Feedback Is Driven by Systemic Issues, Not Isolated Incidents**
    Negative reviews are dominated by recurring themes such as order cancellations, driver behavior, and system errors. The repetition and consistency of these complaints indicate systemic UX and policy-related issues rather than one-off service failures.

# Business Recommendations
- **Improve Cancellation Flow and Policy Transparency**
    Redesign the cancellation process to clearly communicate user and driver responsibilities, penalties, and system behavior. Reducing ambiguity in cancellation rules can directly address one of the most common sources of user frustration.
- **Strengthen App Release Quality Control**
    Implement stricter QA testing and staged rollouts for new app versions, with close monitoring of early negative sentiment signals. App versions associated with high negative sentiment should be prioritized for investigation or rollback.
- **Leverage Sentiment Analysis as an Early Warning System**
    Integrate sentiment monitoring into the product release cycle to detect dissatisfaction trends earlier than rating-based metrics alone. Sudden drops in sentiment score can serve as leading indicators of UX or system issues.
- **Shift Focus from Reactive Support to Proactive Product Fixes**
    Since negative feedback reflects systemic problems, improvements should focus on product design, system stability, and policy alignment rather than relying solely on customer service resolution.
- **Prioritize High-Impact UX Improvements**
    Address recurring pain points identified in negative reviews—such as system errors and driver-related friction—by aligning product, operations, and policy teams around shared experience metrics.
