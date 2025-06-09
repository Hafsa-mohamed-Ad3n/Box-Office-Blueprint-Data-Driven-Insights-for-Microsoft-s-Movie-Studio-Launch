
![A collage of popular movies](https://miro.medium.com/v2/resize:fit:1400/format:webp/1*NPBh2prSO3USXoRA5CwaNg.png)

# Box Office Blueprint: Data-Driven Insights for Microsoft's Movie Studio Launch

## Authors
- Hafsa Mohamed Aden
- Ryan Karimi
- Elizabeth Ogutu
- Rose Muthini

<sub><i>This project was developed as part of the Phase 2 Project in the Moringa Data Science Program.</i></sub>

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

This helps in shaping a cost-effective, market-aware production strategy aimed at long term  financial sustainability.

![Return on Investment vs Production Budget](Images/Return%20on%20Investment(ROI)%20Vs%20Production%20Budget.png)

![Profit Distribution by Budget Bracket](Images/Production%20Distribution%20by%20Budget%20Bracket.png)

![Average ROI by Release Year](Images/Average%20ROI%20by%20Release%20Year.png)



#### Regression Modelling

To test whether production budget could reliably predict ROI, we applied a simple linear regression model. The results showed that budget alone has almost no predictive power (R² = 0.0069). 
Production budgets don’t account for other crucial factors like marketing, distribution cuts, and backend deals. For more accurate forecasting, we’d need more dataset that reflects the full financial lifecycle of a movie. Simply spending more on production doesn’t guarantee higher returns. 

![Forecasting ROI from Production Budgets](Images/Forecasting%20ROI%20from%20Production%20Budgets.png)


### competitive (market) analysis

Our dataset contains various movie studios along with their domestic and international gross earnings. To calculate each studio’s total gross, we summed their domestic and international revenues. We then grouped the data by studio to compare overall earnings. The aim was to conduct a market analysis to identify leading studios based on global performance.

![Top 10 Studios by Global Box Office](Images/Top%2010%20Studios%20by%20Global%20box%20office.png)

We also analyzed global box office revenue trends over the years to better understand industry cycles. As the chart below shows, revenue does not increase consistently year over year, highlighting the volatile nature of the movie industry.

This highlights the importance of:
- Building a resilient business model
- Timing market entry wisely
- Developing risk mitigation strategies (e.g., genre diversification, leveraging streaming platforms like Netflix)

![Global Box Office Revenue by Year](Images/Global%20box%20office%20Revenue%20by%20Year.png)


### Information about the Movies

We explored existing movie data to understand trends in genres, ratings, runtimes, and the influence of talent, to identify where the business could succeed.

- Drama is a dominant genre and blends well with others. For a new studio, focusing on Drama and Drama Hybrids (Drama-Romance, Drama-Comedy) could meet wide audience demand and offer storytelling flexibility

- The industry leans heavily toward R and NR-rated movies:
   - If the studio wants creative freedom, NR may be attractive. 
   - If aiming for mainstream adult audiences, R-rated films are a safer bet.
   - For family-friendly content, PG or PG-13 are ideal but more competitive.

The studio should target making movies with runtime of 100–110 minutes because it aligns with current norms and audience attention spans. Longer runtimes tend to align with PG-13 and R-rated films, which dominate the market

Certain directors and writers consistently produce more films, suggesting strong brand power and proven reliability. For a new studio, partnering with experienced talent could drive visibility and long-term success.

![Common Movie Genres](Images/Most%20Common%20Movie%20Genres.png)
![Distribution of Ratings](Images/Distribution%20of%20Rating.png)
![Average Movie Runtime by Rating](Images/Average%20Movie%20Runtime%20by%20Rating.png)
![Top Directors](Images/Top%20Movie%20Directors%20by%20the%20number%20of%20movies.png)  
![Top Writers](Images/Top%20movie%20Writers%20by%20the%20number%20of%20movies.png)


### Understanding Audience Preference
We also analyzed audience engagement (popularity) and viewer satisfaction (ratings) across genres and genre combinations. This helps inform content strategy by balancing what attracts viewers with what they enjoy.

- To maximize reach and satisfaction, prioritize Fantasy and Animation. 
- For strong audience pull, Action works, but quality control is crucial to avoid polarizing reviews.


We explored the trade-off between a movie’s popularity and how well it's received by audiences.
- Movies with viewer ratings of 6+ tend to show higher popularity.
- Action, Sci-Fi, and Adventure genres tend to be highly popular but polarizing, they draw large audiences, but reviews vary.
- Drama, Animation, and Family genres have more balanced and consistent reception.

For consistent critical success and family appeal, lean into Drama and Animation.


Genre blending can enhance both appeal and quality. Creating Adventure-Fantasy or Sci-Fi crossovers may yield high engagement and satisfaction. Pairing Action with Thriller ensures wide marketability.. 

![Average Popularity by Genre](Images/Average%20Popularity%20by%20Genre.png)
![Vote Average vs Genre Popularity](Images/Vote%20Average%20vs%20Genre%20Popularity.png)
![Top 10 Genre Pairs by Audience Preference](Images/Top%2010%20Genre%20Pairs%20by%20Audience%20Preference.png). 

