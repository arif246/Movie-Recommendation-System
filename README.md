# Movie Recommendation System

This project is a content-based movie recommendation system that suggests movies similar to a given input. By analyzing the features of each movie, such as genres, keywords, cast, and crew, the system provides tailored recommendations based on movie characteristics.
## Project Overview

The recommendation system uses natural language processing (NLP) and machine learning techniques to identify and recommend movies similar to those a user likes. The project pipeline includes data preprocessing, feature extraction, and similarity computation.

### Key Components

1. Data Preparation:
- Dataset: Uses TMDb’s movie and credits datasets, including features such as genres, keywords, cast, crew, and movie overview.
- Data Cleaning: Handles missing values and duplicates to ensure clean data for modeling.
- Feature Selection: Retains only relevant columns, including movie title, genres, keywords, cast, and crew, which are critical for content-based recommendations.

2. Feature Engineering:
- Genres, Keywords, and Cast Extraction: Extracts specific genres, keywords, and top three actors for each movie. Uses ast.literal_eval to convert stringified lists into Python - objects.
- Director Extraction: Identifies the director of each movie, focusing on their name in the crew list.
- Tags Creation: Combines relevant fields (overview, genres, keywords, cast, and director) into a single tag for each movie to represent its content.

3. Text Preprocessing:
- Text Cleaning: Converts tags to lowercase and removes whitespace for consistent formatting.
- Stemming: Applies stemming to tags to reduce words to their root forms using PorterStemmer from NLTK, ensuring similar words are unified (e.g., "liked" and "like" become "like").

4. Feature Vectorization:
- Count Vectorizer: Uses CountVectorizer from Scikit-Learn to convert tags into a matrix of token counts with a vocabulary size of 5000, excluding English stop words.
- Cosine Similarity: Calculates similarity between movies based on their vectorized tags, using cosine similarity to measure how close the movies are in feature space.

5. Recommendation Function:
- The recommend function identifies the top five movies most similar to the user’s input movie based on cosine similarity scores.

### How to Use
1. Clone the repository and install necessary dependencies.
2. Run the notebook or script, which loads the dataset, processes the data, and builds the recommendation engine.
3. Use recommend('Movie Title') to get recommendations for any movie in the dataset.
### Conclusion
This movie recommendation system provides content-based recommendations by analyzing each movie’s attributes. It demonstrates practical applications of NLP and similarity measures in building recommendation engines.
