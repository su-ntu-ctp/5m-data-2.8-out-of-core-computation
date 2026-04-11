# Assignment

## Brief

Write the Python codes for the following questions.

## Instructions

Paste the answer as Python in the answer code section below each question.

### Question 1

Question: Join the `metadata_pl` and `ratings_pl` DataFrames in Polars, then calculate the average rating by `genre` and by `original_language` (separately).

Answer:

```python
import polars as pl

# Join the DataFrames
joined_df = metadata_pl.join(ratings_pl, on='movieId')

# Average rating by genre
genre_ratings = (
    joined_df
    .groupby('genre')
    .agg(pl.mean('rating'))
    .sort('rating', descending=True)
)

# Average rating by original language
language_ratings = (
    joined_df
    .groupby('original_language')
    .agg(pl.mean('rating'))
    .sort('rating', descending=True)
)
```

### Question 2

Question: Calculate the average total amount for vendors with at least 5 trips from the NYC Taxi Trip Data.

Answer:

```python
import polars as pl

# Read NYC Taxi data and calculate average total amount for vendors with >= 5 trips
result = (
    pl.scan_csv("nyc_taxi_data.csv")
    .groupby('vendor_id')
    .agg([
        pl.count('total_amount').alias('trip_count'),
        pl.mean('total_amount').alias('avg_total_amount')
    ])
    .filter(pl.col('trip_count') >= 5)
    .sort('avg_total_amount', descending=True)
    .collect()
)
```

## Submission

- Submit the URL of the GitHub Repository that contains your work to NTU black board.
- Should you reference the work of your classmate(s) or online resources, give them credit by adding either the name of your classmate or URL.
