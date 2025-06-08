
![A collage of popular movies](https://cdn.mos.cms.futurecdn.net/rDJegQJaCyGaYysj2g5XWY-1280-80.jpg.webp)

# Box Office Blueprint Data Driven Insights for Microsoft Movie Studio Launch
Phase 2 Project, Moringa Data Science Program

## Authors
- Hafsa Mohamed Aden
- Ryan Karimi
- Elizabeth Ogutu
- Rose Muthini

## Project Overview
This project aims to guide the establishment of a new movie studio by providing actionable insights into the key factors driving box office success. We explore data from IMDB, The Movie Database (TMDb), and the finaancial numbers to understand what types of movies perform well at the box office. The goal is to extract patterns in genres, ratings, and other characteristics to guide the studio’s production strategy.


## Business Problem
The new movie studio lacks experience in movie making and needs insights to:
- Identify successful movie characteristics.
- Pinpoint profitable genres.
- Determine optimal budget ranges.
- Strategize release timings to maximize box office revenue.

## Data Understanding
The dataset used for this project combines information from multiple sources, each offering unique and complementary insights into movie attributes and box office performance. Below is a breakdown of the data sources used and the specific datasets obtained from each.

###  Data Sources and Datasets

1. [Box Office Mojo](https://www.boxofficemojo.com/) 
Provides comprehensive box office earnings, including (domestic and international) revenue data.
   - bom.movie_gross.csv.gz 

2. [IMDB (Internet Movie Database)](https://www.imdb.com/) 
Comprehensive movie database featuring production details, cast and crew (including directors, writers, actors, and producers), user ratings and votes, as well as metadata such as title, release year, runtime, genre, and biographical information.
   - imdb.title.crew.csv.gz
   - imdb.title.akas.csv.gz
   - imdb.title.ratings.csv.gz
   - imdb.name.basics.csv.gz
   - imdb.title.basics.csv.gz
   - imdb.title.principals.csv.gz

3. [The Movie Database (TMDb)](https://www.themoviedb.org/) 
Collaborative movie database providing community sourced metadata such as popularity, vote count, and original language
   - tmdb.movies.csv.gz

4. [The Numbers](https://www.the-numbers.com/) 
Provides financial data on movies, including production budgets, worldwide gross, and estimated profits
   - tn.movie_budgets.csv.gz


###  Datasets Used in Analysis
After performing an initial analysis, cleaning, and merging of data, we used the following datasets for analysis:

- `tn.movie_budgets.csv.gz` → Used for financial and studio performance analysis (budget, gross, profit, ROI).
- `bom.movie_gross.csv.gz` → Supplementary financial data, focusing on domestic and international gross.
- `imdb.title.basics.csv.gz` → Used to extract genre, runtime, and title information.
- `imdb.title.akas.csv.gz` & `imdb.title.principals.csv.gz` → Contains Movie Metadata like genre, runtimes, directors, actors, and producers for talent influence.


### Data Preparation

We performed basic data cleaning using Python, including converting data types where necessary, removing missing values that could significantly impact our analysis, and identifying potential outliers. New columns were added based on the needs of the analysis or the outcomes we wanted. We also carried out exploratory analysis to understand data distributions and spot anomalies early in the process. 
To maximize the usefulness of the data, we merged datasets to enrich the information available allowing us to have a better understand of the business problem.

## Exploratory Data Analysis (EDA)

### Financial Performance Metric
We analyzed over a century’s worth of movie data to evaluate key financial performance variables:
- production budget
- domestic gross
- worldwide gross

After cleaning the dataset, we calculate key profitability metrics such as profit and Return on Investment (ROI), enabling us to assess how efficiently movies converted budget into revenue.

Key Insights:
- Low to mid budget movies (under $50M) tend to have higher ROI, making them more profitable relative to cost and less financially risky.
- High budget movies ($200M+), while capable of generating massive profits, show wide flactuations in returns, making them riskier investments for new studios.
- The $50M–$200M budget range appears to be a strategic sweet spot, balancing strong profit potential with manageable risk.

We also found out that domestic success is a strong predictor of international earnings, but a few movies succeed internationally despite poor local performance highlighting the importance of understanding global markets.

Historically, movie investments were most efficient during the 1930s–1970s with significantly higher average ROI than in more recent decades. While modern ROI has stabilized, this insight could  offer valuable inspiration remakes or modern adaptations of older high-return models could be worth exploring.

By analyzing profit trends across budget brackets, ROI distribution over time, and the relationship between budget and returns, our work offers clear, data-backed guidance for investors and stakeholders. 

The insights help in shaping a cost-effective, market-aware production strategy aimed at long term  financial sustainability.

#### Regression Modelling

To test whether production budget could reliably predict ROI, we applied a simple linear regression model. The results showed that budget alone has almost no predictive power (R² = 0.0069). 
Production budgets don’t account for other crucial factors like marketing, distribution cuts, and backend deals. For more accurate forecasting, we’d need more dataset that reflects the full financial lifecycle of a movie. Simply spending more on production doesn’t guarantee higher returns. 

![Forecasting ROI from Production Budgets](Images/forecasting_roi_from_production_budgets.png)


