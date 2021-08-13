# Introduction to Data Visualization with Seaborn
### Course Description
Seaborn is a powerful Python library that makes it easy to create informative and attractive visualizations. This course provides an introduction to Seaborn and teaches you how to visualize your data using plots such as scatter plots, box plots, and bar plots. You’ll do this while exploring survey responses about student hobbies and the factors that are associated with academic success. You’ll also learn about some of Seaborn’s advantages as a statistical visualization tool, such as how it automatically calculates confidence intervals. By the end of the course, you will be able to use Seaborn in a variety of situations to explore your data and effectively communicate the results of your data analyses to others.

## Introduction to Seaborn
What is Seaborn, and when should you use it? In this chapter, you will find out! Plus, you will learn how to create scatter plots and count plots with both lists of data and pandas DataFrames. You will also be introduced to one of the big advantages of using Seaborn - the ability to easily add a third variable to your plots by using color to represent different subgroups.

- Making a scatter plot with lists
    - sns.scatterplot(x=gdp, y=percent_literate)
    - plt.show()
- Making a count plot with a list
    - sns.countplot(y=region)
    - plt.show()
- Making a count plot with a DataFrame
- Hue and scatter plots
    - sns.scatterplot(x="absences", y="G3", 
                data=student_data, 
                hue="location", hue_order=['Rural', 'Urban'])
- Hue and count plots
    - palette_colors = {"Rural": "green", "Urban": "blue"}
    - sns.countplot(x="school", data=student_data, hue="location", palette=palette_colors)

## Visualizing Two Quantitative Variables
In this chapter, you will create and customize plots that visualize the relationship between two quantitative variables. To do this, you will use scatter plots and line plots to explore how the level of air pollution in a city changes over the course of a day and how horsepower relates to fuel efficiency in cars. You will also see another big advantage of using Seaborn - the ability to easily create subplots in a single figure!

## Visualizing a Categorical and a Quantitative Variable
Categorical variables are present in nearly every dataset, but they are especially prominent in survey data. In this chapter, you will learn how to create and customize categorical plots such as box plots, bar plots, count plots, and point plots. Along the way, you will explore survey data from young people about their interests, students about their study habits, and adult men about their feelings about masculinity.

## Customizing Seaborn Plots
In this final chapter, you will learn how to add informative plot titles and axis labels, which are one of the most important parts of any data visualization! You will also learn how to customize the style of your visualizations in order to more quickly orient your audience to the key takeaways. Then, you will put everything you have learned together for the final exercises of the course!