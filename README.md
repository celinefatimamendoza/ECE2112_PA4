<kbd>ECE2112<kbd>  
# ECE 2112 - Programming Assignment #03  

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


### B. VISAYAS FEMALE DATAFRAME  
Create a second DataFrame named `VisFemale` containing students whose `Hometown` is `Visayas` and whose `Gender` is `Female`.   
Retain only:  
```Name, Track, GEAS, Electronics, Average```  
Display `VisFemale`. Then display only the rows of `VisFemale` whose `Average` is at least 60. Do not overwrite `VisFemale` when performing this second filter.  


### C. CATEGORY-AVERAGE VISUALIZATION   
Examine how the recorded `Average` differs across the three categorical features `Track`, `Gender`, and `Hometown`.  
a. For each feature, compute the mean of Average for every category using Pandas.  
b. Display the three summary tables.  
c. Create one figure containing three bar charts: mean `Average` by `Track`, by `Gender`, and by `Hometown`.  
d. Below the figure, write three concise statements identifying the category with the highest sample mean for each feature.  


#### *Thank you for reading!*  
  
  
**README file Version History**   
*September 12, 2026* - Published the repository and inserted some content into the README file.  


