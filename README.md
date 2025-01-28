# Book-Recommendation-System

This project is a Machine Learning-based Book Recommendation System that provides recommendations for books based on user ratings. The system filters out popular books, identifies power users, and employs a collaborative filtering approach using cosine similarity.

---

## Features
- **Data Cleaning:** Handle missing and duplicate data in the Books, Users, and Ratings datasets.
- **Popularity-based Filtering:** Identify books with a sufficient number of ratings and display the top-rated ones.
- **Collaborative Filtering:** Recommend books similar to a given book using cosine similarity on a user-item pivot table.
- **Power User Filtering:** Focus on users who have rated a minimum number of books for better recommendation quality.

---

- Required Libraries:
  - numpy
  - pandas
  - scikit-learn

---

## Datasets
The project uses three datasets:
1. `Books.csv`: Contains book metadata such as title, author, and publication year.
2. `Users.csv`: Contains user information.
3. `Ratings.csv`: Contains user ratings for books.

Ensure that all datasets are in the same directory as the script.

---

## Installation
1. Clone the repository:
   ```bash
   git clone [https://github.com/sai2290/Book-Recommendation-System.git]
   ```
2. Navigate to the project directory:
   ```bash
   cd book-recommendation-system
   ```
3. Install required dependencies:
   ```bash
   pip install numpy pandas scikit-learn
   ```

---

## Usage
1. Run the script to preprocess the data and calculate book recommendations.
   ```bash
   python book_recommendation.py
   ```
2. Use the `recommend` function to get book recommendations for a specific title:
   ```python
   recommended_books = recommend("Book Name")
   print(recommended_books)
   ```

---

## Code Description
### 1. Data Import and Cleaning
- Load datasets (`Books.csv`, `Users.csv`, `Ratings.csv`) into pandas DataFrames.
- Handle missing and duplicate values.
- Convert columns to appropriate data types.

### 2. Popularity-based Filtering
- Group books by title to calculate the number of ratings and average rating.
- Filter books with at least 250 ratings and sort them by average rating.
- Merge with `Books.csv` to retrieve metadata like author and image URL.

### 3. Power User Filtering
- Identify users who have rated at least 200 books.
- Filter the ratings data to include only these power users.

### 4. Pivot Table Creation
- Create a user-item matrix with book titles as rows, user IDs as columns, and ratings as values.
- Fill missing values with zeros.

### 5. Recommendation Function
- Compute cosine similarity scores between books.
- Retrieve the top 4 books similar to the input book (excluding itself).
- Return a list containing book titles, authors, and image URLs.

---

## Example Output
Given the input:
```python
recommend("The Da Vinci Code")
```
The output might look like this:
```python
[
  ["Angels & Demons", "Dan Brown", "http://example.com/angels_demons.jpg"],
  ["Deception Point", "Dan Brown", "http://example.com/deception_point.jpg"],
  ["Digital Fortress", "Dan Brown", "http://example.com/digital_fortress.jpg"],
  ["Inferno", "Dan Brown", "http://example.com/inferno.jpg"]
]
```

---

## Contributing
Contributions are welcome! Feel free to open issues or submit pull requests.

1. Fork the repository.
2. Create a new branch (`git checkout -b feature-branch`).
3. Commit your changes (`git commit -m 'Add new feature'`).
4. Push to the branch (`git push origin feature-branch`).
5. Open a pull request.

---

## License
This project is licensed under the MIT License. See the `LICENSE` file for details.

---
