
![A collage of popular movies](https://cdn.mos.cms.futurecdn.net/rDJegQJaCyGaYysj2g5XWY-1280-80.jpg.webp)

# Box Office Blueprint Data Driven Insights for Microsoft Movie Studio Launch
Phase 2 Project, Moringa Data Science Program

## Authors
- Hafsa Mohamed Aden
- Ryan Karimi
- Elizabeth Ogutu
- Rose Muthini

## Project Overview
This project aims to guide the establishment of a new movie studio by providing actionable insights into the key factors driving box office success. We explore data from IMDB, The Movie Database (TMDb), and the numbers to understand what types of movies perform well at the box office. The goal is to extract patterns in genres, ratings, and other characteristics to guide the studio’s production strategy.

## Business Problem
The new movie studio lacks experience in filmmaking and needs insights to:
- Identify successful movie characteristics.
- Pinpoint profitable genres.
- Determine optimal budget ranges.
- Strategize release timings to maximize box office revenue.

## Data Understanding
The dataset used for this project combines information from multiple sources, each offering unique and complementary insights into movie attributes and box office performance. Below is a breakdown of the data sources used and the specific datasets obtained from each.

###  Data Sources and Datasets

1. [Box Office Mojo](https://www.boxofficemojo.com/) - Provides detailed box office revenue information.
 - `bom.movie_gross.csv.gz` – Contains gross earnings for movies, including domestic and international revenue data.

2. [IMDB (Internet Movie Database)](https://www.imdb.com/) - Database showing production details, cast/crew, and user ratings.
   - `imdb.title.akas.csv.gz` – Includes international titles and alternative titles.
   - `imdb.title.basics.csv.gz` – Contains basic information about films such as title, year, runtime, and genre.
   - `imdb.title.crew.csv.gz` – Lists directors and writers of each film.
   - `imdb.title.ratings.csv.gz` – Shows user ratings and number of votes.
   - `imdb.title.principals.csv.gz` – Lists principal cast and crew including actors, actresses, producers, etc.
   - `imdb.name.basics.csv.gz` – Provides basic information about people (e.g., birth year, profession).

3. [The Movie Database (TMDb)](https://www.themoviedb.org/) - Movie database offering community sourced metadata.

   - `tmdb.movies.csv.gz` – Contains metadata about movies including popularity, vote count, and language.

4. [The Numbers](https://www.the-numbers.com/) - Shows financial data related to movies.

   - `tn.movie_budgets.csv.gz` – Includes production budgets, worldwide gross, and calculated profits.

5. [Rotten Tomatoes](https://www.rottentomatoes.com/) - Contains reviews was considered for sentiment and critic score references.


###  Datasets Used in Analysis
After performing an initial assessment, cleaning, and merging of data, we used the following datasets for analysis:

- `tn.movie_budgets.csv.gz` → Used for financial and studio performance analysis (budget, gross, profit, ROI).
- `bom.movie_gross.csv.gz` → Supplementary financial data, focusing on domestic and international gross.
- `imdb.title.basics.csv.gz` → Used to extract genre, runtime, and title information.
- `imdb.title.akas.csv.gz` & `imdb.title.principals.csv.gz` → Used to identify directors, actors, and producers for cast analysis.















































### Data source
Below are the sources of the data :
    -1. [IMDB](https://www.imdb.com/)
    -2.  [Rotten Tomatoes](https://www.rottentomatoes.com/)
    -3. [TheMovieDB](https://www.themoviedb.org/)
    -4.  [The Numbers](https://www.the-numbers.com/)
    -5. [Box Office Mojo](https://www.boxofficemojo.com/)













1. Box Office Mojo:
   - bom.movie_gross.csv.gz

2. IMDB:
   - imdb.title.crew.csv.gz
   - imdb.title.akas.csv.gz
   - imdb.title.ratings.csv.gz
   - imdb.name.basics.csv.gz
   - imdb.title.basics.csv.gz
   - imdb.title.principals.csv.gz

3. TMDB:
   - tmdb.movies.csv.gz

4. The Numbers:
   - tn.movie_budgets.csv.gz

After initial analysis and some data cleaning, the datasets which we used for our analysis were:

- a) tn.movie_budgets.csv.gz for financial & studio data
- b) bom.movie_gross.csv.gz for financial data
- c) imdb.title.basics.csv.gz for genre data
- d) imdb.title.akas.csv.gz for Directors, Actors & Producers data