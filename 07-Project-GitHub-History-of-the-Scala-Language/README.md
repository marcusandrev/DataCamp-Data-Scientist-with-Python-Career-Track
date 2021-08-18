# Project: The GitHub History of the Scala Language
- Open source projects contain entire development histories, such as who made changes, the changes themselves, and code reviews. In this project, you'll be challenged to read in, clean up, and visualize the real-world project repository of Scala that spans data from a version control system (Git) as well as a project hosting site (GitHub). With almost 30,000 commits and a history spanning over ten years, Scala is a mature language. You will find out who has had the most influence on its development and who are the experts.

- The dataset includes the project history of Scala retrieved from Git and GitHub as a set of CSV files.

### Task 1
Import the dataset into the notebook. All the relevant files can be found in the datasets subfolder.

- Import the pandas module.
- Load in 'datasets/pulls_2011-2013.csv' and 'datasets/pulls_2014-2018.csv'as pandas DataFrames and assign them to pulls_one and pulls_two respectively.
- Similarly, load in 'datasets/pull_files.csv' and assign it to pull_files.

### Task 2
Combine the two pulls DataFrames and then convert date to a DateTime object.

- Append pulls_one to pulls_two and assign the result to pulls.
- Convert the date column for the pulls object from a string into a DateTime object.

### Task 3
Merge the two DataFrames.

- Merge pulls and pull_files on the pid column. Assign the result to the data variable.

### Task 4
Calculate and plot project activity in terms of pull requests.

- Group data by month and year (i.e. '2011-01', '2011-02', etc), and count the number pull requests (pid). Store the counts in a variable called counts.
- There are a number of ways to accomplish this.
- One way would be to create two new columns containing the year and month attributes of the date column, and then group by these two variables.
- Plot counts using a bar chart (this has been done for you).

### Task 5
Plot pull requests by user.

- Group the pull requests by each user and count the number of pull requests they submitted. Store the counts in a variable called by_user.
- Plot the histogram for by_user.

### Task 6
Identify the files changed in the last ten pull requests.

- Select the last ten pull requests and name the resulting DataFrame last_10.
- Merge last_10 with the pull_files DataFrame on pid, assigning the result to joined_pr.
- Identify the unique files in joined_pr (via the file column) using set().

### Task 7
Identify the top 3 developers that submitted pull requests to src/compiler/scala/reflect/reify/phases/Calculate.scala.

- Select the pull requests that changed that file and name the resulting DataFrame file_pr.
- Count the number of changes made by each developer and name the resulting DataFrame author_counts.
- Print the top 3 developers.

### Task 8
Identify the most recent ten pull requests that touched src/compiler/scala/reflect/reify/phases/Calculate.scala.

- Select the pull requests that touched the file and name the resulting DataFrame file_pr.
- Merge file_pr with the pulls DataFrame on the pid column and name the resulting DataFrame joined_pr.
- Using set(), create a set of users for the ten most recent pull requests.

### Task 9
Plot the number of pull requests for two developers, over time.

- Using the pulls DataFrame, select all of the pull requests by these two developers and name the resulting DataFrame by_author.
- Fill in the groupby parameters to count the number of pull requests submitted by each author each year. That is, group by user and the year property of date.
- Plot counts_wide using a bar chart.

### Task 10
Calculate the number of pull requests submitted by a developer to a file each year.

- Select the pull requests submitted by the authors from the data DataFrame and name the results by_author.
- Select the pull requests from by_author that affect the file and name the results by_file.
- Transform grouped into a wide format using pivot_table. Name the results by_file_wide.