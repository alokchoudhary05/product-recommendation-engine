# E-Commerce Product Recommendation System

A comprehensive machine learning-based recommendation system that suggests products to users using multiple collaborative and content-based approaches. This project demonstrates proficiency in data preprocessing, exploratory data analysis, and implementing various recommendation algorithms.

## Project Overview

This project builds a multi-faceted recommendation engine for e-commerce platforms. It processes 5,000 product records, performs extensive data cleaning and preprocessing, and implements four distinct recommendation strategies to optimize user experience and drive sales.

## Features

- **Rating-Based Recommendations**: Identifies trending products by calculating average ratings and review counts, providing a simple yet effective way to showcase popular items
- **Content-Based Filtering**: Recommends similar products using TF-IDF vectorization and cosine similarity on product descriptions and tags. This approach ensures users discover items related to their interests
- **Collaborative Filtering**: Suggests products based on similar users' preferences using user-item interaction matrices and cosine similarity between users. This captures implicit user preferences
- **Hybrid Recommendations**: Intelligently combines content-based and collaborative filtering results to provide diverse and accurate recommendations

## Technologies Used

- **Python Libraries**: 
  - Pandas: Data manipulation and analysis
  - NumPy: Numerical computing
  - Scikit-learn: Machine learning algorithms (TF-IDF, Cosine Similarity)
  - Spacy: Natural Language Processing for tag extraction and text processing
  - Matplotlib & Seaborn: Data visualization

- **Techniques**: 
  - TF-IDF (Term Frequency-Inverse Document Frequency) vectorization
  - Cosine Similarity for measuring item and user similarity
  - NLP-based tag extraction from product descriptions
  - Pivot tables for user-item interaction matrices

## Dataset

- **Size**: 5,000 e-commerce products with 10 key attributes
- **Attributes**: Unique ID, Product ID, Rating, Reviews Count, Category, Brand, Name, Image URL, Description, and Tags
- **Data Processing**: 
  - Handles missing values through imputation (mean for ratings, median for reviews, "Unknown" for categorical)
  - Removes duplicates
  - Standardizes column names for clarity
  - Extracts numeric values from ID fields

## Project Structure

```
├── Product Recommendation.ipynb    # Main notebook with all implementations
├── product_data_5k.tsv             # Raw product dataset
├── models/
│   ├── clean_data.csv              # Preprocessed product data
│   └── trending_products.csv       # Top-rated products output
└── README.md                        # Project documentation
```

## Key Algorithms Explained

### 1. Content-Based Filtering
- Uses TF-IDF vectorization to convert product tags and descriptions into numerical vectors
- Calculates cosine similarity between item vectors to find semantically similar products
- Returns top N most similar products to a given item
- **Advantage**: Doesn't require user ratings; works well for new products

### 2. Collaborative Filtering
- Creates a user-item interaction matrix with ratings
- Computes user-to-user similarity using cosine similarity
- Identifies similar users and recommends items they rated highly
- **Advantage**: Captures implicit user preferences and discovers serendipitous recommendations

### 3. Hybrid Approach
- Merges recommendations from both content-based and collaborative filtering
- Removes duplicates to provide diverse suggestions
- **Advantage**: Combines strengths of both methods for improved accuracy and variety

## How to Use

1. Open `Product Recommendation.ipynb` in Jupyter Notebook
2. Run cells sequentially to load and preprocess data
3. Call recommendation functions with specific parameters:


## Data Processing Pipeline

1. **Data Loading**: Read TSV file with product information
2. **Data Cleaning**: Handle missing values, remove duplicates, extract numeric IDs
3. **Feature Engineering**: Extract and combine tags from Category, Brand, and Description using NLP
4. **Exploratory Analysis**: Statistical summaries, distribution visualizations, and heatmaps
5. **Vectorization**: Convert text to numerical format using TF-IDF
6. **Similarity Computation**: Calculate cosine similarity matrices for recommendations

## Results & Outputs

- Top 10 trending products ranked by rating and reviews
- Similar product recommendations for any given item
- Personalized recommendations for specific users
- Combined hybrid recommendations balancing quality and diversity

<!-- ## Future Enhancements

- Implement matrix factorization (SVD) for improved collaborative filtering
- Add deep learning approaches (neural collaborative filtering)
- Incorporate temporal data to capture trending patterns
- Deploy as REST API for production use
- Add A/B testing framework to evaluate recommendation quality
- Implement cold-start problem solutions for new users/products -->
