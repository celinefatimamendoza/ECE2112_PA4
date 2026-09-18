<kbd>ECE2112<kbd>  
# ECE 2112 - Programming Assignment #04 

**Celine Fatima C. Mendoza | 2ECE-C**  
# EXPERIMENT 4: DATA WRANGLING AND DATA VISUALIZATION  

This repository contains programming assignment 2 for the **ADVANCED COMPUTER PROGRAMMING AND ALGORITHMS** ```[ECE2112]``` course. It consists of three programming problems covering **Module 4 - Data Wrangling and Data Visualization**.  

  ## I. Intended Learning Outcomes   
  At the end of this laboratory activity, the student should be able to:  

  1. filter tabular data using several categorical and numerical conditions;  
  2. construct focused DataFrames by selecting relevant features;  
  3. summarize the relationship between categorical features and a numerical variable; and  
  4. communicate a data comparison using clear and correctly labeled plots.  

   ## II. Programming Problems  
   
### A. VISAYAS COMMUNICATION DATAFRAME  
Create a DataFrame named `VisComm` containing students whose `Hometown` is `Visayas` and whose `Track` is `Communication`.   
Retain only these columns, in the stated order:  
```Name, Gender, Math, Electronics, Average```   
Display the resulting DataFrame and its number of rows. Both filtering conditions must be applied to the source dataset before the columns are selected.  

### Function:  

```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt

df = pd.read_excel('board2.xlsx')

df['Average'] = np.mean(df[['Math', 'Electronics', 'GEAS', 'Communication']], axis = 1)

VisComm = df.loc[(df['Hometown'] == 'Visayas') & (df['Track'] == 'Communication')][['Name', 'Gender', 'Math', 'Electronics', 'Average']]
rows = len(VisComm)

display(VisComm)
print("Number of rows:", rows)
```


### B. VISAYAS FEMALE DATAFRAME  
Create a second DataFrame named `VisFemale` containing students whose `Hometown` is `Visayas` and whose `Gender` is `Female`.   
Retain only:  
```Name, Track, GEAS, Electronics, Average```  
Display `VisFemale`. Then display only the rows of `VisFemale` whose `Average` is at least 60. Do not overwrite `VisFemale` when performing this second filter.  

### Function:  

```python
VisFemale = df.loc[(df['Hometown'] == 'Visayas') & (df['Gender'] == 'Female')] [['Name', 'Track', 'GEAS', 'Electronics', 'Average']]
avesixty_VisFemale = VisFemale.loc[(VisFemale['Average']>=60)]

display(VisFemale)
print("VisFemale whose average is at least 60: ")
display(avesixty_VisFemale)
```


### C. CATEGORY-AVERAGE VISUALIZATION   
Examine how the recorded `Average` differs across the three categorical features `Track`, `Gender`, and `Hometown`.  
a. For each feature, compute the mean of Average for every category using Pandas.  
b. Display the three summary tables.  
c. Create one figure containing three bar charts: mean `Average` by `Track`, by `Gender`, and by `Hometown`.  
d. Below the figure, write three concise statements identifying the category with the highest sample mean for each feature.  

### Function: 

```python
Track_Mean = df.groupby('Track')['Average'].mean()
Gender_Mean = df.groupby('Gender')['Average'].mean()
Hometown_Mean = df.groupby('Hometown')['Average'].mean()

print("Categorical Features Average Summary: (Track, Gender, and Hometown)")
print('\n',Track_Mean)
print('\n',Gender_Mean)
print('\n',Hometown_Mean)

plt.figure(figsize=(20,6))

plt.subplot(1,3,1)
plt.bar(Track_Mean.index, Track_Mean.values, color = '#FF1B8D')
plt.title("Mean Average by Track")
plt.xlabel("Track")
plt.ylabel("Average Score")

plt.subplot(1,3,2)
plt.bar(Gender_Mean.index, Gender_Mean.values, color='#FFD900')
plt.title("Mean Average by Gender")
plt.xlabel("Gender")
plt.ylabel("Average Score")

plt.subplot(1,3,3)
plt.bar(Hometown_Mean.index, Hometown_Mean.values, color='#1BB3FF')
plt.title("Mean Average by Hometown")
plt.xlabel("Hometown")
plt.ylabel("Average Score")

statements = (
    "a. The 'Communication' group has the highest average value for the category feature 'Track'. \n"
    "b. The 'Male' population has a greater average value in the 'Gender' category. \n"
    "c. The 'Luzon' division has the highest average value for the 'Hometown' category. \n"
    )

plt.figtext(0.02, -0.2, statements, fontsize=15, ha="left")

plt.tight_layout()
plt.show()
```

#### *Thank you for reading!*  
  
  
**README file Version History**   
*September 12, 2026* - Published the repository and inserted some content into the README file.  
*September 17, 2026* - Published the Excel file and the `PA4.ipynb`.


