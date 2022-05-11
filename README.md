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
* **Math and reading scores by grade**

Replacing ninth grade scores resulted in only one change in our "math scores by grade" analysis and "reading scores by grade" analysis. Specifically, the scores for 9th grade for Thomas High School were replaced with NaN as seen in the tables below.

![Screen Shot 2022-05-11 at 1 34 55 PM](https://user-images.githubusercontent.com/101564349/167912070-a02db5db-ec19-4925-ac87-aeac91835fa1.png)          ![Screen Shot 2022-05-11 at 1 38 22 PM](https://user-images.githubusercontent.com/101564349/167912313-d6a49fdd-de5f-4c51-87ac-f06252e5914c.png)

* **Scores by school spending**

Replacing ninth grade scores also had an affect on the results of our "scores by school spending" analysis. After updating our analysis, we can see that the _% Passing Reading_ column had a shift in its results. Each Spending Range saw an increase in percentage of the % passing reading. 

**Initial Analysis**

![Screen Shot 2022-05-11 at 1 43 26 PM](https://user-images.githubusercontent.com/101564349/167913332-308eeb1e-ede0-4b52-b16b-12234fb68606.png)

**Updated Analysis**

![Screen Shot 2022-05-11 at 1 43 47 PM](https://user-images.githubusercontent.com/101564349/167913336-941e16d8-01cd-42d7-9ff9-39dbc1206dbf.png)

* **Scores by school size**

The results of the scores by school size can be seen below. The analysis indicates that the general trend remained the same. The only difference in our results was an increase in the percentage of students passing reading which went up by about 3-4% for each school size. 

**Initial Analysis**

![Screen Shot 2022-05-11 at 2 07 25 PM](https://user-images.githubusercontent.com/101564349/167917155-5474c1e1-58f9-49ac-8c6a-0bee4dde29a9.png)

**Updated Analysis**

![Screen Shot 2022-05-11 at 2 07 48 PM](https://user-images.githubusercontent.com/101564349/167917166-265e242a-c385-4db7-a19f-0229b9da51bc.png)


* **Scores by school type**

Looking at our analysis of "scores by school type", we can see that the general trend of results remained the same. Our initial and updated analyses both indicated that charter schools have a higher average score and a higher percentage of passing students. After we updated our analysis, the trend remained however, the values for % Passing Reading increased by 3-4% for both school types. 

**Initial Analysis**

<img width="723" alt="Screen Shot 2022-05-11 at 1 56 33 PM" src="https://user-images.githubusercontent.com/101564349/167915490-17d996ad-918f-4830-a863-603afae015a4.png">

**Updated Analysis**

<img width="724" alt="Screen Shot 2022-05-11 at 1 56 50 PM" src="https://user-images.githubusercontent.com/101564349/167915504-b41b403e-e0f6-4aba-89ee-7db986fc2383.png">


## Summary

In conclusion, by changing the scores of ninth graders at Thomas High School to NaN, we saw changes in some of our analysis. Overall, the trend patterns remained the same and we ultimately saw some slight changes in the average scores and percentages. A few changes made evident in our updated analysis are:
* Thomas High School remained as Number 2 in the list of Top 5 Schools, although, the average math score decreased while the average reading score increased. 
* The % Passing Reading increased in regard to scores by school spending
* The % Passing Reading icnreased in regard to scores by school size
* The % Passing Reading increased in regard to scores by school type
