# Project: The Android App Market on Google Play
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


https://github.com/Radu-Goguta/DataCamp-Projects/blob/master/The%20Android%20App%20Market%20on%20Google%20Play/Android%20App%20Google%20Play.ipynb
