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

```
# Scrubbing the data

# Check to see if there are any missing values in our data set
HR.isnull().any()

satisfaction_level       False
last_evaluation          False
number_project           False
average_montly_hours     False
time_spend_company       False
Work_accident            False
left                     False
promotion_last_5years    False
sales                    False
salary                   False
dtype: bool
```

```
# Let's take a look at a quick overview of what exactly is in our dataset
HR.head()

satisfaction_level	last_evaluation	number_project	average_montly_hours	time_spend_company	Work_accident	left	promotion_last_5years	sales	salary
0	0.38	0.53	2	157	3	0	1	0	sales	low
1	0.80	0.86	5	262	6	0	1	0	sales	medium
2	0.11	0.88	7	272	4	0	1	0	sales	medium
3	0.72	0.87	5	223	5	0	1	0	sales	low
4	0.37	0.52	2	159	3	0	1	0	sales	low
```

# Labeling

*Labeling your column names appropriately and periodically is the best way for you to understand the problem as well as making things visually appealing and organized. Furthermore, it helps with the coding part.*

```
# Renaming certain columns for better readability
HR = HR.rename(columns={'satisfaction_level': 'Satisfaction', 
                        'last_evaluation': 'Evaluation',
                        'number_project': 'NumberCompany',
                        'average_montly_hours': 'AverageMonthlyHours',
                        'time_spend_company': 'TimeAtCompany',
                        'Work_accident': 'WorkAccident',
                        'promotion_last_5years': 'Promotion',
                        'sales' : 'Department',
                        'left' : 'Turnover'
                        })
```

*By printing, the new head of the data, we can see the change in the labels*

```
HR.head()
	satisfaction	evaluation	projectCount	averageMonthlyHours	yearsAtCompany	workAccident	turnover	promotion	department	salary
0	0.38	0.53	2	157	3	0	1	0	sales	low
1	0.80	0.86	5	262	6	0	1	0	sales	medium
2	0.11	0.88	7	272	4	0	1	0	sales	medium
3	0.72	0.87	5	223	5	0	1	0	sales	low
4	0.37	0.52	2	159	3	0	1	0	sales	low
```

# Feature conversion 

*Since the 'department' and 'salary' features are categorical, I'm going to convert it into numeric values for better analysis.*

```# Convert "department" and "salary" features to numeric types because some functions won't be able to work with string types
HR['department'].replace(['sales', 'accounting', 'hr', 'technical', 'support', 'management',
        'IT', 'product_mng', 'marketing', 'RandD'], [0, 1, 2, 3, 4, 5, 6, 7, 8, 9], inplace = True)
HR['salary'].replace(['low', 'medium', 'high'], [0, 1, 2], inplace = True)

HR.head()

satisfaction	evaluation	projectCount	averageMonthlyHours	yearsAtCompany	workAccident	turnover	promotion	department	salary
0	0.38	0.53	2	157	3	0	1	0	0	0
1	0.80	0.86	5	262	6	0	1	0	0	1
2	0.11	0.88	7	272	4	0	1	0	0	1
3	0.72	0.87	5	223	5	0	1	0	0	0
4	0.37	0.52	2	159	3	0	1	0	0	0
```
```
# Move the reponse variable "turnover" to the front of the table
front = HR['turnover']
HR.drop(labels=['turnover'], axis=1,inplace = True)
HR.insert(0, 'turnover', front)
HR.head()
```
![GitHub Logo](/Users/dayanamoncada/Desktop/Project2DataVis/4.png)

Markdown | Less | Pretty
--- | --- | ---
*Still* | `renders` | **nicely**
1 | 2 | 3
