
# 🎬 Content-Based Movie Recommendation System

---

## 1. Introduction & Problem Statement

### 1.1 Project Goal 🎯
This project aims to develop a **Content-Based Movie Recommendation System** that provides personalized movie suggestions by analyzing the intrinsic attributes of movies users have previously enjoyed. Unlike collaborative filtering, this system focuses on movie characteristics such as genre, director, actors, plot keywords, and descriptions to recommend new movies with similar features.

### 1.2 Problem Statement ❗
Users often face difficulty discovering new movies aligned with their tastes due to the overwhelming volume of available films. Popularity-based or broad categorization recommendations do not capture the nuances of individual preferences, leading to poor user experience and missed opportunities for content discovery.

### 1.3 Importance of the Project 🚀
- **Enhanced User Experience:** Saves users time by proactively suggesting relevant movies.
- **Increased Content Discovery:** Helps content providers surface less popular but relevant titles.
- **Personalization:** Meets user expectations for tailored content.
- **Cold Start Problem:** Can recommend new movies based on content attributes.
- **Business Impact:** Increases user retention and engagement on movie platforms.

---

## 2. Dataset 📊

### 2.1 Source of the Dataset 🔗
The dataset used in this project was sourced from [TMDB 5000 Movie Dataset, which is sourced from Kaggle.I]. It contains detailed movie metadata including genres, cast, crew, and plot summaries.

### 2.2 Brief Description of the Dataset 📝
The dataset includes information on thousands of movies, with features such as:
- Movie Title
- Genre(s)
- Director
- Main Actors
- Plot Keywords
- Description/Overview
- Release Year

### 2.3 Link to the Dataset 🌐
You can access the dataset here: (https://www.kaggle.com/datasets/tmdb/tmdb-movie-metadata)

---

## 3. Setup & Dependencies 🛠️

Before running the project, ensure you have the following dependencies installed:

- Python 3.11.13 or above
- kagglehub
- pandas
- numpy
- scikit-learn
- nltk
- Flask (for website, optional)
- Jupyter Notebook or any Python IDE

You can install dependencies via pip:

```bash
pip install pandas numpy scikit-learn nltk flask
```

---

## 4. Download and Load Dataset 📥

Download the dataset from the provided link and load it into your Python environment using pandas:

```python
import pandas as pd

movies = pd.read_csv('movies_metadata.csv')
credits = pd.read_csv('credits.csv')
```

---

## 5. Data Preprocessing 🔄

### 5.1 Merge DataFrames 🔗
Merge the movies metadata with credits data on the movie id to consolidate relevant information:

```python
movies = movies.merge(credits, on='id')
```

### 5.2 Select Relevant Features 🎯
Select features needed for the recommendation system, such as:
- title
- genres
- cast
- crew
- overview

### 5.3 Data Exploration and Cleaning 🧹

#### 5.3.1 Data Exploration 🔍
Explore dataset to understand the distributions and check for missing values.

#### 5.3.2 Data Cleaning 🧼
Handle missing data by removing or filling nulls and correct data types.

---

## 6. Feature Engineering ⚙️

### 6.1 Feature Extraction and Transformation 🛠️

#### 6.1.1 Extracting All Names 👥
Parse and extract relevant names from the cast and crew columns.

#### 6.1.2 Extracting Top Three Actors 🎭
From the cast list, select the top three actors per movie.

#### 6.1.3 Fetching Directors Names 🎬
Identify the director from the crew data.

### 6.2 Text Preprocessing ✍️
Clean and preprocess text data (overview, keywords) by:
- Lowercasing
- Removing stopwords
- Tokenization
- Stemming/Lemmatization (if applicable)

### 6.3 Feature Construction / Feature Combination 🔗
Combine genres, director, top actors, and keywords into a single string feature for each movie.

### 6.4 Text Vectorization 🔢
Convert combined text features into numerical vectors using TF-IDF or CountVectorizer.

---

## 7. Cosine Similarity Calculation (Our Model) ➗

Calculate cosine similarity between movie feature vectors to find movies similar to a given movie:

```python
from sklearn.metrics.pairwise import cosine_similarity

cosine_sim = cosine_similarity(feature_vectors)
```

---

## 8. Create the Recommendation Function 🎯

Create a function that, given a movie title, returns the top N recommended movies based on similarity scores.

---

## 9. Test and Evaluate Our System ✅

Test recommendations with sample movies to verify relevant suggestions. Optionally, use user feedback or domain knowledge to qualitatively evaluate results.

---

## 10. Converting Recommendation Code/System into a Website 🌐

### 10.1 Advantages 👍
- Allows users to interactively get movie recommendations
- Enhances accessibility and user engagement
- Easy to deploy and maintain

### 10.2 How to Create a Website 🏗️
- Use Flask or Django to build backend APIs
- Use HTML, CSS, JavaScript for frontend UI
- Integrate recommendation logic into backend
- Deploy on platforms like Heroku or AWS

---

## 11. Conclusion & Future Work 🏁

This project successfully builds a content-based movie recommendation system that personalizes suggestions based on movie attributes. Future work may include:
- Incorporating collaborative filtering for hybrid recommendations
- Adding user rating data for enhanced accuracy
- Expanding the system to support real-time recommendations
- Improving UI/UX of the website interface

---

## 12. References 📚

- Rounak Banik. The Movies Dataset. Kaggle, 2018. [https://www.kaggle.com/datasets/rounakbanik/the-movies-dataset](https://www.kaggle.com/datasets/rounakbanik/the-movies-dataset)
- Scikit-learn documentation: https://scikit-learn.org/stable/
- Flask documentation: https://flask.palletsprojects.com/
- Natural Language Toolkit (NLTK): https://www.nltk.org/

---

## Developer 👨‍💻

- **Name:** Kalihose Migisha  
- **GitHub:** [![GitHub](https://img.shields.io/badge/GitHub-%2312100E.svg?style=for-the-badge&logo=github&logoColor=white)](https://github.com/KalihoseMigisha)  
- **Twitter (X):** [![Twitter](https://img.shields.io/badge/Twitter-%231DA1F2.svg?style=for-the-badge&logo=twitter&logoColor=white)](https://twitter.com/KalihoseMigisha)  
- **Email:** [![Email](https://img.shields.io/badge/Email-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:KalihoseMigisha@gmail.com)  

---

## Contact 📬

For questions or suggestions, please contact me via email or Twitter.

---

## License ⚖️

This project is licensed under the MIT License.  
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
