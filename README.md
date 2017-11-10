# Data Visualization Project 2

This is my second data visualization project for my masters degree. For the following project I chose the Human Resources Analytics data set from Kaggle. It is a very clean, organized and helpful dataset for a new Python user like myself. I would recommend the dataset for new users who are looking to learn simple data visualizations. 

For the following project, we had to do the following tasks: 

1. Select a dataset of our choosing (Human Resources)
1. Chop the dataset using pandas or any other method in python
1. Clean the dataset and drop missing values if needed
1. Create two types of visualization minimum
1. Create an excellent readme file
1. Push to Github and Kaggle

**Note** This data is a simulated.

# About the Readme
1. Obtaining the required data is the first approach. The first step is to download the dataset from Kaggle’s website and import it as a csv file to my desktop and following to github and kaggle. For the first step, it is important to find a dataset the use feels comfortable with. Personally, I am a beginner in programming hence why I chose this dataset. 

1.  Scrubbing or cleaning the data is the next step. This includes data imputation of missing or invalid data and fixing column names. The Human Resources dataset that we are using is a very clean dataset and actually requires very little editing. 

1. The main goal is to understand data through visualizations of different kinds, which is also the main goal of the course. It doesn't matter how big the data is  The use of various graphs plays a significant role here as well because it will give us a visual representation of how the variables interact with one another. We will get to see whether some variables have a linear or non-linear relationship. Taking the time to examine and understand our dataset will then give us the suggestions on what type of predictive model to use.

1. Modeling the data will give us our predictive power on whether an employee will leave. It will allow the coding to be ran and to visualize the data better. For the visualizations we utilized pandas, matplotlib and seaborn. 

1. Understanding and interpreting the data comes last. This step is as important as the rest of the others because we can receive comments and concerns for further research and/or implementation. 

**Note** The data was found from the “Human Resources Analytics” dataset provided by Kaggle’s website. https://www.kaggle.com/ludobenistant/hr-analytics

# Part 1 Obtaining the Data

```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import matplotlib as matplot
import seaborn as sns
%matplotlib inline
```

```
# Reading the file

HR = pd.read_csv('/Users/dayanamoncada/Desktop/DataVisProject2/HR_comma_sep.csv')
```

# Part 2: Scrubbing the Data 

*Usually, programmers would recommend to a cleaning of the dataset. There's a lot of instances in which there is unnecessary data, gramar errors and so on. This dataset from Kaggle is super clean and contains no missing values. Even though there wasn't data cleaning to do, it is still recommended.*

![alt text](https://github.com/dmonca63/DataVisProject2/blob/master/line12.png)

# Labeling

*Labeling your column names appropriately and periodically is the best way for you to understand the problem as well as making things visually appealing and organized. Furthermore, it helps with the coding part.*

# Feature conversion 

*Since the 'department' and 'salary' features are categorical, I'm going to convert it into numeric values for better analysis.*

# Exploratory data analysis 
#Statistical overview 


# Part 3: Visualizations
*Check the notebook for visualizations*

1. Heatmap - There seems to be heavy positive(+) correlation between projectCount, averageMonthlyHours, and evaluation. Which could mean that the employees who spent more hours and did more projects were evaluated highly. But the feature evaluation, when compared independently with the response variable turnover, shows little to no relationship. What does this mean? For the negative(-) relationships, turnover, satisfaction, and salary are highly correlated. I'm assuming that people tend to leave a company more when they are less satisfied and are lowly paid.

1. Department vs Salary - Looks like the top three departments for the company are support, technical, and sales. Most of the departments have similar turnover rates, but management has the lowest. This could mean that people with a higher position tend to not leave.

1. Turnover vs Department - he management department has the highest salary ratio and lowest turnover rate.

1. Turnover vs Years at Company - Summary: Looks like the bulk of the employees worked for about 3-6 years before leaving. Employees that worked for 7-10 years did not have anybody who left.

1. There seems to be a biomodal distrubtion for those that had a turnover. It looks like employees who performed bad or performed well left the company. The sweet spot seems for those that stayed seems to be within 0.6-0.8.

1. Looks like employees who did not have a turnover had consistent averageMonthlyHours, despite the increase in projects. In contrast, employees who did have a turnover had an increase in averageMonthlyHours with the increase in projects.

1. Pie Chart - Demonstrates the project Count vs Evaluation. 

