# Film Data Analysis with Python
## Project Overview
* Cleaned and refined the data.
* Assigned numerical values to categorical variables to analyse correlations between different film variables using the Pearson method.
* Discovered which film companies had the highest average profits and reviews (scores). 

## Resources
***Python Version:*** 3.12   
***Packages:*** numpy, pandas, matplotlib, seaborn    
***Film Data:*** https://www.kaggle.com/datasets/danielgrijalvas/movies 

## Data Cleaning
* Handled missing values by manually assigning release dates and IMDb scores, deriving missing vote values from the average votes of films with similar budgets, imputing missing runtimes from the average, and introducing an 'unknown' value for the rating, writer, star, country and company variables.
* Checked for and removed duplicate values.
* Numeric codes for all non-numeric variables were introduced to allow later correlations.

## EDA
The two variables I was most interested in were movie grossing and score (rating).
* Budget and the number of votes had the highest correlation with grossing with Pearson correlation coefficients of 0.74 and 0.63, respectively.
* Score was most highly correlated with the number of votes and runtime with Pearson correlation coefficients of 0.41 and 0.40, respectively.

![image](https://github.com/reversed-xelA/film_correlations/assets/141697086/48721063-0124-4b8e-b164-0b9c28059952)

* The top three companies by average score were (in order) Marvel Studios, Pixar Animation Studios and Lucasfilms.

![image](https://github.com/reversed-xelA/film_correlations/assets/141697086/68f71066-c4a5-4de8-b110-e8818e714da2)

* The top film companies by average gross were (in order) Marvel Studios, Lucasfilms and Pixar Animation Studios.

  ![image](https://github.com/reversed-xelA/film_correlations/assets/141697086/1029fda2-84b9-4ee4-ae8e-bd96f865c3e0)
