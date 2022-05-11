# School District Analysis

Performing analysis on School District data for Module 4 challenge.

## Overview

Maria, the chief data scientist for city school district, has asked for help in preparing all standardized test data for analysis, reporting, and presentation. Our task was to aggregate the data and showcase trends in school performance. However, once the analysis was completed, the school board notified Maria expressing concerns of academic dishonesty; specifically in regard to the reading and math grades for Thomas High School ninth graders. To eliminate this data from the overall analysis we have replaced the reading and math scores with NaNs while keeping the rest of the data intact. Once this was done, the school district analysis was repeated with reliable results. Below are the summaries of the results as well as a comparative analysis of the changes made.

## Results

In order to replace the math and reading scores with NaN for all ninth grade Thomas High School students, the following code was refactored:

``
student_data_df.loc[(student_data_df["school_name"] == "Thomas High School") & (student_data_df["grade"] == "9th"), "reading_score"] = np.nan
``

``
student_data_df.loc[(student_data_df["school_name"] == "Thomas High School") & (student_data_df["grade"] == "9th"), "math_score"] = np.nan
``

Once the code was refactored, we were able to repeat the analysis which yielded the results below. 

### I. District Summary

First, we dive into how the district summary was affected once we incorporated the NaN's. Initially, the district summary reflected the following:

![Screen Shot 2022-05-11 at 11 21 17 AM](https://user-images.githubusercontent.com/101564349/167886972-b2be0d2b-e848-4bce-8e3a-1c465190f118.png)

Once we updated the analysis, the district summary changed to the following:

![Screen Shot 2022-05-11 at 11 22 35 AM](https://user-images.githubusercontent.com/101564349/167887233-876a7c68-e1b6-4c1d-b390-f0cf8f2713ea.png)

While the total number of schools, students, and budget remained the same, we can see a slight decline in the average math and reading scores as well as the % passing. The Average Math Score decreased by 0.1% while the average reading score seemed to remain relatively consistent. The changes in score yielded a 0.2% decrease in % Passing Math, a 0.3% decrease in % Passing Reading, and a 0.1% decrease in % Overall Passing.

### II. School Summary

Next, we looked into the affect on the School Summary. Initially, the results were depicted as such:

![Screen Shot 2022-05-11 at 11 35 41 AM](https://user-images.githubusercontent.com/101564349/167889983-defbff66-96a4-4dbc-9105-6ce79eff624b.png)

Once the code was refactored, the school summary was updated to the following:

![Screen Shot 2022-05-11 at 11 37 25 AM](https://user-images.githubusercontent.com/101564349/167890300-a791c65c-0e03-441f-896c-5af9a9522310.png)

The updated School Summary indicates that the only results affected were pertaining to Thomas High School. We can see a slight drop in the average math score going from 83.418349 to 83.350937 and consequently, a slight drop in the % Passing Math going from 93.272171% to 93.185690%. Alternatively, the average reading score slightly increased from a score of 83.848930 to 83.896082. We can also see a larger increase in the % Passing Reading going from 92.905199% to 97.018739%. Lastly, the % Overall Passing decreased by roughly 0.3%, going from 90.948012% to 90.630324%.

### III. Thomas High School’s performance relative to the other schools

Replacing Thomas High School's ninth grade math and reading scores did not seem to have an affect on its performance relative to other schools. When evaluating the Top 5 Schools, we can see that initially Thomas High School ranked as Number 2. After substituting the ninth grade scores with NaN's, we can see that although Thomas High School's scores and % Passing values were affected, it's overall ranking remained the same at Number 2. 

**Initial Analysis**
![Screen Shot 2022-05-11 at 11 54 34 AM](https://user-images.githubusercontent.com/101564349/167894277-9c139c54-b2b5-440f-aaa9-0f17673ba434.png)

**Updated Analysis**

![Screen Shot 2022-05-11 at 11 54 51 AM](https://user-images.githubusercontent.com/101564349/167894409-ab6a8bbd-5143-4b87-9a8d-468f11ccd9e8.png)

### IV. Replacing ninth-grade scores:
#### Math and reading scores by grade

#### Scores by school spending

#### Scores by school size

#### Scores by school type

## Summary
