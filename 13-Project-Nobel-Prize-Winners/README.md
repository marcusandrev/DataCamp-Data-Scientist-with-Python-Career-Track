# Project: A Visual History of Nobel Prize Winners

The Nobel Prize is perhaps the world's most well known scientific award. Every year it is given to scientists and scholars in chemistry, literature, physics, medicine, economics, and peace. The first Nobel Prize was handed out in 1901, and at that time the prize was Eurocentric and male-focused, but nowadays it's not biased in any way. Surely, right?

Well, let's find out! What characteristics do the prize winners have? Which country gets it most often? And has anybody gotten it twice? It's up to you to figure this out.

The dataset used in this project is from The Nobel Foundation on Kaggle.

### Task 1: Instructions
Load the required libraries and the Nobel Prize dataset.

- Import the pandas library as pd.
- Import the seaborn library as sns.
- Import the numpy library as np.
- Use pd.read_csv to read in datasets/nobel.csv and save it into nobel.
- Show at least the first six entries of nobel using the head() method, setting n=6 or greater.

### Task 2: Instructions
Count up the Nobel Prizes. Also, split by sex and birth_country.

- Count the number of rows/prizes using the len() function. Use the display() function to display the result.
- Count and display the number of prizes for each sex using the value_counts() method.
- Count the number of prizes for each birth_country using value_counts() and show the top 10 using head(). Do not use display().


### Task 3: Instructions
Create a DataFrame with two columns: decade and proportion of USA-born Nobel Prize winners that decade.

- Add a usa_born_winner column to nobel, where the value is True when birth_country is "United States of America".
- Add a decade column to nobel for the decade each prize was awarded. Here, np.floor() will come in handy. Ensure the decade column is of type int64.
- Use groupby to group by decade, setting as_index=False. Then isolate the usa_born_winner column and take the mean(). Assign the resulting DataFrame to prop_usa_winners.
- Display prop_usa_winners.

### Task 4: Instructions
Plot the proportion of USA born winners per decade.

- Use seaborn to plot prop_usa_winners with decade on the x-axis and usa_born_winner on the y-axis as an sns.lineplot. Assign the plot to ax.
- Fix the y-scale so that it shows percentages using PercentFormatter.


### Task 5: Instructions
Plot the proportion of female laureates by decade split by prize category.

- Add the female_winner column to nobel, where the value is True when sex is "Female".
- Use groupby to group by both decade and category, setting as_index=False. Then isolate the female_winner column and take the mean(). Assign the resulting DataFrame to prop_female_winners.
- Copy and paste your seaborn plot from task 4 (including axis formatting code), but plot prop_female_winners and map the category variable to the hue parameter.

### Task 6: Instructions
Extract and display the row showing the first woman to win a Nobel Prize.

- Select only the rows of 'Female' winners in nobel.
- Using the nsmallest() method with its n and columns parameters, pick out the first woman to get a Nobel Prize.


### Task 7: Instructions
Extract and display the rows of repeat Nobel Prize winners.

- Use groupby to group nobel by 'full_name'.
- Use the filter method to keep only those rows in nobel with winners with 2 or more prizes.

### Task 8: Instructions
Calculate and plot the age of each winner when they won their Nobel Prize.

- Convert the nobel['birth_date'] column to datetime using pd.to_datetime.
- Add a new column nobel['age'] that contains the age of each winner when they got the prize. That is, year of prize win minus birth year.
- Use sns.lmplot (not sns.lineplot) to make a plot with year on the x-axis and age on the y-axis.


### Task 9: Instructions
Plot how old winners are within the different price categories.

- As before, use sns.lmplot to make a plot with year on the x-axis and age on the y-axis. But this time, make one plot per prize category by setting the row argument to 'category'.


### Task 10: Instructions
Pick out the rows of the oldest and the youngest winner of a Nobel Prize.

- Use nlargest() to pick out and display the row of the oldest winner.
- Use nsmallest() to pick out and display the row of the youngest winner.


### Task 11: Instructions
Assign the name of the youngest winner of a Nobel Prize to youngest_winner. The first name will suffice.