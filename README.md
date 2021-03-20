# School-District Analysis with Pandas 

## Overview of the school district analysis

In this Module, we used Pandas to analyze the school district data. There are two CSV files included in this analysis: student level data and school level data. After the initial analysis, the school board decided to do further analysis by replacing the Ninth grade reading and math scores in Thomas High School with NaN. Then used the cleaned data to conduct the following school district analysis:

-	The district summary.
-	The school summary.
-	The top and bottom 5 schools based on the overall passing rate.
-	The average math and reading score of each grade level for each school.
-	The scores by school spending per student, size and type respectively. 

## Analysis

1.	Initial process.

    In this step, imported the Pandas dependency, set up the path of the school level and student level data. Used Pandas pd.read_csv() function to read in both files. Then         cleaned the prefixes and suffixes in the student’s name in the student level dataset. 

    ![ins1](https://user-images.githubusercontent.com/79289806/111886288-47ab1100-89a3-11eb-86fd-94dbeb7b4a99.png) 

2.	Import Numpy, used loc() function to replace the ninth grade reading and math scores in Thomas High School with NaN, kept the rest of the records the same. 

    ![ins2](https://user-images.githubusercontent.com/79289806/111886289-47ab1100-89a3-11eb-9691-3bf945b7cc14.png) 

3.	In the following steps used the clean version of the student level dataset to conduct each analysis.

    (1) 	District summary:
    
    Merged the cleaned student level data with the school level data by school name. Calculated the total number of schools and students, average reading and math scores             across all schools. 

    ![ins3](https://user-images.githubusercontent.com/79289806/111886290-47ab1100-89a3-11eb-871e-2662065f5428.png) 

    Subtracted the number of students in 9th grade of Thomas High School from the total number of students. This will be the adjusted denominator to calculate percentage in         the following steps.

    ![ins4](https://user-images.githubusercontent.com/79289806/111886291-47ab1100-89a3-11eb-96f6-e339617bd34a.png)  

    Calculated the number of students passing reading, math and both. Used the adjusted total number of students across all schools from previous step as the denominator to         calculate the percentage respectively.

    ![ins5](https://user-images.githubusercontent.com/79289806/111886292-47ab1100-89a3-11eb-91c8-a434dc4c3318.png) 

    Created the DataFrame for district summary.

    ![ins6](https://user-images.githubusercontent.com/79289806/111886293-47ab1100-89a3-11eb-882a-60dd88ded378.png) 

    (2)	  School summary:

    Used the school level and student level combined dataset from the previous step to create all the variables that needed for the school summary data frame. Created the final     school summary data frame.
 
    ![ins7](https://user-images.githubusercontent.com/79289806/111886294-47ab1100-89a3-11eb-9467-349f50fcd271.png)

    In the following steps, Used the total number of students in 10th to 12th grade instead of the total number of students across all grades in Thomas High School as the           denominator, number of students passed math, reading or both as the numerator to calculate the percentage respectively. Used the new values overwrote the existing values for     Thomas High School in the per_school_summary_df and kept the other values unchanged. 

    ![ins8](https://user-images.githubusercontent.com/79289806/111886295-4843a780-89a3-11eb-8638-2a0b11c3c862.png)

    ![ins9](https://user-images.githubusercontent.com/79289806/111886296-4843a780-89a3-11eb-8f87-eb4b061623fa.png) 
 

    (3) 	Top and Bottom 5 schools:

    Used the sort_values() function to get the top and bottom 5 of the schools based on the overall passing percentage. 

    ![ins10](https://user-images.githubusercontent.com/79289806/111886297-4843a780-89a3-11eb-8e1d-ce64ffcfdc95.png) 

    (4)	  Math and Reading Scores by Grade:

    Used the cleaned school level and student level combined dataset from the previous step to calculate the average math and reading scores for each grade by school. 

    ![ins11](https://user-images.githubusercontent.com/79289806/111886298-4843a780-89a3-11eb-950c-d8ac8f4e6b21.png)

    ![ins12](https://user-images.githubusercontent.com/79289806/111886299-4843a780-89a3-11eb-8aeb-ef44c7fa9b4d.png)

    ![ins13](https://user-images.githubusercontent.com/79289806/111886302-48dc3e00-89a3-11eb-943b-f69ff06290cb.png) 
  
    (5)	  Scores by School Spending:

    Established the spending bins based on the school spending for student in each school. Calculated the averages for the desired columns by using the school summary data frame     created in the previous step. Creates the final data frame. 

    ![ins14](https://user-images.githubusercontent.com/79289806/111886303-48dc3e00-89a3-11eb-9ede-420be503cac9.png) 

    (6)	  Scores by School Size:

    Similar as the calculation in step (5), established bins based on the number of students in each school. Calculated averages for the desired columns by using the school         summary data frame created in the previous step. Created the final data frame. 

    ![ins15](https://user-images.githubusercontent.com/79289806/111886304-48dc3e00-89a3-11eb-9c0b-440d34f9a59a.png) 

    (7)	  Scores by School Type:

    The school type information was included in the school summary data frame so that there is no need to create bins for school type. Used the school summary data frame to         calculate the averages for the desired columns. Created the final data frame.

    ![ins16](https://user-images.githubusercontent.com/79289806/111886305-48dc3e00-89a3-11eb-95f5-4ccbb5a8b66f.png) 


## Results

1.	Initial process. The top 10 records of the student level data after remove the prefixes and suffixes. 

    ![ins17](https://user-images.githubusercontent.com/79289806/111886306-48dc3e00-89a3-11eb-8a63-0df6e69b6315.png) 

2.	Sample of records after replace the math and reading score in ninth grade of Thomas High School. 

    ![ins18](https://user-images.githubusercontent.com/79289806/111886307-4974d480-89a3-11eb-98bb-580595b44f1b.png) 

3.	Final data frames:

    (1) 	District summary: for the new analysis we replaced the math and reading scores of the 9th grade students in Thomas High School to NaN. Here are the data frames before           and after this action.

    Before:

    ![ins19](https://user-images.githubusercontent.com/79289806/111886308-4974d480-89a3-11eb-8da4-688a3673205c.png) 

    After:

    ![ins20](https://user-images.githubusercontent.com/79289806/111886309-4974d480-89a3-11eb-9563-fdacbcf964c0.png) 

    There are slightly difference between the “Before” and “After” outputs. The average scores and percentages are slightly lower in the “After” output compared to the values in     the “Before” data frame. 

    In the calculation of the percentage, both denominator and numerator have been changed. 

    (2) 	School summary: 

    Before: used original student level data.

    ![ins21](https://user-images.githubusercontent.com/79289806/111886310-4974d480-89a3-11eb-83e0-5f2c759802cf.png) 

    After: Used cleaned student level data. Only included 10th to 12th grades student when calculating the average scores and percentages for Thomas High School.

    ![ins22](https://user-images.githubusercontent.com/79289806/111886311-4974d480-89a3-11eb-9e2d-694578115209.png) 

    All the schools have the same values in the “After” output compared to “Before” except Thomas High School. Similar as the district summary output, the values for Thomas High     School in the “After” output are slightly lower than the values in the “Before” output due to the adjusted denominator and numerator used in the calculation.

    (3)	  Top and Bottom 5 schools: based on the overall passing percentage. 

    -	 Top 5 schools:

    Before: used the original version of the student level data.

    ![ins23](https://user-images.githubusercontent.com/79289806/111886312-4974d480-89a3-11eb-9b8a-ff15bdc3e00c.png) 

    After: used the cleaned version of the student level data and adjusted to use only 10th to 12th grades student’s information.

    ![ins24](https://user-images.githubusercontent.com/79289806/111886275-45e14d80-89a3-11eb-8034-7f112957919e.png) 

    Although the overall passing percentage for Thomas High school slightly dropped in the “After” output compared to the “Before” output, it didn’t affect the position of the       school to be ranked at the 2nd place among the top 5 schools.

    -	 Bottom 5 schools:

    Before:

    ![ins25](https://user-images.githubusercontent.com/79289806/111886276-4679e400-89a3-11eb-921a-3d1b62f96e81.png) 

    After:

    ![ins26](https://user-images.githubusercontent.com/79289806/111886277-4679e400-89a3-11eb-8525-6c9f0c1a0557.png) 

    The bottom 5 schools didn’t affect by this adjustment. 

    (4) 	Math and Reading Scores by Grade:

    Math:

    - 	Before: used the original student level data.        

    ![ins27](https://user-images.githubusercontent.com/79289806/111886278-4679e400-89a3-11eb-80c7-e205e0f5b9b8.png)     
    
    - 	After: Used the cleaned student level data. 
    
    ![ins28](https://user-images.githubusercontent.com/79289806/111886279-4679e400-89a3-11eb-8f9e-931816e806b9.png) 

    The average scores for math across all grades are the same between the “Before” and “After” outputs except the 9th grade score in Thomas High School. This is expected since     we replace the 9th grade math score in Thomas High School with NaN at the beginning of the process. In the “After” output, we used the cleaned version of the student data. 

    Reading:

    - 	Before: used original version of the student level data. 
 
    ![ins29](https://user-images.githubusercontent.com/79289806/111886280-4679e400-89a3-11eb-9a11-6c8a67485f37.png)

    - 	After: used cleaned version of the student level data. 

    ![ins30](https://user-images.githubusercontent.com/79289806/111886281-47127a80-89a3-11eb-91ff-9d5ecd983179.png) 

    Similar as the Math average scores for each grade, all the average reading scores are the same expect 9th grade in Thomas High School due to the clean up action at the           beginning of the process. 

    (5) 	Scores by School Spending:

    Before:

    ![ins31](https://user-images.githubusercontent.com/79289806/111886282-47127a80-89a3-11eb-9168-71ec5441e3b6.png) 

    After:

    ![ins32](https://user-images.githubusercontent.com/79289806/111886283-47127a80-89a3-11eb-993d-254a94059aae.png) 

    Given that we didn’t adjust the calculation of spending, the values in the “Before” and “After” are the same after formatting. 

    (6) 	Scores by School Size:

    Before:

    ![ins33](https://user-images.githubusercontent.com/79289806/111886284-47127a80-89a3-11eb-9e7a-31120b6bf8e1.png) 

    After:

    ![ins34](https://user-images.githubusercontent.com/79289806/111886285-47127a80-89a3-11eb-9fd9-c59847a1ee68.png) 

    After formatting, there is no difference between “Before” and “After” replacing the 9th grade math and reading scores in the Thomas High School.

    (7) 	Scores by School Type:

    Before:

    ![ins35](https://user-images.githubusercontent.com/79289806/111886286-47127a80-89a3-11eb-809a-36a902772c04.png) 

    After:

    ![ins36](https://user-images.githubusercontent.com/79289806/111886287-47127a80-89a3-11eb-8d75-947741a34df8.png) 

    After formatting, there is no difference between “Before” and “After” replacing the 9th grade math and reading scores in the Thomas High School.

## Summary:

After replaced the math and reading scores of ninth grade in Thomas High School with NaN, some of the values slightly changes in the adjusted analysis compared to the values in the initial. Given that both the denominator and numerator for the average score and passing rate of both math and reading calculation changed, the major effects are:

1.	Average math and reading scores across all schools (district level).
2.	Percentage of passing rate for both math and reading across all schools (district level).
3.	Average math and reading scores for Thomas High school (school level).
4.	Percentage of passing rate for both math and reading for Thomas High school (school level).

The clean-up action at the beginning of the process in the student level data decreased the average math and reading score, as well as the percentage of passing rate in both district level, and school level (for Thomas High School only).

