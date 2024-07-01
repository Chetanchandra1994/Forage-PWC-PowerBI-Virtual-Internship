# Forage-PWC-PowerBI-Virtual-Internship

In this project, I played the role of a BI Developer for National Rail, a company providing business services to passenger train operators in England, Scotland, and Wales. My task was to create an exploratory dashboard to help the management team gain insights into various aspects of their operations.


## Objectives of the Report

### 1. Customer Loyalty and Retention Analysis

Analyze customer loyalty and retention by identifying repeat customers, measuring their purchase frequency, and evaluating their impact on revenue over time.

### 2. Impact of Journey Time on Customer Satisfaction

Analyze how the actual journey time (from departure to actual arrival) impacts customer satisfaction, assuming delays reduce satisfaction levels (where satisfaction decreases as delay increases (e.g., -1 satisfaction point per 10 minutes of delay).

### 3. Profitability Analysis Based on Ticket Type and Class

Perform a profitability analysis based on ticket type and class, with dynamic filtering to show insights for different periods or stations (consider 55% of the ticket price is the cost of a ticket).


## Data Preparation and Transformation

#### Data Cleaning

The dataset underwent thorough cleaning using Power Query Editor and M code to ensure accuracy and consistency:

- Duplicate columns were removed, invalid characters were corrected, and errors were resolved.
- Null values were handled meticulously to maintain data integrity.
- Data types and formats were standardized, including setting date columns to YYYY-MM-DD format and correcting decimal values for uniformity.
- Sorting and filtering techniques were applied to align the dataset with project requirements, enhancing data usability and relevance.

#### Data Transformation

The transformation process involved implementing DAX measures and calculated columns to derive crucial metrics essential for railway performance analysis:

- Multiple measures were created to quantify revenue, operational efficiency, route performance, and the impact of delays on customer satisfaction.
- These calculated metrics provided actionable insights into patterns, trends, and areas for improvement within the dataset.
- Stakeholders were empowered with the ability to make informed decisions based on these insights.

## Report Layout

The report is structured across four main pages to facilitate comprehensive analysis:

- Revenue Analysis: Focuses on sales trends, revenue generation, and performance metrics.
- Performance Analysis: Provides insights into operational efficiency, route performance, and factors affecting service reliability.
- Journey Analysis: Analyzes the best and worst-performing routes based on various metrics, enabling optimization strategies.
- Travelers Analysis: Examines traveler demographics, satisfaction levels, and preferences to enhance customer experience and service offerings.

By organizing the report in this manner, key stakeholders gain a holistic view of National Rail's operations, enabling strategic decision-making and continuous improvement efforts.


![Revenue_Analysis](https://github.com/Chetanchandra1994/Maven_Challenge/assets/71788058/629f0829-89f1-43ab-857e-65c13026b5cf)


![Performance_Analysis](https://github.com/Chetanchandra1994/Maven_Challenge/assets/71788058/3f0e1734-6533-49ca-a9b2-7294b38f98cd)


![Journey Analysis](https://github.com/Chetanchandra1994/Maven_Challenge/assets/71788058/6566a34d-2553-41c1-875f-f7deb417ba3b)


![Travelers Analysis](https://github.com/Chetanchandra1994/Maven_Challenge/assets/71788058/a81bfec3-cf2e-461d-b707-19d5c22136f5)



## Key Measures Created

```DAX
1. Most Unsatisfied Customers = 
   CALCULATE(COUNTROWS(Railway), FILTER(Railway, Railway[Customer Satisfaction Score] <= -6))

2. Refunds = 
   CALCULATE(COUNTROWS(Railway), FILTER(Railway, Railway[Refund_Request] = "Yes"))

3. Satisfied Customers = 
   CALCULATE(COUNTROWS(Railway), FILTER(Railway, Railway[Journey_Status] = "On Time"))

4. Total no of Trains Cancelled = 
   CALCULATE(COUNTROWS(Railway), Railway[Journey_Status] = "Cancelled")

5. Total no of Trains Delayed = 
   CALCULATE(COUNTROWS('Railway'), 'Railway'[Journey_Status] = "Delayed")

6. Total no of Trains On-Time = 
   CALCULATE(COUNTROWS(Railway), Railway[Journey_Status] = "On Time")
```

## Insights on Revenue Analysis

- Total Revenue generated by Booking is £7,41,921. Although Total Refunds amount to £38,702, hence Net Revenue generated is £7,03,219.
- Total Cost incurred in Booking is £4,08,057.
- 8,400 Customers were gained in January, generating the highest revenue gain of £2,04,399, and 1,097 customers were reduced in February. March gained 763 customers, and April again lost 352 customers.








