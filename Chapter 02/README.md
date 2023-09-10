# Customer Lifetime Value

## Content Overview 

![CLV](https://github.com/chutima-khun/MADT8101/blob/main/Chapter%2002/CLV-Overview.png) 
#### Customer Lifetime Value is predicted customer value calculated from presume customer's activity with the Company. It use to estimates the total revenue a customer is likely to generate throughout their relationship with company and help business plan strategy to react with customer and retain them for business sustainability.
 
![CustomerScore](https://github.com/chutima-khun/MADT8101/blob/main/Chapter%2002/Customer%20scoring.png)
#### Customer Scoring is used for classify customer from pattern of activity/charactoristic. It help business in quick identify and take action suitable to each type of customer.

![CampaignScore](https://github.com/chutima-khun/MADT8101/blob/main/Chapter%2002/Campaign%20scoring.png)
#### Campaign scoring is giving score to each marketing campaign which vary suitable to different customer and also timing of provide offer.


## Class activity - CLV & Customer Scoring
### Task 
1. Select 1 company to understand business background.
2. Analyze its existing loyalty program, and offer recommendations for improvement by scoring.

### Result of workshop

[Workshop](https://github.com/chutima-khun/MADT8101/blob/main/Chapter%2002/Suki%20Teenoi.pdf)

![Teenoi](https://github.com/chutima-khun/MADT8101/blob/main/Chapter%2002/Teenoi.png)

### Project Overview

"Suki Teenoi" is considered a popular budget sukiyaki restaurant that growing business day-to-day.
Aparting from strong loyalty customer, Suki Teenoi had not promote their loyalty program which in form of a membership card that will earn 1 point for each visit to the shop. The accumulate points to 15 points will transfer to membership card with exclusive privilege only allows 50% discount on food when dining in the birth month.

### Problem Statement
From understand background of business, our team identify that Suki Teenoi may facing challenges to increase customer lifetime value due to:
1. Lack of customer insights:
   - The loyalty program is not well-known, resulting in fewer sign-ups and an inability to gather customer data.
   - The loyalty program offers limited privileges, currently only providing discounts on birthdays, thus lacking incentives for enrollment.
2. Dependency on visit frequency for growth:
   - The only way to increase customer lifetime value is by increasing the number of visits since the products are priced at a fixed amount of 219 THB.

### Identify Customer Lifetime Value (CLV)

#### From background of Suki Teenoi business, our team estimate CLV of them as "(Average Basket Size x Margin% x Purchase Frequency) x Average Customer Lifespan" which is business target to maintain long term relationship with customer.
![TeenoiCLV](https://github.com/chutima-khun/MADT8101/blob/main/Chapter%2002/CLV-Teenoi.png)
#### Therefore, the customer loyalty program should be implement to keep loyalty customer and expand their CLV.

### Analytic steps

#### 1. Segmentation by CLV
  Segment the customers into groups using the following features:
  
  - CLV
  - Meantime Between purchase
  - Avg basket size
  - Total visit per month (avg last 3 months)
  - % Standard Set Bought
  - % Premium Set Bought
  - lifetime

        Machine Learning such as classifications model can be used to segment customers into groups.
        Classification algorithms can help segment customers into different groups based on their CLV scores.
        Algorithms like decision trees, random forests, or support vector machines can learn from historical customer data and assign customers to appropriate segments based on their characteristics and CLV potential.
  
#### 2. Customer Scoring Criteria

![TeenoiCustomerScore](https://github.com/chutima-khun/MADT8101/blob/main/Chapter%2002/TN-CustomerScore.png)
  
  Developing a customer scoring system utilizing Customer Lifetime Value (CLV) can provide significant insights and enable effective customer segmentation based on their long-term value to Suki Teenoi. 
  By assigning scores based on key classification features, such as the number of visits and the percentage of premium set purchases, we can establish a scoring framework:
  - each visit (frequency) = 1 point earned.
  - each premium set purchase (larger basket size) = 3 points earned. 

#### 3. Loyalty Program Suggestion 

![TeenoiCampaignScore](https://github.com/chutima-khun/MADT8101/blob/main/Chapter%2002/TN-Campaign.png)

  By using CLV as a basis for customer scoring, you can prioritize and personalize your interactions and marketing efforts. 
    1. Tier Benefit
    2. Tailored promotions and retention 

#### 4. Suggest implementation plan and expected result

![TeenoiPlan](https://github.com/chutima-khun/MADT8101/blob/main/Chapter%2002/TN-ImplementPlan.png)

![TeenoiResult](https://github.com/chutima-khun/MADT8101/blob/main/Chapter%2002/TN-Result.png)


## Lesson Learn & What can improve
- Add beverage as suggest plan.
- Demonstrate forecasting amount before and after implement plan to visual the comparative information.
- Try other business that may have real world use case (as Suki Teenoi may have limitation in estimate CLV due to no data of customer for calculation).





