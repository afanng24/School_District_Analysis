# A Written Report for the School District Analysis 

## Overview of the school district analysis



### Resources
**Source of Data** : schools_complete.csv, students_complete.csv

**Software** : Python 3.7.6 , Jupyter Notebook, Visual Studio Code.

## Results


  
## Summary



### Example of Finalized Summary 




## Explaining the Code and Introductions

This section is an addition created to further explain the code and why some lines of code are used. This will make it easier to review further down the line should anyone ever need to revisit syntax or misunderstand what certain lines accomplishes. The challenge itself is called "PyCitySchools_Challenge.ipynb" while the homework file was named "PyCitySchools.ipynb" much of the challenge is again simply restructuring what we have learned in "PyCitySchools.ipynb" and making it work in the challenge file. Screenshots will be added where it is necessary. 


 ## Code and Comparisons
 
- Setting up the dependencies, linking the csv folders and storing them into a pandas dataframe.
The student names had suffixes and prefixes, cleaned them by using the FOR IN function and replacing them with “” to create empty space. student_data_df.head(10) prints out the first 10 names to check if the code had worked. 
![Part 1](https://user-images.githubusercontent.com/82983000/118372427-86161400-b57f-11eb-82d6-88d380df5b6d.png)

- Installing numpy as np. Using the Loc method to replace all 9th grade Thomas High School students math and reading scores with Nan’s.
    - student_data_df.loc[(student_data_df['school_name'] == 'Thomas High School') & (student_data_df['grade'] == '9th'), 'reading_score'] = np.nan
    - student_data_df.loc[(student_data_df['school_name'] == 'Thomas High School') & (student_data_df['grade'] == '9th'), 'math_score'] = np.nan

- Chekcing the last 10 students to make sure Thomas High School 9th grader stats were replaced.![Part 2](https://user-images.githubusercontent.com/82983000/118372747-1a34ab00-b581-11eb-81e5-1a7eee62014a.png)








