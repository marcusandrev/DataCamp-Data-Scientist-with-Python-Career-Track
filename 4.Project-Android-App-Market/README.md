# Guided Project: The Android App Market on Google Play
- This project lets you apply the skills from Joining Data with pandas. We recommend that you take this course before starting this project.

- The data for this project was scraped from the Google Play website. While there are many popular datasets for Apple App Store, there aren't many for Google Play apps, which is partially due to the increased difficulty in scraping the latter as compared to the former.

### Task 1
Import the data, drop duplicate rows, and inspect the data.

- Load datasets/apps.csv into a DataFrame and assign it to the variable apps_with_duplicates.
- Drop all duplicate rows from apps_with_duplicates and assign the result to apps.
- Print the total number of apps.
- Finally, display a random sample of 5 rows from apps.

### Task 2
Clean the dataset.

- Create a list named chars_to_remove that contains the following characters: + , and $.
- Create a list named cols_to_clean that contains the following column names: Installs and Price.
- For each column in cols_to_clean in the apps DataFrame, replace each character in chars_to_remove with the empty string ''.
- Note: Make sure to use an empty string '' and not a space character ' '
- Finally, print a summary of the apps dataframe using the info() function. Observe the output.
- Note: Notice that Installs and Price are still of type object and not int or float as we would have expected after removal of the special characters. We will solve this issue in the next task.

### Task 3

- Convert Installs and Price columns to float data type using astype() function.
- Verify the corrected data types by using the dtypes attribute of apps dataframe. (You can also reuse the info() function to verify the corrected data types)

### Task 4
Create data for a bar chart that shows the distribution of apps across different categories.

- Find the number of unique app categories. Save your result in num_categories.
- Count the number of apps in each category and then sort the categories in descending order of app count. Save your answer in sorted_num_apps_in_category.

### Task 5
Create a plot annotation for average app rating.

- Find the average app rating and assign it to avg_app_rating.

### Task 6
Examine the relationship between size, price, and rating of apps using jointplot(). <br />

Recall from Task #1 that we had observed some missing values in the Rating and Size columns. To make rational decisions, it is important that we do not consider these missing values in our analysis. We will work with a subset apps_with_size_and_rating_present DataFrame for this task.

- Select rows from apps where both Rating and Size values are present, ie - they are not null. Store the result in the apps_with_size_and_rating_present dataframe.
- From apps_with_size_and_rating_present, select the categories having atleast 250 apps. Assign the result to large_categories dataframe.
- Fill out x and y to create a joint plot of Rating as a function of Size.
- From apps_with_size_and_rating_present dataframe, select all Paid apps. Save the result in paid_apps.
- Fill out x and y to create a joint plot of Rating as a function of Price.

### Task 7
Use a strip plot to visualize the distribution of paid apps across different categories.

- Plot a strip plot with x-axis extending along the Price range and y-axis depicting the Category.
- Find apps priced above $200. Print the Category, App and Price columns for such apps.

### Task 8
Filter out "junk" apps.  <br />
Note: For simplicity, we will continue to use the popular_app_cats dataframe (from previous task) and not our original dataframe apps

- Select rows from popular_app_cats that contain apps priced below $100 and assign it to apps_under_100.
- Re-plot your strip plot using apps_under_100 dataframe (instead of popular_app_cats used in the previous task).

### Task 9
Prep the data for a box plot that compares the number of installs of paid apps vs. number of installs of free apps.

- From apps, filter rows where for Type == Paid, and select the Installs column and assign it to y of trace0.
- From apps, filter rows where for Type == Free, and select the Installs column and assign it to y of trace1.

### Task 10
Load the user review data and plot it to visualize sentiment of paid vs. free apps.

- Read datasets/user_reviews.csv into the reviews_df DataFrame.
- Merge apps and reviews_df DataFrames and assign the result to merged_df.
- Create a box plot with Type on the x-axis and Sentiment_Polarity on the y-axis.
