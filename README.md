🎬 Movie Recommendation System (Content-Based)

This project is a Content-Based Movie Recommendation System that suggests movies similar to a given movie using textual features such as genre, overview, cast, and director.
It does not rely on user ratings and works purely on movie content similarity.

📌 How It Works (Simple Flow)

TMDB Dataset
   ↓
Data Cleaning & Feature Extraction
   ↓
Text Vectorization (Bag of Words)
   ↓
Cosine Similarity
   ↓
Top-N Movie Recommendations

⚙️ Features Used

Genres
Movie Overview
Keywords
Top 3 Cast Members
Director

All features are combined into a single text column and converted into vectors.

🧠 Technique Used

Count Vectorizer (5,000 features)
Cosine Similarity for measuring similarity between movies

📂 Project Structure

.
├── data/
│   └── tmdb_5000_dataset.zip
├── notebooks/
│   └── movie_recommender.ipynb
├── src/
│   └── main.py
└── README.md

🚀 How to Run

1. Extract Dataset
unzip data/tmdb_5000_dataset.zip
2. Install Dependencies
pip install pandas numpy scikit-learn
3. Run Recommendation
recommend_movies('The Dark Knight', top_n=5)

📊 Sample Output

Top 5 Recommendations for: The Dark Knight

1. The Dark Knight Rises
2. Batman Begins
3. Batman Returns
4. Batman Forever
5. Inception

🛠 Tools Used
Python
Pandas & NumPy
Scikit-learn
Google Colab
