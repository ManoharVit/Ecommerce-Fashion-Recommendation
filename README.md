# Personalized-Fashion-Recommendation
Based on past interactions with customer and product metadata, including product description and appearance, recommend 12 products that are quite relevant to the customer.

## Introduction

Kaggle H&M Personalized Fashion Recommendations competition, where the challenge was to build a recommendation engine to predict which articles a customer would buy in a particular week starting on September 23, 2020.

### Key highlights of our work:
* Analyzed over 34GB of publicly available H&M datasets from Kaggle, which included images, articles, customer data, and time-series transaction data.
* Cleaned and merged unstructured and messy datasets to create a cohesive dataset.
* Integrated customer and transaction data to identify purchase patterns, and used classification techniques to categorize them into their respective article clusters.
* Developed a personalized fashion recommendation model that achieved an accuracy of 79%.

As Yuval Noah Harari points out in "Homo Deus," the same mathematical laws apply to both biochemical and electronic algorithms. This project aims to represent human decision-making processes as algorithms that process multidimensional input information and generate outputs in the form of decisions.

## Recommendations Everywhere

Recommendations have become integral to our daily lives, whether it's Spotify creating personalized playlists or Netflix suggesting TV series and movies. Similarly, H&M aims to save customers time by providing personalized clothing recommendations.

### Example Scenario: Emily's Decision-Making Process

1. **Need Identification**: Emily realizes she needs a new jacket for a cold evening out with friends.
2. **Search and Evaluation**: She browses H&M's online store and decides she prefers a coat over a jacket.
3. **Style and Preference**: Emily's style influences her decision, and she chooses a classic, cream coat within her budget.
4. **In-Store Experience**: She visits a local H&M store, tries on the coat, and decides to buy it along with matching pants and an umbrella.

## Data Sources

### Customers
The customer table contains information such as age, club membership status, and newsletter frequency. There are over 1.3 million customers to provide recommendations for.

### Transactions
Transactional data represents a customer's interests, needs, and style, with over 31 million transactions recorded.

### Article Hierarchy
Articles are described using multiple dimensions, such as product group, department, section name, garment group, perceived color name, and graphical appearance.

### Article Descriptions
Detailed descriptions of articles provide additional information about products, which can be transformed into embeddings to enhance ML model performance.

### Article Images
Images of articles were included in the dataset, offering another dimension for feature generation.

## Recommendation Engines

When thinking about recommendations, content-based and collaborative filtering models are the two most popular ML algorithms in this field.

### Content-Based Filtering
Content-based filtering uses item features to recommend other items similar to what the user likes, based on their previous actions or explicit feedback. For example, if a customer likes a leopard-print pattern, the model will recommend other products with the same pattern.

### Collaborative Filtering
Collaborative filtering uses similarities between users and items simultaneously to provide recommendations. This allows for serendipitous recommendations, where an item is recommended to user A based on the interests of a similar user B. The embeddings are learned automatically, without relying on hand-engineering of features.

## Tools and Frameworks

### Python Libraries

- **CUDF**: GPU DataFrame library for fast, parallel processing.
- **Pandas**: Data manipulation and analysis.
- **NumPy**: Numerical computing.
- **Scipy**: Scientific computing and technical computing.
- **Scikit-Learn**: Machine learning algorithms and tools.
- **TensorFlow / Keras**: Deep learning frameworks.
- **PyTorch**: Another popular deep learning framework.
- **Matplotlib / Seaborn**: Data visualization.
- **Plotly**: Interactive graphing library.
- **NLTK / SpaCy**: Natural language processing.
- **LightGBM / XGBoost**: Gradient boosting frameworks for efficient modeling.
- **TQDM**: Progress bar for loops.
- **Pillow (PIL)**: Image processing.
- **WordCloud**: Generate word clouds.
- **OpenCV**: Image processing.
- **WandB**: Experiment tracking and visualization.
- **Bokeh**: Interactive visualizations.

## Conceptualization

### ML Model: General Need for Clothing

1. **Expectations**: The model should estimate the probability of a customer needing a particular clothing type in a given time period.
2. **Solution**: Use propensity-to-buy models and time-series seasonality forecasting models.

### ML Model: Customer’s Style

1. **Expectations**: The model should sort articles within a product category based on how well they match a customer's style.
2. **Solution**: Generate features using image and text embeddings, then apply content-based and collaborative filtering models.

### ML Model: Available Stock / Lifetime of an Article

1. **Expectations**: Estimate the probability of an article being offered in a given week.
2. **Solution**: Use models to predict sales volume per article per week.

### ML Model: The Customer's Final Decision

1. **Concept**: Create a final-decision model that is an ensemble of all the individual models.
2. **Solution**: Use AutoML to generate final scores and validate the model.

## Final Concept

The solution involves generating features using multiple techniques, storing them in a feature store, and using an ensemble of ML models to generate recommendations. The expected input to the final ensemble model is a table with `customer_id`, `week_id`, and `article_id`, with columns representing results from various ML models.

## Summary

Our approach to the H&M Personalized Fashion Recommendations competition involved understanding the decision-making process, generating relevant features, and applying a combination of ML models to create a robust recommendation system. The project highlights the importance of data-driven insights in predicting customer behavior and enhancing the shopping experience.

## References

- [H&M Personalized Fashion Recommendations Kaggle Competition](https://www.kaggle.com/competitions/h-and-m-personalized-fashion-recommendations)
