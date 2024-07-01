# Forage PWC PowerBI Virtual Internship


This consists of my dashboards which I have done as a part of my Power BI Virtual Intership by PWC Switzerland. Task 2 - Call Centre Trends, Task 3 - Customer Retention , Task4 - Diversity & Inclusion.

Problem Statement :
The purpose of this task is to:

Define proper KPI's
Create a dashboard for the retention manager reflecting the KPI's
Write a short email to him (the engagement partner) explaining your findings, and include suggestions as to what needs to be changed
Customers who left within the last month
Services each customer has signed up for: phone, multiple lines, internet, online security, online backup, device protection, tech support, and streaming TV and movies
Customer account information: how long as a customer, contract, payment method, paperless billing, monthly charges, total charges and number of tickets opened in the categories administrative and technical
Demographic info about customers – gender, age range, and if they have partners and dependents
Datasource :
Dataset used for this task was presented by Pwc and customer churn Retention dataset:

Dataset: Customer Churn Retention

Data Preparation:
Completed the Data transformation in Power Query and the dataset loaded into Microsoft Power BI Desktop for modeling.

Customer Churn dataset is give table named:

Customer churn dataset which has 23 columns and 7043 rows of observation
Data Cleaning for the dataset was done in the power query editor as follows:

Removed Unnecessary columns
Removed Unnecessary rows

Replaced the value is SeniorCitizen N coverted No and Y converted Yes
In the new table, one additional conditional columns were added using M-formula:

loyalty = SWITCH(TRUE(),'01 Churn-Dataset'[tenure]<=12,"< 1 year",'01 Churn-Dataset'[tenure]<=24,"< 2 years",'01 Churn-Dataset'[tenure]<=36,"< 3 years",'01 Churn-Dataset'[tenure]<=48,"< 4 years", '01 Churn-Dataset'[tenure]<=60,"< 5 years",'01 Churn-Dataset'[tenure]<=72,"< 6 years")



Each of the columns in the table were validated to have the correct data type

Data Modeling:
And then dataset was cleaned and transformed, it was ready to the data modeled.


![Task 2 Call Centre Trend Analyisis](https://github.com/Chetanchandra1994/Forage-PWC-PowerBI-Virtual-Internship/assets/71788058/ec6231d3-ce1e-43eb-8408-4c3353e697fb)




![Task 3 PhoneNow Customer Retention](https://github.com/Chetanchandra1994/Forage-PWC-PowerBI-Virtual-Internship/assets/71788058/3d182b34-81d9-4d5f-8cd1-28b636499c48)




![Task 4 Diversity   Inclusion](https://github.com/Chetanchandra1994/Forage-PWC-PowerBI-Virtual-Internship/assets/71788058/a3b78a4f-199c-4d31-828a-34640816df39)



## Key Measures Created

```DAX
Average MonthlyCharges = AVERAGE('01 Churn-Dataset'[MonthlyCharges])

Average TotalCharges = AVERAGE('01 Churn-Dataset'[TotalCharges])

churn count = CALCULATE(COUNT('01 Churn-Dataset'[Churn]), ALLSELECTED('01 Churn-Dataset'[Churn]),'01 Churn-Dataset'[Churn] = "Yes")

churn rate % = DIVIDE(CALCULATE(COUNT('01 Churn-Dataset'[Churn]), '01 Churn-Dataset'[Churn] = "yes" ), COUNT('01 Churn-Dataset'[Churn]), 0)

Dependent in % = DIVIDE(CALCULATE(COUNT('01 Churn-Dataset'[Dependents]), '01 Churn-Dataset'[Dependents]="Yes",'01 Churn-Dataset'[Churn]="Yes"), CALCULATE(COUNT('01 Churn-Dataset'[Dependents]),'01 Churn-Dataset'[Churn]="Yes"), 0)

Device protection in % = DIVIDE(CALCULATE(COUNT('01 Churn-Dataset'[DeviceProtection]), '01 Churn-Dataset'[DeviceProtection] ="Yes", '01 Churn-Dataset'[Churn]="Yes"),CALCULATE(COUNT('01 Churn-Dataset'[DeviceProtection]),'01 Churn-Dataset'[Churn]="Yes"),0)

Online backup in % = DIVIDE(CALCULATE(COUNT('01 Churn-Dataset'[OnlineBackup]), '01 Churn-Dataset'[OnlineBackup] ="Yes", '01 Churn-Dataset'[Churn]="Yes"),CALCULATE(COUNT('01 Churn-Dataset'[OnlineBackup]),'01 Churn-Dataset'[Churn]="Yes"),0)

Online security in % =DIVIDE(CALCULATE(COUNT('01 Churn-Dataset'[OnlineSecurity]), '01 Churn-Dataset'[OnlineSecurity] ="Yes", '01 Churn-Dataset'[Churn]="Yes"),CALCULATE(COUNT('01 Churn-Dataset'[OnlineSecurity]),'01 Churn-Dataset'[Churn]="Yes"),0)

Partner in % = DIVIDE(CALCULATE(COUNT('01 Churn-Dataset'[Partner]),'01 Churn-Dataset'[Partner]="Yes",'01 Churn-Dataset'[Churn]="Yes"), CALCULATE(COUNT('01 Churn-Dataset'[Partner]), '01 Churn-Dataset'[Churn]="Yes"), 0)

Phone service in % =DIVIDE(CALCULATE(COUNT('01 Churn-Dataset'[PhoneService]), '01 Churn-Dataset'[PhoneService] ="Yes", '01 Churn-Dataset'[Churn]="Yes"),CALCULATE(COUNT('01 Churn-Dataset'[PhoneService]),'01 Churn-Dataset'[Churn]="Yes"),0)

SenioCitizen in % = DIVIDE(CALCULATE(COUNT('01 Churn-Dataset'[SeniorCitizen]),'01 Churn-Dataset'[SeniorCitizen]=1,'01 Churn-Dataset'[Churn]="Yes"), CALCULATE(COUNT('01 Churn-Dataset'[SeniorCitizen]),'01 Churn-Dataset'[Churn]="Yes"), 0)

Streaming Movies in % =DIVIDE(CALCULATE(COUNT('01 Churn-Dataset'[StreamingMovies]), '01 Churn-Dataset'[StreamingMovies] ="Yes", '01 Churn-Dataset'[Churn]="Yes"),CALCULATE(COUNT('01 Churn-Dataset'[StreamingMovies]),'01 Churn-Dataset'[Churn]="Yes"),0)

Streaming TV in % =DIVIDE(CALCULATE(COUNT('01 Churn-Dataset'[StreamingTV]), '01 Churn-Dataset'[StreamingTV] ="Yes", '01 Churn-Dataset'[Churn]="Yes"),CALCULATE(COUNT('01 Churn-Dataset'[StreamingTV]),'01 Churn-Dataset'[Churn]="Yes"),0)

Tech Support in % =DIVIDE(CALCULATE(COUNT('01 Churn-Dataset'[TechSupport]), '01 Churn-Dataset'[TechSupport] ="Yes", '01 Churn-Dataset'[Churn]="Yes"),CALCULATE(COUNT('01 Churn-Dataset'[TechSupport]),'01 Churn-Dataset'[Churn]="Yes"),0)
```


## Insights:

- Customers on the Two-Year contract, have been with the company for long, while most of the customers on Month-to-Month contract joined the company.
- The company is at risk of losing recently joined customers. based on the results from analysis.. if they decided to month-to-month contract.
- 7043 customers are at the risk of churn. and The churn rate is 27% and yearly charges is $16.06M charges. and Monthly Charges is $456.12K monthly charges.
- 2955 tech tickets were opened and 3632 admin tickets were opened.
- Most of the churned customers did not sign up for Online Security and tech support and also did not sign up for Phone Services.
- It a lot of customers had an issue with Fiber Optic . Up to 42% of the customers churned were using Fiber Optic as their Internet Services.

## Recommendation:

- The Company could try convincing customers to subscribe to One-Year and Two-Year contract. The contract are not favorable to customers as they tend to pay more monthly.
- Giving the discount to customers based on the some specific tasks is also good wat retaining them, specially those month-to-month contract.
- From analysis majority customers who churned did not sigh up for Online Security and Tech Support. These are the important services that customers should customers signup for. The company should educate customers on the benefits of signing up for these services.
- Increase sale of 1 and 2 year contract by 5% each and Yearly increase of automatic payments by 5%.







