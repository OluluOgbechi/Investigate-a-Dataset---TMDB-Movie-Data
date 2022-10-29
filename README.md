# Udacity Project (Investigate-a-Dataset - TMDB-Movie-Data)

## About the Dataset
This data set contains information about 10,000 movies collected from The Movie Database (TMDb), including user ratings and revenue. The data was provided from [this link](https://s3.amazonaws.com/video.udacity-data.com/topher/2018/July/5b57919a_data-set-options/data-set-options.pdf) provided by Udacity.

## Questions for Analysis
1.  Which genres are most popular from year to year?
2.  What kinds of properties are associated with movies that have high revenues?

## Data Wrangling
The data was downloaded directly to local machine using this [link](https://www.google.com/url?q=https://d17h27t6h515a5.cloudfront.net/topher/2017/October/59dd1c4c_tmdb-movies/tmdb-movies.csv&sa=D&ust=1532469042115000) and was then read into jupyter notebook using pandas. The contents of the data were also assessed. 

### Additional Wrangling
- Create dictionary called 'genre_years_dict' to store the number of times each genre of movie was released for each year.
- Create new dataframe called 'trend_df' with two columns, containing the year and most popular genre for each year.
- Create new columns for each genre. These columns will only contain 1s and 0s. Each new column will be for a new genre. For each distinct genre column, the values of that column will have a value of 1 if the movie in that row is of that genre, and it will have a value of 0 if the movie in that row is not of that genre. These new columns were named using the format genre_<genre_name> (e.g genre_Drama).
- Create new columns for each distinct Production Company, and use a value of 1 if the movie in the column was made by that Production Company, and a value of 0 if it wasn't. The focus was on Production companies that occur more than 30 times in the dataset. The new columns were named using the format production_<production_company_name> (e.g production_Universal Studios).
- Create new columns for each distinct value in the cast column, and use a value of 1 if the movie in the column was made by that Production Company, and a value of 0 if it wasn't.

## Exploratory Analysis 
This section of the report delves into the main analysis and seeks to address and answer the proposed research questions.
- For Question 1, bar charts were used to show the yearly trend for each year. Each bar chart showed the number of movies released for each year for each genre. Then a stacked bar chart was used to view the trendsin genre and show which genre is most common.

- For Question 2, Pearson's correlation was used to find out how each of the new columns created from additional wrangling correlate with each other. The reason for using the Pearson correlation is because of the data transformation where more features were brought out with the creation of new columns containing 0s and 1s. The focus was on the columns that correlated with the adjusted revenue (revenue_adj) by more than 10 percent. A correlation table, sorted in descending order, was created to see which properties were more related with high revenue. This was then visualized using a bar chart.

## Conclusions
This part of the report summarizes and concludes the results from the analysis. The following findings were made:
- For Question 1, Drama genre is often the most popular genre but few times Comedy takes the lead.
- For the Question two, we can see that different features that weren't readily available from the original dataset are very important for which movies tend to have high revenues.
- Production companies like **Twentieth Century Fox Film Corporation** and actors like **Harrison Ford** are slightly good indicators of a movie that may have high revenues.
