# Diversity-And-Inclusion-Dashboard---Power-BI

This project analyzes a Diversity &amp; Inclusion dataset to provide actionable insights for HR. Using Power BI, I cleaned, transformed, and visualized key metrics such as hiring rates, promotions, performance ratings, and turnover, enabling data-driven decision-making to improve workforce diversity.

![229363730-638a282b-7348-4b3d-a0ff-3f8c0c9e3b9e](https://github.com/user-attachments/assets/22683cd6-7bfb-4e28-9cc1-e2088fdf469d)

# Table of Contents:

Problem Statement

Datasource

Data Preparation

Data Modeling

Data Analysis (DAX)

Data Visualization (Dashboard)

Insights

# Problem Statement:

The purpose of this task is to:

Define proper KPIs in hiring, promotion, performance and turnover
Create a visualisation for the HR manager that reflects all relevant Key Performance indicators(KPIs) and metrics in the dataset.
Calculating the following measures could help to define proper KPIs:

Number of men
Number of women
Number of leavers
% employees promoted (FY21)
% of women promoted
% of hires men
% of hires women
% turnover
Average performance rating: men
Average Performance rating: women

# Datasource :

Dataset used for this task was presented by Pwc and Diversity and Inclusion dataset:

Dataset: Diversity and Inclusion

# Data Preparation:

Completed the Data transformation in Power Query and the dataset loaded into Microsoft Power BI Desktop for modeling.

Diversity and Inclusion dataset is give table named:

Diversity and Inclusion dataset which has 500 rows and 31 Column of observation
Data Cleaning for the dataset was done in the power query editor as follows:

Changed the header row of dataset
Replaced the value is New hire FY20? N coverted No and Y converted Yes
Replaced the value is In base group for turnover FY20 N coverted No and Y converted Yes
Replaced the value is Promotion in FY20? N coverted No and Y converted Yes
Removed Unnecessary columns
Removed Unnecessary rows
Each of the columns in the table were validated to have the correct data type

# Data Modeling:

And then dataset was cleaned and transformed, it was ready to the data modeled.

The diversity and inclusion tables as show below:

![229366105-ee670e8e-2c01-4370-b28d-3a74d5033a00](https://github.com/user-attachments/assets/3f948b12-f951-44e4-8073-db5a493c6243)

# Data Analysis (DAX):

1. .# of leavers = 
CALCULATE(COUNTA('Pharma Group AG'[Employee ID]), 'Pharma Group AG'[Leaver FY] IN { "FY20" })

2. .# of men = Calculate(distinctcount('Pharma Group AG'[Employee ID]),Filter('Pharma Group AG','Pharma Group AG'[Gender]="Male"))

3. .# of women = Calculate(distinctcount('Pharma Group AG'[Employee ID]),Filter('Pharma Group AG','Pharma Group AG'[Gender]="Female"))

4. % employees promoted (FY21) = Divide(Calculate(distinctcount('Pharma Group AG'[Employee ID]),Filter('Pharma Group AG','Pharma Group AG'[Promotion in FY21?]="Yes")),Calculate(distinctcount('Pharma Group AG'[Employee ID]),Filter('Pharma Group AG','Pharma Group AG'[In base group for Promotion FY21]="Yes")))

5. % of hires men = Divide('Pharma Group AG'[# of men],('Pharma Group AG'[# of men]+'Pharma Group AG'[# of women]))

6. % of hires women = Divide('Pharma Group AG'[# of women],('Pharma Group AG'[# of women]+'Pharma Group AG'[# of men]))

7. % Promotees who were men = Divide(Calculate(distinctcount('Pharma Group AG'[Employee ID]),Filter('Pharma Group AG','Pharma Group AG'[Gender]="Male")),distinctcount('Pharma Group AG'[Employee ID]))

8. % Promotees who were women = Divide(Calculate(distinctcount('Pharma Group AG'[Employee ID]),Filter('Pharma Group AG','Pharma Group AG'[Gender]="Female")),distinctcount('Pharma Group AG'[Employee ID]))

9. % Turnover = Divide(Calculate(distinctcount('Pharma Group AG'[Employee ID]),Filter('Pharma Group AG','Pharma Group AG'[FY20 leaver?]="Yes")),Divide(Calculate(distinctcount('Pharma Group AG'[Employee ID]),Filter('Pharma Group AG','Pharma Group AG'[In base group for turnover FY20]="Y"))+Calculate(distinctcount('Pharma Group AG'[Employee ID]),Filter('Pharma Group AG',NOT('Pharma Group AG'[Department @01.07.2020]=BLANK()))),2))

10. Avg Rating Men = Calculate(Average('Pharma Group AG'[FY20 Performance Rating]),Filter('Pharma Group AG','Pharma Group AG'[Gender]="Male"))

11. Avg Rating Women = Calculate(Average('Pharma Group AG'[FY20 Performance Rating]),Filter('Pharma Group AG','Pharma Group AG'[Gender]="Female"))

12. # Data Visualization:

13. ![HR Dashboard 1](https://github.com/user-attachments/assets/744f9962-746b-47d7-95df-9e039592db6e)

14. ![HR Dashboard 2](https://github.com/user-attachments/assets/c881ccd2-aa8a-461a-a6c0-5c0ee1ac2891)

15. # Insights:

As shown the data Visualization, It can be deduced that:

41 % Female hires of the year and 59 % Male hires of the years.

53.8% of promoted were Female in the Junior Officer category, the highest for the year.

47% of promoted were Male in the Junior Officer category, the lowest for the year.

Director is the highest Average time of job level promoted in this year.

Finance department 22% highest turnover of the year.

Average Rating Female 2.42%

Average Rating Male 2.41%

Employees promoted year of 2021 is 54.34% Male and 45.66% Female.

The most common age group is 20-29 having 223 employees fall in this category.


