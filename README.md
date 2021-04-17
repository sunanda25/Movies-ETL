# Movies-ETL
## Overview
Amazing prime video is the world’s largest online retailer for streaming movies and tv shows. The team at Amazing prime video would like to develop an algorithm to predict which low-budget movies released will become popular so they can buy the streaming rights. To develop the algorithm, amazing prime has decided to sponsor a hackathon. Britta, a member of the video team was given a task to provide clean datasets for the hackathon. Using an ETL (Extract, Transform, Load) process, Britta extracts the Wikipedia and Kaggle data from Wikipedia and MovieLens website, transform the datasets by cleaning and joining them together and load the cleaned datasets into a SQL database. The process is divided into four steps:

- Write an ETL function to read three data files
- Extract and Transform the Wikipedia data
- Extract and Transform the Kaggle data
- Create the Movie database

## Results
### Write an ETL Function to Read Three Data Files
- Created an extract_transform_load function to load the three data files.
- Using Pandas, the Kaggle data and MovieLens rating data is loaded and read into a DataFrame.
- Using json.load(), Wikipedia JSON file is loaded and read into a DataFrame.

![image](https://user-images.githubusercontent.com/76491891/115122044-d94a7600-9f83-11eb-96a9-191605443a98.png)

![image](https://user-images.githubusercontent.com/76491891/115122054-e6676500-9f83-11eb-93e7-50cea1ee47a6.png)

![image](https://user-images.githubusercontent.com/76491891/115122063-f3845400-9f83-11eb-9182-90e1c2dc3f9c.png)

### Extract and Transform the Wikipedia Data
- The Box office, Budget, Release date, Running time columns in Wikipedia data are extracted and cleaned.
- The cleaned data is stored in a wiki_movies_df DataFrame.

![image](https://user-images.githubusercontent.com/76491891/115122147-6392da00-9f84-11eb-8ae7-070af191b658.png)

### Extract and Transform the Kaggle Data
- Kaggle data is cleaned and merged with the wiki movies DataFrame and stored in a movies_df DataFrame. 
- Ratings data is cleaned and merged with the movies DataFrame and stored in a movies_with_ratings_df DataFrame.

![image](https://user-images.githubusercontent.com/76491891/115122172-93da7880-9f84-11eb-90e1-e8454e3be801.png)

![image](https://user-images.githubusercontent.com/76491891/115122190-a18ffe00-9f84-11eb-90c3-0240d129766e.png)

### Create the Movie Database
- Created a connection to the PostgreSQL database and add movies DataFrame, Ratings.csv files to a Movie database.
- Using a SQL query, we can see there are 6052 rows in the movies table and 1048575 rows in the ratings table.

<img width="251" alt="movies_query" src="https://user-images.githubusercontent.com/76491891/115122209-c97f6180-9f84-11eb-9614-0c1e2731a8c1.png">

<img width="260" alt="ratings_query" src="https://user-images.githubusercontent.com/76491891/115122218-d00dd900-9f84-11eb-9571-a11030459090.png">

Note: Due to a memory error issue, I was unable to read the entire dataset in the ratings.csv file. So, I used a partial dataset (104875 rows) and completed the assignment.
