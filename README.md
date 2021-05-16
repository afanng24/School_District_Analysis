# A Written Report for the School District Analysis 

## Overview of School District Analysis
School District Analysis is a project to essentially refactor the code in PyCitySchools. The original code took data from two excel csv files and formatted them so that data could be read easily. This included cleaning the student data to insure there were no additional prefix or suffix, generating the school/district summary and averaging group scores across all grades for fifteen separate highschools. The School District Analysis completes all this and more as the school board has found evidence of academic dishonesty in the 9th grade class in Thomas High School. The objective then is to replace the reading and math grades in Thomas High School for only the 9th grade class. 

Using newly acquired data the refactored code will also need to recreate the district summary, the school summary, the top 5 and bottom 5 schools, as well as the average math and reading scores for each grade level from each school. Finally the spending data, which is separated by students, school size, and school type.  



### Resources
**Source of Data** : schools_complete.csv, students_complete.csv

**Software** : Python 3.7.6 , Jupyter Notebook, Visual Studio Code.

## Results
### District Summary
- There is a neglible -0.1 change in Average Math Score and -0.2 Passing Math percentage after 9th grade Thomas High School was taken out. Passing Reading percentage did fall by -0.3 percent. 
  - Original PyCitySchool District  ![OrigianlDistrict](https://user-images.githubusercontent.com/82983000/118382674-ac5ea280-b5c5-11eb-81a2-0bc2c84258fb.png)

  - Refactored District 
![Challegne district](https://user-images.githubusercontent.com/82983000/118382679-b2ed1a00-b5c5-11eb-9b53-b786248fe12e.png)


### School Summary
- There does not seem to be any change in overall school summary. Looking further into the not formatted charts there is a neglible change in overall passing percentage. 
  - Original School Summary 


  ![OrigianlSchoolSummary](https://user-images.githubusercontent.com/82983000/118382783-c056d400-b5c6-11eb-9ecd-4669e5d73a3d.png)


  - Refactored School Summary 

  ![RefactoredlSchoolSummary](https://user-images.githubusercontent.com/82983000/118382787-c947a580-b5c6-11eb-87cc-07424ac02762.png)

- Replacing Scores
- Compared to other schools there is no change in placement or budget however in Thomas High School:
-   Passing percentage shift from 90.95 to 90.60
-   Average math score from 83.41 to 83.35
-   Average reading score from 83.85 to 83.90
-   Math percentage from 93.27 to 93.19
-   Reading percentage from 97.31 to 97.02 

Original 

![Orignal](https://user-images.githubusercontent.com/82983000/118383144-50961880-b5c9-11eb-8681-e9d94f3fe0e3.png)

Refactored  
![Refactored](https://user-images.githubusercontent.com/82983000/118383146-5855bd00-b5c9-11eb-806f-77382aa63448.png)



  - Math and reading scores by grade
  - Scores by school spending
  - Scores by school size
  - Scores by school type

  
## Summary
4 changes in the updated school distrcit after the replacement scores. 






## Explaining the Code and Introductions

This section is an addition created to further explain the code and why some lines of code are used. This will make it easier to review further down the line should anyone ever need to revisit syntax or misunderstand what certain lines accomplishes. The challenge itself is called "PyCitySchools_Challenge.ipynb" while the homework file was named "PyCitySchools.ipynb" much of the challenge is again simply restructuring what we have learned in "PyCitySchools.ipynb" and making it work in the challenge file. Screenshots will be added where it is necessary. 


 ## Code and Comparisons
 
- Setting up the dependencies, linking the csv folders and storing them into a pandas dataframe.
The student names had suffixes and prefixes, cleaned them by using the FOR IN function and replacing them with “” to create empty space. student_data_df.head(10) prints out the first 10 names to check if the code had worked. 
![Part 1](https://user-images.githubusercontent.com/82983000/118372427-86161400-b57f-11eb-82d6-88d380df5b6d.png)

### Replace the 9th grade reading and math scores at Thomas High School with NaN
- Installing numpy as np. Using the Loc method to replace all 9th grade Thomas High School students math and reading scores with Nan’s.
    - student_data_df.loc[(student_data_df['school_name'] == 'Thomas High School') & (student_data_df['grade'] == '9th'), 'reading_score'] = np.nan
    - student_data_df.loc[(student_data_df['school_name'] == 'Thomas High School') & (student_data_df['grade'] == '9th'), 'math_score'] = np.nan

- Checking the last 10 students to make sure Thomas High School 9th grader stats were replaced.![Part 2](https://user-images.githubusercontent.com/82983000/118372747-1a34ab00-b581-11eb-81e5-1a7eee62014a.png)


### District Summary
- Use the LEN() function to calculate school count. Use the COUNT() function for student count and SUM() function for total school budget. Calculate the average math and reading scores by using the MEAN() function.
Use LOC function once again as well as COUNT() to find the number of students in 9th grade at Thomas High School. 
  - ninth_grade = student_data_df.loc[(student_data_df["grade"]== "9th")&(student_data_df["school_name"]=="Thomas High School")].count()['Student ID']

- Find the total student count with COUNT() and then subtracting ninth grade count from total student count. ![Part 3](https://user-images.githubusercontent.com/82983000/118372971-3258fa00-b582-11eb-8c9d-1cd791dfd2b8.png)

- Setting up the passing_math_count and passing_reading_count dictionaries so we cand later set them into percentages by dividing them against new_total_count and multiplying by 100. Calculate the overall passing percentage by combining the two into overall_passing_math_reading_count and turning that into percentages with the same steps as previously noted before. ![Part 4](https://user-images.githubusercontent.com/82983000/118373098-e9ee0c00-b582-11eb-8fd1-7a20d7b970dd.png)

- Creating a district_summary_df and formatting every number to have a comma for a thousands separator and decimal seperator. ![Part 5](https://user-images.githubusercontent.com/82983000/118373135-40f3e100-b583-11eb-90e2-ab30454eeec7.png)
### School Summary
  
- Determining the school type was already completed in “PyCitySchools” and everything here is done to find the per school summary based on scores and budget. ![Part 6](https://user-images.githubusercontent.com/82983000/118373287-0e96b380-b584-11eb-9709-29e4c385251f.png)
- Creating the per_school_summary Dataframe by the new per_school dictionaries and showing all 15 schools affected by the change. ![Part 7](https://user-images.githubusercontent.com/82983000/118373365-6df4c380-b584-11eb-95ac-cad40f77a0ba.png) ![Part 8](https://user-images.githubusercontent.com/82983000/118373387-882ea180-b584-11eb-87cc-a1d4123e91ee.png)

- Formatting the Total School Budget and Per Student Budget, once again already written in “PyCitySchools” as well as displaying the new Dataframe. ![Part 9](https://user-images.githubusercontent.com/82983000/118373462-e8bdde80-b584-11eb-85fa-b974a785731b.png)

- Using the LOC function we are to separate everyone that’s not in 9th grade from the variables “Thomas High School” and “Student ID” to create a new total_thomas_students dictionary that does not include the 9th grade stats. 
  - tenth_graders = school_data_complete_df.loc[(school_data_complete_df["grade"]== "10th")
                                                     &(school_data_complete_df["school_name"]=="Thomas High School")].count()['Student ID']
- Passing Math and Reading are accomplished with the same LOC code as well. Afterwards they are combined to create a total_thomas_students_passing dictionary. 

  - passing_math = school_data_complete_df.loc[(school_data_complete_df["school_name"]=="Thomas High School") & (school_data_complete_df["math_score"] >= 70)].count()["Student ID"]
  - passing_reading = school_data_complete_df.loc[(school_data_complete_df["school_name"]=="Thomas High School") & (school_data_complete_df["reading_score"]
 ![Part 10](https://user-images.githubusercontent.com/82983000/118373606-d7290680-b585-11eb-9568-2767937a7726.png)
![Part 11](https://user-images.githubusercontent.com/82983000/118373652-06d80e80-b586-11eb-97c6-af60731ca26e.png)
- Calculate the percentage of 10th-12th grade students passing math and reading and then combining them into an overall passing percentage as had been done before during “clean student data.”![Part 12](https://user-images.githubusercontent.com/82983000/118373776-836aed00-b586-11eb-888c-eb25e8877580.png)

- Using the LOC function to replace the passing math and reading percentage for Thomas High school in the per_school_summary Dataframe. As well as Overall passing percentage. ![Part 13](https://user-images.githubusercontent.com/82983000/118373873-02602580-b587-11eb-9671-af445ddaaeee.png)
![Part 14](https://user-images.githubusercontent.com/82983000/118373887-186de600-b587-11eb-88f5-8ba512788428.png)
### High and Low Performing Schools

-  By sorting through values we can determine the high and low perfoming schools with ascending=False and ascending=True respectuvly.
    - per_school_summary_df.sort_values(["% Overall Passing"], ascending=False)
    - per_school_summary_df.sort_values(["% Overall Passing"], ascending=True)

![Part 15](https://user-images.githubusercontent.com/82983000/118374024-d5f8d900-b587-11eb-884c-066eb5f3aa92.png)
![Part 16](https://user-images.githubusercontent.com/82983000/118374025-d7c29c80-b587-11eb-957f-3da06195e36e.png)


### Math and Reading Scores by Grade
![Part 17](https://user-images.githubusercontent.com/82983000/118376697-9934de00-b597-11eb-8729-8ad36e465a43.png)
![Part 18](https://user-images.githubusercontent.com/82983000/118376713-b49fe900-b597-11eb-8f0d-94dde3d4ce2b.png)
![Part 19](https://user-images.githubusercontent.com/82983000/118376731-d26d4e00-b597-11eb-96f5-6d3ee1f3d8f1.png)
![Part 20](https://user-images.githubusercontent.com/82983000/118376762-eadd6880-b597-11eb-8651-9ec79b3a12e5.png)

### Scores by School Spending, Scores by School Size
- The following two tasks Scores by School Spending and Scores by School Size are the same as they both follow the same process of creating BINS based on "PyCitySchools" variables. Calculating average is a simple GROUPY function in conjunction with adding MEAN() and making sure the new dictionaries are included in the spending_summary_df and school_size_summary_df. Formatting is again the same code as used before to format the previous Dataframes. 

![Part 21](https://user-images.githubusercontent.com/82983000/118376977-2d537500-b599-11eb-916f-a052c36f72e5.png)
![Part 22](https://user-images.githubusercontent.com/82983000/118376979-32182900-b599-11eb-9aad-0aa91700af9f.png)
![Part 23](https://user-images.githubusercontent.com/82983000/118376983-393f3700-b599-11eb-9c3c-825a6abcb206.png)
![Part 24](https://user-images.githubusercontent.com/82983000/118376985-3ba19100-b599-11eb-99cb-b1878a924c26.png)
![Part 25](https://user-images.githubusercontent.com/82983000/118376986-3f351800-b599-11eb-9418-b3f37968f429.png)


### Scores by School Type
- Calculating the averages for desired columns is making sure that the MEAN() function is used specifically by the respective GROUPBY functions. All the new dictionaries are then assembled into the new school_type_summary Dataframe and then formatted like all the other dataframes. ![Part 26](https://user-images.githubusercontent.com/82983000/118377106-d4381100-b599-11eb-92b1-cb3ab195cebc.png)




