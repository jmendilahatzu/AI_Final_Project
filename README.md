# Predicting Helpful Reviews on Amazon

## Hypothesis
It is possible to predict whether a review will be classified as "helpful" or "not helpful" based on its text and other features such as rating, verified purchase status, and word count. This analysis can help e-commerce platforms highlight relevant reviews, improving user experience and fostering trust in products.

## Data Source
The dataset used contains **7,820** records of product reviews from Amazon's **"Home and Kitchen"** category, previously filtered. The main variables include:
- **Review Text**: Product description and customer experience.
- **Rating**: Product rating (1-5 stars).
- **Verified Purchase**: Indicator of whether the purchase was verified.
- **Helpful Votes**: Number of votes indicating review usefulness.

## Methodology and Exploratory Data Analysis (EDA)
### 1. Data Cleaning and Transformations:
- Removed missing values in key columns like `text`.
- Created a binary variable `is_helpful` classifying a review as helpful if it has at least one helpful vote.
- Added a `text_length` column measuring the length of the review.

### 2. Key EDA Findings:
- Helpful reviews are significantly longer and tend to be associated with extreme ratings (1 or 5 stars).
- Verified purchases have a positive correlation with review usefulness.
- The distribution of helpful votes is skewed, with many reviews receiving no votes.

## Selected Model
We utilized **LightGBM (Light Gradient Boosting Machine)** for the following reasons:
- Efficient handling of combined tabular and textual data.
- Fast training speed and ability to process large datasets.
- Interpretability through feature importance analysis.

The review text was vectorized using **TF-IDF** to capture relevant patterns, while structured variables such as `rating`, `verified_purchase`, and `text_length` were normalized and combined with the text representations.

## Key Results
### Feature Importance:
- **TF-IDF text representations** were the most influential.
- **Verified purchase** and **text length** were also key determinants.

## Highlights of the Analysis
1. **Impact of Text**: Helpful reviews often include detailed descriptions and keywords related to the user experience.
2. **Variable Relationships**: Verified and longer reviews showed a higher probability of being considered helpful, validating their relevance.
3. **Model Scalability**: This approach can be applied to other product categories and improved with advanced models like **BERT** to capture more complex language nuances.

## Conclusions
- It is possible to predict review helpfulness by combining textual and structured data with high accuracy.
- This model can be integrated into recommendation systems to highlight relevant reviews and enhance user experience.

## Final Summary
This project demonstrates the feasibility of predicting the usefulness of a review by combining textual and structured data. Helpful reviews tend to include more detailed descriptions and user-related keywords. Additionally, **verified purchase status** and **text length** are key indicators. This analysis highlights the potential of AI in transforming how users interact with content on digital platforms, improving customer experience, and fostering product trust.
