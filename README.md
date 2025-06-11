
![A collage of popular movies](Images/image-4.png)

# Box Office Blueprint: Data-Driven Insights for Microsoft's Movie Studio Launch

## Authors

- [Hafsa M.Aden](https://www.linkedin.com/in/hafsa-m-aden-330451223/)
- [Ryan Karimi](https://www.linkedin.com/in/ryan-karimi-39a701326/)
- [Elizabeth Ogutu](https://www.linkedin.com/in/elizabeth-ogutu-36222b1a6/)
- [Rose Muthini](https://www.linkedin.com/in/syomiti-muthini-03849a153/)


<sub><i>Phase 2 Project, Moringa Data Science Program.</i></sub>

## Project Overview
This project aims to guide the establishment of a new movie studio by providing actionable insights into the key factors driving box office success. We explore data from IMDB, The Movie Database (TMDb), and the finaancial numbers to understand what types of movies perform well at the box office. The goal is to extract patterns in genres, ratings, and other characteristics to guide the studio’s production strategy.

## Project Collaboration
We used [Notion](https://www.notion.so/Group-Project-Box-Office-Analysis-20adb8fbd6cf804cb0b6d1bf27be4ef2) to manage our project timeline, assign tasks, and track contributions. This helped ensure smooth coordination across the team.

## Business Objectives
The new movie studio lacks experience in movie making and needs insights to:
- Identify successful movie characteristics.
- Pinpoint profitable genres.
- Determine optimal budget ranges.
- Strategize release timings to maximize box office revenue.

## Data Understanding
The dataset used for this project combines information from multiple sources, each offering unique and complementary insights into movie attributes and box office performance. Below is a breakdown of the data sources used and the specific datasets obtained from each.

###  Data Sources and Datasets

1. [Box Office Mojo](https://www.boxofficemojo.com/) 
Provides comprehensive box office earnings of other studios including (domestic and international) revenue data.
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


### Exploratory Data Analysis (EDA)

We performed basic data cleaning using Python, including converting data types where necessary, removing missing values that could significantly impact our analysis, and identifying potential outliers.
New columns were added based on the needs of the analysis or the outcomes we wanted. We also carried out exploratory analysis to understand data distributions and spot anomalies early in the process. 
To maximize the usefulness of the data, we merged datasets to enrich the information available allowing us to have a better understand of the business problem.

## Analysis Overview
To address the business problem of helping a new movie studio with no prior movie making experience, we structured our analysis around these key pillars:

#### a) Financial Metric Performance
- We analyzed financial data to understand what makes a movie financially successful. Using production budget, gross earnings, and calculated metrics like profit and Return on investment (ROI), we identified patterns in profitability across diffrent budget ranges and time periods. This helped us determine cost effective production strategies and the financial risks involved in different investment levels.

- We also applied regression model to quantify the impact of Production budget on financial outcomes like Return on investment(ROI). 

#### b) Market Landscape
To understand the industry dynamics, we conducted a competitive analysis of global box office trends to identify the top studios and examine their revenue patterns over time.


#### c) Influence of Talent
We also looked at the impact of directors, producers, and lead actors on movie performance. By linking cast and crew data with box office returns, we checked whether specific individuals consistently drive higher profitability or audience engagement. This aims to support informed hiring decisions for the studio.


#### d) Audience Preference
We explored ratings, genre trends, and runtime distributions to better understand what types of content resonate most with audiences. By segmenting movies by genre, rating, and popularity metrics, we gained insight into audience preference. This enables the studio to tailor content to audience tastes while balancing creative goals and market viability.


#### e) Basic Movie Meta data for Strategic Decision Making
Finally, we considered general movie attributes such as release year, language, and runtime to identify seasonal trends, optimal movie lengths, and how content success has evolved over time. These are critical for shaping release strategies and production planning.

For a detailed breakdown of the analysis, please refer to the full notebook: [Box_Office.ipynb](Final%20merged%20file.ipynb)


## Key Findings & Results

We created an interactive Tableau dashboard to present the results of the analysis in a clear and accessible way.


[View the tableau Dashboard](https://public.tableau.com/app/profile/ryan.karimi1348/viz/Tableuaproject_17494898725590/Dashboard1?publish=yes)

![Dashboard](Images/Dashboard%20Image.png)

To access the presentation, refer to the link below:
[View the Presentation](Presentation.pdf)


### Observation

1. Financial Metric Performance
- Low to mid-budget films (under \$50M) tend to yield higher ROI and lower financial risk, while very high-budget movies (\$200M+) show highly variable returns.
- Production budget alone has minimal predictive power for ROI, emphasizing the need to consider additional factors like marketing and talent.
- The box office industry is volatile with no consistent yearly revenue growth.

2. Market Landscape:
- Leading studios demonstrate fluctuating revenue patterns, highlighting the importance of continuous market research and adaptability.

3. Audience Preferences:
- Genres such as Fantasy, Animation, and Drama consistently receive higher viewer satisfaction and stable box office performance.
- Action and Sci-Fi are popular but come with more mixed reviews and higher variability.
- Clear genre positioning and movie runtimes between 60 and 120 minutes are associated with better audience reception.
- Release timing and seasonal trends play a crucial role in maximizing audience turnout and revenue.
- Optimal runtimes align with industry norms (\~100–110 minutes), supporting audience preferences and market success.


### Recomendation

- Production budget alone does not reliably predict financial success. The studio should diversify investment and allocate resources strategically, factoring in marketing, distribution, and talent costs to maximize ROI.

- Prioritize collaboration with directors, producers, and lead actors who have consistently demonstrated positive impact on movie performance to improve profitability and audience engagement.
 
- Tailoring movie content to align with our audience preferences, while balancing creativity, will enhance market reception and box office returns.

- Understanding seasonal trends and optimal runtimes can improve audience turnout and overall performance.  Strategic scheduling of releases is recommended.
 
- Continuous market research is essential to stay ahead in a rapidly evolving industry by actively tracking top studios’ revenue patterns helps identify emerging trends and potential market gaps.


## Conclusion

Our analysis provides a foundational understanding to guide the launch of a new movie studio. However, there are some limitations and challenges to consider:
- The dataset does not capture the full financial cycle such as marketing budgets and revenue splits with theatres. These missing variables are critical for developing a comprehensive financial picture.
- The rise of streaming platforms like Netflix, Amazon Prime, and Disney presents both challenges and opportunities, which are not fully reflected in the data. The new studio should explore hybrid release strategies to adapt to this evolving landscape.

We encourage the stakeholders to expand their definition of success beyond traditional financial metrics like ROI and to include:
- Audience ratings and critical reception
- Streaming platform viewership,
- Award nominations and wins, which contribute to prestige and long term brand value.

While this analysis provides actionable insights into financial performance, talent influence, movie characteristics and strategic release planning of a movie, the studio’s ultimate success will rely on its ability to continuously adapt to industry shifts.