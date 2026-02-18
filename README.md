# Netflix Movies Data Analysis
## Project summary

This notebook performs an end-to-end exploratory data analysis of a Netflix movies dataset to extract content trends, genre/popularity patterns, and temporal insights. The analysis cleans and reshapes genre lists, categorizes ratings, highlights popular content, and surfaces temporal patterns in film releases.

### Data sources

    - mymoviedb.csv (movies metadata: title, genre, release date, popularity, vote average, overview, language, etc.)

## Key steps & pipeline

### 1.Load & initial inspection

    - Read CSV, inspect shape and dtypes.

    - Notebook reports ~9,827 rows and 9 columns (dataset summary).

### 2.Cleaning

    - Remove non-informative columns for analysis (Overview, Poster-Url, Original_Language where not needed).

    - Convert Release_Date to datetime and extract year.

    - Trim whitespace in string columns and check for duplicates / NaNs (noted as mostly tidy).

### 3.Transformations

    - Split Genre (comma-separated) into lists and explode() the dataframe so each row contains a single genre (one genre per row per movie).

    - Create year buckets or release-year derived features for temporal analysis.

    - Categorize Vote_Average into bins/categories (e.g., popular, average, below_avg, not_popular) for grouped analysis.

### 4.EDA & Visualizations

    - Distribution plots for Popularity, Vote_Average, Duration, Release Year.

    - Top genres by count and share (bar charts / pie charts).

    - Identify movies with highest and lowest popularity and examine their genres.

    - Year-wise release analysis to find which years had the most releases.

### 5.Findings (from the notebook)

    - Dataset largely tidy with few missing values; Release_Date required casting.

    - Drama is the most frequent genre — appears as the top genre among ~19 genres.

    - A large portion of films are categorized as having high votes (the notebook binning highlights a substantial “popular” category).

    - Highest popularity film identified: Spider-Man: No Way Home (genres: Action, Adventure, Science Fiction).

    - Lowest popularity example called out in the notebook: The United States, Thread's (multi-genre including Music, Drama, War, Sci-fi, History).

    - Year 2020 shows the highest number of filmed movies in this dataset (noted in the analysis).

### 6.Conclusions & recommendations

    - Drama and Action are central to the catalog — consider prioritizing these genres for acquisition or recommendation experiments.

Use Vote_Average categories and Popularity to build a content-priority list for further testing (A/B recommendations).

    - Add content-based features (cast, director, keywords) and combine with user interactions for recommendation modeling.

## Reproducibility

    - Requirements: Python + pandas + matplotlib + seaborn (and any Excel readers if you adapt file sources).

    - Run notebook cells sequentially; data cleaning steps are commented for easy reuse.

## Suggested next steps

    - Feature engineering: extract actor/director features, keyword embeddings, runtime buckets.

    - Build a content recommendation baseline (collaborative and/or content-based).

    - Time-series analysis of release volumes by genre to forecast content acquisition needs.

    - Use supervised learning to predict popularity bucket or vote-category for new titles.

### Tech stack

    - Python (pandas, numpy, matplotlib, seaborn), Jupyter Notebook, CSV data.
