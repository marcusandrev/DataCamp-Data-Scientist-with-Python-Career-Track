# Introduction to Data Visualization with Matplotlib
### Course Description
Visualizing data in plots and figures exposes the underlying patterns in the data and provides insights. Good visualizations also help you communicate your data to others, and are useful to data analysts and other consumers of the data. In this course, you will learn how to use Matplotlib, a powerful Python data visualization library. Matplotlib provides the building blocks to create rich visualizations of many different kinds of datasets. You will learn how to create visualizations for different kinds of data and how to customize, automate, and share these visualizations.

## Introduction to Matplotlib
- Using the matplotlib.pyplot interface
    - fig, ax = plt.subplots()
    - plt.show()
- Adding data to an Axes object
    - ax.plot(seattle_weather["MONTH"], seattle_weather["MLY-PRCP-NORMAL"])
    - ax.plot(austin_weather["MONTH"], austin_weather["MLY-PRCP-NORMAL"])
- Customizing data appearance
    - ax.plot(seattle_weather["MONTH"], seattle_weather["MLY-PRCP-NORMAL"], color="b", marker="o", linestyle="--")
    - ax.plot(austin_weather["MONTH"], austin_weather["MLY-PRCP-NORMAL"], color="r", marker="v", linestyle="--")
- Customizing axis labels and adding titles
    - ax.set_xlabel("Time (months)")
    - ax.set_ylabel("Precipitation (inches)")
    - ax.set_title("Weather patterns in Austin and Seattle")
- Small multiples with shared y axis
    - fig, ax = plt.subplots(2, 1, sharey=True)
    - ax[0].plot(seattle_weather['MONTH'], seattle_weather['MLY-PRCP-NORMAL'], color = 'b')
    - ax[0].plot(seattle_weather['MONTH'], seattle_weather["MLY-PRCP-25PCTL"], color = 'b', linestyle = '--')
    - ax[0].plot(seattle_weather['MONTH'], seattle_weather['MLY-PRCP-75PCTL'], color = 'b', linestyle = '--')