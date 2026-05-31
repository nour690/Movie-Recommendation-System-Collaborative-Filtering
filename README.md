# Movie Recommendation System

A Java Swing desktop application that recommends movies using heap-based collaborative filtering.

The system recommends movies in two ways:

- By selecting an existing target user
- By creating a new user profile using manual movie ratings

---

## Project Screenshots

### Target User Screen - Design Preview

![Target User Design](screenshots/target-user-design.jpeg)

### Target User Recommendation Output

![Target User Output](screenshots/target-user-output.jpeg)

### Manual Movie Rating Screen

![Manual Rating Output](screenshots/manual-rating-output.jpeg)

### Duplicate Movie Selection Validation

![Duplicate Movie Validation](screenshots/duplicate-validation.jpeg)

---

## Features

### Existing User Recommendation

- Select a target user from `target_user.csv`
- Choose number of similar users
- Choose number of movies per user
- Compute cosine similarity with users from `main_data.csv`
- Store similar users in a Max Heap
- Display movie recommendations by movie name

---

### New User Recommendation

- Select 5 different movies
- Give each movie a rating from 1 to 5
- Convert ratings into a user vector
- Compare the new user with users in `main_data.csv`
- Store similar users in a Max Heap
- Recommend movies not already rated by the user

---

## Data Structures Used

### Max Heap

Used to store users according to similarity score.

The user with the highest similarity is kept at the root.

### HashMap

Used for:

- Movie ID to movie name
- Movie ID to column index
- Column index to movie ID

### ArrayList

Used for:

- User records
- Movie names
- Recommendation results

---

## Recommendation Process

1. Read user ratings from CSV files
2. Compute cosine similarity
3. Insert users into Max Heap
4. Extract most similar users
5. Retrieve top-rated movies
6. Display `X * K` recommendations

Where:

- `X` = number of similar users
- `K` = number of movies per user

---

## Project Files

```text
src/
├── GUI.java
├── GUI2.java
├── Main.java
├── MovieRecommendationSystem.java
├── MaxHeap.java
├── HeapNode.java
└── UserRating.java

main_data.csv
movies.csv
target_user.csv
pom.xml
