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

- Checking the last 10 students to make sure Thomas High School 9th grader stats were replaced.![Part 2](https://user-images.githubusercontent.com/82983000/118372747-1a34ab00-b581-11eb-81e5-1a7eee62014a.png)

- Use the LEN() function to calculate school count. Use the COUNT() function for student count and SUM() function for total school budget. Calculate the average math and reading scores by using the MEAN() function.
Use LOC function once again as well as COUNT() to find the number of students in 9th grade at Thomas High School. 
  - ninth_grade = student_data_df.loc[(student_data_df["grade"]== "9th")&(student_data_df["school_name"]=="Thomas High School")].count()['Student ID']

- Find the total student count with COUNT() and then subtracting ninth grade count from total student count. ![Part 3](https://user-images.githubusercontent.com/82983000/118372971-3258fa00-b582-11eb-8c9d-1cd791dfd2b8.png)

- Setting up the passing_math_count and passing_reading_count dictionaries so we cand later set them into percentages by dividing them against new_total_count and multiplying by 100. Calculate the overall passing percentage by combining the two into overall_passing_math_reading_count and turning that into percentages with the same steps as previously noted before. ![Part 4](https://user-images.githubusercontent.com/82983000/118373098-e9ee0c00-b582-11eb-8fd1-7a20d7b970dd.png)

- Creating a district_summary_df and formatting every number to have a comma for a thousands separator and decimal seperator. ![Part 5](https://user-images.githubusercontent.com/82983000/118373135-40f3e100-b583-11eb-90e2-ab30454eeec7.png)

  







