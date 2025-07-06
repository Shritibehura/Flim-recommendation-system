# 🎬 Movie Recommender System

A **content-based movie recommender system** built using Python and machine learning techniques. It suggests similar movies based on the metadata like genres, cast, crew, keywords, and overview.

## 📊 Dataset

This project uses the [TMDB 5000 Movie Dataset](https://www.kaggle.com/datasets/tmdb/tmdb-movie-metadata), which includes:

- `tmdb_5000_movies.csv`
- `tmdb_5000_credits.csv`

## 📌 Features Used for Recommendation

- **Overview** of the movie
- **Genres**
- **Keywords**
- **Top 3 Cast Members**
- **Director**

These features are combined to generate a `tags` column, which is used to calculate similarity.

## 🧰 Tech Stack

- Python
- Pandas
- NumPy
- Scikit-learn
- NLTK (PorterStemmer)
- Jupyter Notebook / Python Script

## 🔄 Workflow

1. **Data Loading and Merging**
   - Combine movie and credits data on `title`.

2. **Preprocessing**
   - Drop null and duplicate entries
   - Extract genres, keywords, cast, and director from nested JSON-like strings
   - Normalize data (remove spaces, lowercase, stemming)

3. **Feature Engineering**
   - Create a `tags` column by combining important metadata
   - Convert tags to vectors using `CountVectorizer` with top 5000 features and stop words removal

4. **Similarity Calculation**
   - Use cosine similarity to compute closeness between movie vectors

5. **Recommendation Function**
   - Returns top 5 similar movies based on input title

## 🚀 How to Use

```bash
# Step 1: Clone the repository
git clone https://github.com/yourusername/movie-recommender.git
cd movie-recommender

# Step 2: Install required packages
pip install -r requirements.txt

# Step 3: Run the script
python movie_recommender.py
