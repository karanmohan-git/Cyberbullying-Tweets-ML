# Cyberbullying Tweet Classification

This project aims to build and evaluate a machine learning model capable of classifying tweets into different categories of cyberbullying. The goal is to create a tool that can help identify and flag toxic content on social media platforms.

## Dataset

The dataset used for this project is the "Cyberbullying Tweets" dataset from Kaggle. It contains tweets that have been classified into six categories: `age`, `ethnicity`, `gender`, `religion`, `other_cyberbullying`, and `not_cyberbullying`.

-   **Source:** [Kaggle Cyberbullying Classification Dataset](https://www.kaggle.com/datasets/andrewmvd/cyberbullying-classification/data?select=cyberbullying_tweets.csv)
-   **File:** `cyberbullying_tweets.csv`

## Methodology

The project follows the **Cross-Industry Standard Process for Data Mining (CRISP-DM)** methodology, covering the entire lifecycle from business understanding to model evaluation.

## Project Workflow

1.  **Data Understanding:** The dataset was loaded and analyzed to understand the distribution of the different cyberbullying types. The classes were found to be well-balanced.

2.  **Data Preparation:** A comprehensive text preprocessing pipeline was created to clean the raw tweet data. This included:
    *   Converting text to lowercase.
    *   Removing URLs, user mentions (`@username`), and punctuation.
    *   Removing common English stopwords.
    *   **Lemmatization** to reduce words to their root form.

3.  **Feature Engineering:** The cleaned text was converted into numerical features using `TfidfVectorizer`, which captures the importance of words in the tweets. N-grams (both single words and pairs of words) were used to retain more context.

4.  **Modeling:** Several classification models were trained and compared:
    *   Logistic Regression
    *   Multinomial Naive Bayes
    *   Linear SVM
    *   **LightGBM (Gradient Boosting)**

## Results & Key Findings

The final **LightGBM model** was the best performer, achieving an accuracy of **~83%** on the test set.

A key finding from the classification report is that the model performs exceptionally well on categories defined by strong keywords (e.g., `age`, `ethnicity`, `religion`), often scoring above 95% on them. However, it finds it more challenging to classify nuanced and broad categories like `not_cyberbullying` and `other_cyberbullying`.

This highlights a classic challenge in NLP: models based on "bag-of-words" are excellent at finding keyword-based patterns but struggle with understanding the true context and meaning of language.

## Acknowledgement

This Jupyter Notebook and analysis were developed with the assistance of **Google's Gemini AI**.
