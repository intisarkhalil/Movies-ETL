# Movies-ETL
## Project Overview
Amazing Prime loves the dataset and wants to keep it updated on a daily basis. The Client needs to create an automated pipeline that takes in new data, performs the appropriate transformations, and loads the data into existing tables. The purpose is to create one function that takes in the three **files—Wikipedia data**, **Kaggle metadata**, and the **MovieLens rating data** and performs the ETL process by adding the data to a **PostgreSQL** database. For this analysis we use the following softwares:
- Jupyter Notebook
- PostgreSQL
- pgAdmin
## The Analysis 
### Write an ETL Function to Read Three Data Files
Using your knowledge of Python, Pandas, the ETL process, and code refactoring, write a function that reads in the three data files and creates three separate DataFrames.
1. An ETL function is written to read in the three data files
2. The function converts the Wikipedia **JSON**[]() file to a Pandas DataFrame, and the DataFrame is displayed in the ```ETL_function_test.ipynb``` file.
3. The function converts the **Kaggle metadata**[]() file to a Pandas DataFrame, and the DataFrame is displayed in the ```ETL_function_test.ipynb``` file.
4. The function converts the **MovieLens ratings**[]() data file to a Pandas DataFrame, and the DataFrame is displayed in the ```ETL_function_test.ipynb``` file.
### Extract and Transform the Wikipedia Data.
1. The TV shows are filtered out, and the wiki_movies_df DataFrame is created.
2. A try-except block is used to catch errors while extracting the ```IMDb IDs``` with a regular expression and dropping duplicate ```IDs```..
3. The extraction and transformation of the Wikipedia data in the ETL function does the following:
    - A list comprehension is used to keep columns with non-null values.
    - The non-null box office data is converted to string values using the lambda and join functions.
    - A regular expression is used to match the six elements of ```"form_one"``` of the box office data.
    - A regular expression is used to match the three elements of ```"form_two"``` of the box office data.
    - The following columns are cleaned in the Wikipedia DataFrame:
        - The box office column
        - The budget column
        - The release date column
        - The running time column
 4. The cleaned Wikipedia data is converted to a Pandas DataFrame, and the DataFrame is displayed in the ETL_clean_wiki_movies.ipynb file.
 ### Extract and Transform the Kaggle Data.
 1. The extraction and transformation of the Kaggle metadata using the ETL function does the following.
    - The Kaggle metadata is cleaned. 
    - The Wikipedia and Kaggle DataFrames are merged.
    - The following is performed on the merged Wikipedia and Kaggle DataFrames to create the ```movies_df```:
      - Unnecessary columns are dropped.
      - A function is used to fill in the missing Kaggle data.
      - The movies_df DataFrame is filtered to keep specific columns.
      - The movies_df DataFrame columns are renamed.
2. The extraction and transformation of the MovieLens ratings data using the ETL function does the following:
  - The ratings counts are cleaned.
  - The movies_df DataFrame is merged with the cleaned ratings DataFrame to create the ```movies_with_ratings_df``` DataFrame.
  - The empty values in the ```movies_with_ratings_df``` DataFrame are filled with ```“0”```.
3. The movies_with_ratings_df and the ```movies_df``` DataFrames are displayed in the ```ETL_clean_kaggle_data.ipynb``` file. 
### Create the Movie Database.
1. The data from the ```movies_df``` DataFrame replaces the current data in the movies table in the **SQL** database, as determined by the ```movies_query.png```.
2. The data from the MovieLens rating **CSV** file is added to the ratings table in the **SQL** database, as determined by the ```ratings_query.png```. 
3. The elapsed time to add the data to the database is displayed in the ```ETL_create_database.ipynb``` file.
## Results:
1. Write an ETL Function to Read Three Data Files
3. Extract and Transform the Wikipedia Data
4. Extract and Transform the Kaggle Data
5. Create the Movie Database.
