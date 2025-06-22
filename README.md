# Movie-Recommendation-System
Project Description
This project is for developing a content-based movie recommendation system with a movie metadata dataset. The system suggests movies that are similar with regard to textual information like genres, keywords, cast, director, and more.

How It Works
The suggestion is made by comparing movies according to textual similarity of their content. Here is a step-by-step overview:

1. Importing Libraries
Python libraries essential for data handling like:

numpy, pandas.

difflib for identifying close string matches:
TfidfVectorizer from sklearn for text vectorization:
cosine_similarity for movie similarity measurement.

2. Loading the Dataset
movies_data = pd.read_csv('movies.csv', low_memory=False)
Loads the dataset containing metadata of movies such as:
Title
Genres
Cast
Director
Overview
Popularity, etc.

3. Inspecting Data
movies_data.head()
Displays the first few rows, ensuring data format.
4. Data Preprocessing
Imported relevant features: ['genres', 'keywords', 'tagline', 'cast', 'director']
5. Handling missing values:
Missing values are replaced with NaN, which are then replaced with empty strings:

movies_data[feature] = movies_data[feature].fillna('')
The chosen textual features are joined into a single string:

combined_features = movies_data['genres'] + movies_data['keywords'] + .
6. TF-IDF Vectorization
Text data is transformed to numerical form using TF-IDF Vectorizer:

vectorizer = TfidfVectorizer()
feature_vectors = vectorizer.fit_transform(combined_features)
7. Similarity Calculation
Cosine similarity is computed between movies according to their feature vectors:

similarity = cosine_similarity(feature_vectors)
8. User Input for Recommendation
User enters the name of his/her favorite movie:

movie_name = input("Enter your favourite movie name:")
The system identifies the closest match using difflib.get_close_matches().

9. Retrieving Similar Movies
The system:

Retrieves the index of the matched movie.

Gets the similarity scores.

Sorts them in descending order.

Prints the top 20 similar movies to the user's input.

10. Sample Output
If the user gives as input "Iron Man", the system could suggest:

1. Up
2. Inside Out
3. The Emperor's New Groove
.
Key Features
No need for user history — purely content-based.

Flexible matching using fuzzy logic (difflib).

Handles missing data.

Uses NLP techniques for vectorization.

Technologies Used
Python

Pandas

Scikit-learn

TF-IDF (NLP)

Cosine Similarity

Jupyter Notebook

Final Summary
It is a Content-Based Movie Recommendation System that suggests movies by matching the textual content (such as genre, cast, keywords) of a movie chosen by the user. It employs TF-IDF vectorization and cosine similarity to locate and provide suggestions for movies that have similar content to the input provided by the user.
