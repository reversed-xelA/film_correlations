# Film Data Analysis with Python
## Project Overview
* Cleaned and refinded the data.
* Assigned numerical values to categorical variables to analyse correlations between different film variables using the Pearson method.
* Discovered which film companies had the highest avereage profits and reviews (scores). 

## Resources
***Python Version:*** 3.12   
***Packages:*** numpy, pandas, matplotlib, seaborn    
***Film Data:*** https://www.kaggle.com/datasets/danielgrijalvas/movies 

## Data Cleaning
* Removed duplicate data.
* Parsed out company names and ratings, creating a company rating variable in the process.
* Parsed out salaries and converted them to floats. Removed any listings without salary data.
* Generated a 'state' variable based on the location of each company.
* Created key skills (e.g. python, SQL, Excel, machine learning, etc.) boolean variables by scanning job descriptions for matches.
* Created a company age variable based on the founding date.
* Created a 'senior' boolean variable from mention of seniority in job titles.
* For NLP; removed punctuation, tokenized words, removed stopwords and lemmatized words.

## Modelling
### Model building
After transforming categorical variables into dummy variables, the data was split into train and test sets with a test size of 20%.

Three models were trialled and evaluated via Mean Absolute Error. MAE was selected for ease of interpretation and because outliers don't need to be punished too heavily in this model.

The three models trialled were:  
* **Multiple linear regression** - A baseline model.
* **Lasso regression** - Due to the sparsity of the data, a normalised regression model like Lasso is appropriate.
*  **Random forest** - Again, with a sparse data set this is an appropriate model.

### Model performance
The Random Forest model far outperformed the other approaches on the test sets.
* **Random forest:** MAE = 19351
* **Lasso regression:** MAE = 20535
* **Linear model:** The model was wildly inaccurate due to colinearities and the sparsity of the data.

## Key Findings in EDA, Modelling and NLP
### Companies and job offerings
* Overall, companies were rated quite highly, with an average rating of 3.8/5.
* 84% of jobs are being offered by private and public companies and the most common sectors for job offerings are human resources, finance, and IT at 13%, 11% and 10%, respectively.

![image](https://github.com/reversed-xelA/ds_salary_preds/assets/141697086/b6c8443c-b961-4419-bc2c-46597f8c081e)

* New South Wales leads the country in job offerings (50%), followed by Victoria (29%).

![image](https://github.com/reversed-xelA/ds_salary_preds/assets/141697086/f5f32341-37ad-49bb-83c5-0c0df230c3c4)

### Salary analysis
* The average salary was $106474.

  ![image](https://github.com/reversed-xelA/ds_salary_preds/assets/141697086/e9377385-f985-4b82-a920-871abaf6363f)

* Government jobs pay the most on average (~ $110K), yet this was not a significant difference (p > 0.05). Conversely, jobs in New South Wales offer significantly higher salaries (~$109K, p = 0.005).

![image](https://github.com/reversed-xelA/ds_salary_preds/assets/141697086/38370e1a-59b3-45b7-951c-d68bb2005a6c)
![image](https://github.com/reversed-xelA/ds_salary_preds/assets/141697086/9a825256-a284-44df-8ca1-e7b25c867fe4)

* Overall, there wasn't a high level of correlation between any of the variables and salary.

  ![image](https://github.com/reversed-xelA/ds_salary_preds/assets/141697086/4c78163d-873e-44fc-9616-8eb6d29e85bd)

* The machine learning skill recorded the highest correlation with salary, leading to a significant (p < 0.000) increase in salary at an average of ~$16K more than jobs not requiring machine learning.
* Other technical skills like Python, SQL, math and statistics also indicated higher salaries; however, the correlations are low, and the effect is not significant (p >0.05).
* Interestingly, excel was indicative of a lower salary, with these jobs earning a significant difference (p = 0.007) of ~$5K less on average.
* Regarding less technical skills, the ability to present data (presentation skill) looked to have a significant (p = 0.004), although small, impact on salary, increasing it by ~5K on average.
* Understandably, senior positions were offering higher salaries at ~6K more on average (p = 0.009).

### NLP findings
* From those listings that mentioned the years of experience required, the average requirement was ~4 years of experience (if a range was provided for experience required, the average was taken).

![image](https://github.com/reversed-xelA/ds_salary_preds/assets/141697086/611f659f-6e34-46c1-8659-a03bba7f15c6)

* Reporting, SQL and Python capabilities are the most requested technical skills, with 48%, 32% and 20% of listings mentioning these skills, respectively.
* There is also a high emphasis on visualisation and database skills (larger words in the word cloud indicate higher frequencies).

![image](https://github.com/reversed-xelA/ds_salary_preds/assets/141697086/03164536-d025-4df2-b53d-fbb6d73e176f)


* Soft skills-wise, communication and initiative are highly required, with 59% and 32% of positions looking for these skills, respectively.

![image](https://github.com/reversed-xelA/ds_salary_preds/assets/141697086/71793b16-9224-4f77-8f76-9aa3ecab8b90)

* Ranking the most common phrases also suggests communication is important, as is experience, business acumen, machine learning, and attention to detail.

![image](https://github.com/reversed-xelA/ds_salary_preds/assets/141697086/a51df633-230e-4cdc-97c7-bccba9998867)
