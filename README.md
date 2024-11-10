# Movie & Genre Analysis 🎬📊

## Table of Contents 📑

1. [Introduction](#introduction)
2. [Data Description](#data-description)
3. [Objectives](#objectives)
4. [Software Used](#software-used)
5. [Data Cleaning](#data-cleaning)
6. [Data Exploratory Analysis](#data-exploratory-analysis)
7. [Findings](#findings)
8. [Conclusion](#conclusion)
9. [Further Links](#further-links)

---

## Introduction 📚

As part of the Le Wagon Data Analytics Bootcamp, my team and I explored the profitability and popularity of movie genres over the last 50 years. This project aims to identify trends, profitable genres, and understand how factors like marketing, distribution, and social context influence box office performance. By analysing both US box office data and a comprehensive movie dataset, we uncovered insights into the film industry.

---

## Data Description 📈

We used the following datasets for this analysis:

1. **Full TMDB Movies Dataset 2024 (1M Movies)**:  
   A comprehensive dataset from [Asaniczka on Kaggle](https://www.kaggle.com/datasets/asaniczka/tmdb-movies-dataset-2023-930k-movies) containing data on 1,000,000 movies, including titles, ratings, release dates, revenue, genres, and more.

2. **US Box Office Data**:  
   Webscraped from [BoxOfficeMojo](https://www.boxofficemojo.com/chart/ww_top_lifetime_gross/), providing weekly gross data for deeper analysis of movie revenues.

3. **Barbenheimer Marketing Data**:  
   Data from [Comscore](https://www.comscore.com/Insights/Blog/Barbenheimer-and-Redefining-Movie-Marketing-Strategies), analysing the simultaneous release strategy of *Barbie* and *Oppenheimer*, and its impact on audience engagement and revenue.

---

## Objectives 🎯

Our analysis aimed to answer the following questions:

- Which genres generate the highest revenue? 💰
- How has genre popularity changed over time? 📅
- What countries are the largest movie distributors? 🌍
- How has revenue changed over time? 📈
- Which production companies generate the most revenue? 🎬
- What are the seasonal trends in profitability? 📅💸
- What is the risk vs reward for each genre? ⚖️
- How does social context affect box office performance? 🧠
- How do marketing campaigns influence box office results? 📢

---

## Software Used 💻

The following tools were used in the analysis:

- **Python** (using Google Colab) 🐍
- **pandas** 🧑‍💻
- **numpy** 🔢
- **matplotlib** 📊
- **plotly.express** 📈
- **seaborn** 📉
- **BigQuery** 🗃️
- **Looker** 📊

---

## Data Cleaning 🧹

Before analysis, the data was cleaned to ensure accuracy:

1. **Removed Adult Content**:  
   Filtered out adult content to focus on general audience films.

2. **Dropped Irrelevant Columns**:  
   Removed columns such as `Spoken_languages`, `original_title`, and `imdb_id` as they were not useful for the analysis.

3. **Filtered English-Language Movies**:  
   Kept only English-language films to ensure relevance for a global audience.

4. **Focused on the Last 50 Years**:  
   Limited the dataset to movies from the past 50 years to capture current trends.

5. **Dropped Null Rows**:  
   Removed rows with missing data in key columns like `title`, `vote_count`, `revenue`, and `budget`. Replaced null values in `production_companies` and `country` with 'unspecified'.

6. **Handled Duplicates**:  
   Removed duplicates (e.g., *Blazed 2009*) where conflicting data existed.

7. **Concatenated Title & Release Year**:  
   Combined movie titles and release years to distinguish between movies with identical titles but different releases.

8. **Dropped the Release Year Column**:  
   Removed the separate `release_year` column after concatenation to avoid redundancy.

9. **Filled Nulls in 'Genre'**:  
   Replaced null values in the `genre` column with 'other' to prevent data loss.

10. **Splitting the 'Genres' Column**:  
    Split the `genres` column into separate columns for each genre then encoded the data (1 for presence, 0 for absence).

11. **Duplicating Rows for Multiple Genres**:  
    Duplicated rows for films with multiple genres (e.g., *Avengers*), so each genre was counted correctly.

---

## Data Exploratory Analysis 🔍

We followed these steps in our exploratory analysis:

1. **Genre Count**:  
   Counted the number of movies in each genre to understand distribution.

2. **Average Popularity**:  
   Calculated the average popularity score for each genre to identify audience engagement.

3. **Average Vote**:  
   Calculated the average vote for each genre to assess critical reception.

4. **Average Revenue**:  
   Calculated the average revenue for each genre to determine financial success.

5. **Average Budget**:  
   Calculated the average budget per genre to understand typical studio investments.

6. **Total Revenue by Genre**:  
   Calculated total revenue per genre by replacing binary values with actual movie revenue.

7. **Total Budget by Genre**:  
   Similarly, calculated total budget per genre by replacing binary values with actual movie budgets.

8. **Total Profit by Genre**:  
   Calculated total profit for each genre by subtracting total budget from total revenue.

---

## Findings 🔍

- **7.2k Movies Analysed**:  
  We analysed 7,200 movies over 50 years to uncover trends.

- **Revenue & Profit**:  
  Movies generated **614.72 billion dollars** in revenue and made **394.73 billion dollars** in profit.

- **Most Popular Genre**:  
  **Drama** was the most popular genre, followed by **Comedy** and **Thriller**.

- **Largest Movie Production Country**:  
  The **United States** produced the most films, with a significant drop in production in **2020** due to COVID-19.

- **Top Genres by Market Share & Profit**:  
  **Adventure**, **Action**, and **Comedy** dominate in both popularity and profitability. **Thriller**, **Family**, and **Science Fiction** follow closely behind.

- **US Box Office Trends**:  
  US box office revenue dipped in **2020** but is recovering as cinemas reopen.

- **Top Production Companies**:  
  **Marvel Studios**, **Pixar**, **Walt Disney Pictures**, and **Lucasfilm** were the top companies by revenue.

- **Seasonal Trends**:  
  **June**, **December**, and **May** are the most profitable months for movie releases, while **January**, **February**, and **August** are the least profitable.

- **Franchise Success**:  
  Movies like **Avatar**, **Shrek**, and **Frozen** are released during peak months and generate significant profits.

- **Profit vs Budget**:  
  - Some horror movies, such as **The Blair Witch Project**, achieved high profits despite having a low budget.  
  - **History**, **Western**, and **War** genres typically do not make back their budgets.  
  - **Adventure**, **Fantasy**, and **Family** films tend to be more successful, often recouping their budget in around 3 weeks.

- **Miramax Insights**:
  - Miramax produced iconic films such as The King’s Speech and Sin City.
  - Despite its success, Miramax ceased film production after 2017, following Harvey Weinstein’s departure.
 
- **Barbie vs Oppenheimer**:  
  Both films showed steadily increasing grosses as more theatres screened them. **Oppenheimer** won more awards despite **Barbie’s** commercial success.

---

## Conclusion 🎯

- **The US dominates the movie production industry**, with the highest number of films produced, although 2020 saw a noticeable decline due to the pandemic.
- **Drama** is the most popular genre, but **Action** and **Comedy** dominate in terms of revenue and market share.
- The **advent of franchise movies** like **Avatar**, **Shrek**, and **Frozen** shows the importance of established brands in generating box office success.
- **The box office is rebounding post-2020**, with seasonal trends revealing that certain months, particularly **June, December, and May**, are crucial for maximising profitability.
- **Low-budget films** can still achieve high profits, as seen with films like **The Blair Witch Project**, while **History, Western, and War** genres tend to underperform.
- **Miramax’s production history** shows a sharp decline in output post-2017, reflecting possible industry shifts.
- **Barbie and Oppenheimer** are prime examples of how strong word-of-mouth and increasing theatre distribution can lead to sustained box office success, with **Oppenheimer** securing more awards despite Barbie’s commercial success.

---

## Further Links 🔗

1. [Click here to read our code](https://colab.research.google.com/drive/1FAbPUWW7yt4Ro-cjzkQcoh4bYP-NviWO?usp=sharing)  
2. [Click here to view our presentation](https://lookerstudio.google.com/reporting/b1c5c346-edee-4f72-9ab1-8982c092e421)
