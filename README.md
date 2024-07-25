# Module 6 Challenge

Using the starter code provided, the assignment was to query the NYT API for movies with the word "love" in tthe headline.  Then, use the list of titles from the NYT data to retrieve movie_id from the TMDB API--and then get query with movie_id to get TMDB API details for each movie in the NYT list.

## 1. Part 1:
- The final outputs were reviews_df (dataframe) and titles_list (list).  Both data objects will be used to query the TMDB API (part 2) and then merge (part 3) with the TMDB dataframe.
- The reviews_df object contains 200 rows and 17 columns.
- To get 200 movies, I used a for loop to cycle through 20 pages--using range(0,19).  I assinged 19 as variable so I could process less pages when doing development and testing.
- Within a try - except block, I looped through the reviews and append key:value pairs for the response to review_list.
- Another part of the exercise was to use the provided lambda function to extract headline.main title from between '\u2018' and '\u2019 Review' characters int the string and store it to a new column called 'title.'
- Using the supplied function, I was able to apply the function to the dataframe to convert the keywords column from a list of dictionaries to a string.
- Last step was to create a list of the titles using to_list() and save it to titles_list which will be used in Part 2.

## 2. Part 2:
- The final output for Part 2 was a tmdb_df (TMDB DB dataframe), which contained 154 rows and 15 columns.
- Looping through the titles from titles_list (NYT data), I submitted an API query to TMDB to retrieve the movie_id.  And then did another query with the movie_id to get TMDB movie details.
- The next major step was to create the result_dict {} to capture the key:value pairs from the TMDB API JSON--including the three separate lists created for genre, spoken language, and production countries.
- The end product was the tmdb_df dataframe to be used in Part 3.

## Part 3:
- First step was to merge reviews_df into the tmdb_df.  The result was the merged data set (on title) called merged_movie_df.
- Using two for loops, I fixed genres, spoken_languages, and production_countries by converting these columns to a string.  And then removing special characters.
- The remaining steps were to drop byline.person, then clean and reindex the data.  I did check for rows with NA values, but did not remove the columns with null values.  There was no instruction to do so in the challenge.
- After resetting the index, the last step was to output the cleaned and reindex dataframe--merged_movie_df_clean, to a csv file.
- The final output was cleaned_merged_data.csv stored in the output folder.

---
Challenge completed by Louis Canjar for the UNC AI Bootcamp


