🎬 Movie Recommendation System

This project implements a Content-Based Movie Recommendation System using natural language processing and vector similarity techniques. The system recommends movies based on content similarity rather than collaborative user behavior, making it suitable for cold-start scenarios.

🔁 System Workflow Overview
[ Raw TMDB Dataset ]
        │
        ▼
[ Data Cleaning & JSON Parsing ]
        │
        ▼
[ Space Collapse Transformation ]
        │
        ▼
[ Unified Tags Generation ]
        │
        ▼
[ Count Vectorization (5,000 Features) ]
        │
        ▼
[ Cosine Similarity Matrix ]
        │
        ▼
[ Top-N Recommendation Engine ]

⚙️ Key Workflow Engineering Phases
1. Feature Parsing & Truncation
Converts stringified JSON attributes into structured Python objects using ast.literal_eval.
Extracts:
Top 3 billed cast members
Director from the crew data
Removes unnecessary metadata to reduce dimensional noise.
2. Space Collapse Transformation
Eliminates inner-word spaces to avoid token fragmentation.

Example:

Johnny Depp → JohnnyDepp
Prevents the vectorizer from treating common first names as independent tokens.
3. Bag-of-Words Representation
Merges selected attributes into a single textual field called tags:
Genres
Keywords
Overview
Cast
Director
Converts all text to lowercase.
Applies stop-word filtering.
Maps tokens into a 5,000-word vocabulary using CountVectorizer.
4. Geometric Similarity Matching
Uses Cosine Similarity to compute angular distance between movie vectors.
Ensures similarity is invariant to document length.
Enables semantic proximity detection across high-dimensional feature space.

📂 Repository Structure
.
├── data/
│   └── tmdb_5000_dataset.zip      # Compressed TMDB Movies & Credits CSV files
├── notebooks/
│   └── movie_recommender.ipynb    # End-to-end Google Colab execution notebook
├── src/
│   └── main.py                    # Modular, production-ready Python script
└── README.md                      # Project documentation and setup guide

🚀 Getting Started (Google Colab / Local Execution)
1️⃣ Clone the Repository
git clone https://github.com/YOUR_USERNAME/YOUR_REPOSITORY_NAME.git
cd YOUR_REPOSITORY_NAME
2️⃣ Extract the Dataset

The dataset is compressed to bypass GitHub file-size constraints.

Option A: Using Terminal (Linux / macOS / Colab)
unzip data/tmdb_5000_dataset.zip -d ./
Option B: Using Python
import zipfile

with zipfile.ZipFile('data/tmdb_5000_dataset.zip', 'r') as zip_ref:
    zip_ref.extractall('./')

print("Dataset extraction completed successfully.")

After extraction, the following files will appear:

tmdb_5000_movies.csv
tmdb_5000_credits.csv

3️⃣ Install Dependencies
pip install pandas numpy scikit-learn

▶️ Running the Recommendation Engine
Function Signature
recommend_movies(movie_title, top_n=5)
Example Execution
recommend_movies('The Dark Knight', top_n=5)
📊 Sample Output
==================================================
TOP 5 RECOMMENDATIONS FOR: THE DARK KNIGHT
==================================================
No.  Movie Title                     Similarity Score
--------------------------------------------------
1    The Dark Knight Rises            0.7001
2    Batman Begins                   0.6325
3    Batman Returns                  0.2887
4    Batman Forever                  0.2764
5    Inception                       0.2621

🛠 Technology Stack
Component	Tools Used
Data Processing	Pandas, NumPy
Feature Engineering	CountVectorizer
Similarity Computation	Cosine Similarity
JSON Parsing	ast.literal_eval
Platform	Google Colab / Local Python

📌 Key Highlights
Fully content-driven recommendation pipeline
Handles large datasets via compression
Academically structured and final-year project ready
Easily extendable to:
TF-IDF
Weighted features
Hybrid recommendation systems
📄 License

This project is intended for academic and educational use.
