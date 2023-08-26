# Customer Segmentation
[![](https://img.shields.io/badge/-K--Means-orange)](#) [![](https://img.shields.io/badge/-DAX-green)](#) [![](https://img.shields.io/badge/-Python-green)](#) [![](https://img.shields.io/badge/-Google--Colab-green)](#) [![](https://img.shields.io/badge/-Power--BI-green)](#) [![](https://img.shields.io/badge/-Dashboard-blue)](#)

## 1) Import Dataset
The given Supermarket dataset contains 956K rows of sales transactions at sales-item level. The data include historical data from year 2006 to 2008.
We initially explore the data and found that members contributes to 85% of total sales. Hence, we want to segment customers into groups so that the supermarket have behaviour insights and able to customize the approach for each segment. 
![Dataset_Overview](./Dataset_Overview.PNG)

## 2) Generate Customer Single View
Total 3,439 customers
![SCV_Table](./SCV_Table.png)

## 3) K-Means Clustering
**Notebooks:** [K-Means Model](./Revise_of_Supermarket_Clustering.ipynb)  
**Google Colab:** [![Open In Collab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/jane-russ/MADT8101/blob/main/2.Basic%20Customer%20Analytics%20%26%20Single%20Customer%20View/Revise_of_Supermarket_Clustering.ipynb)
#### Features
All the features are taken from single customer view table
##### Overall Behaviour
* `FQ`: No. of time a customers has visited the supermarket
* `Total_Spend`: Total spending with the spending from 2006-2008 per customer code
* `MTBP` : Meantime between purchase 
* `Life_Time` : No. days they have been our customers from start date to current date (15 Jul 2008)
* `ARPU` : Average basket size of each customer
* `CLTV` : Average revenue generated from a customer over the entire lifetime of their account
* `MOD_CUST_LIFESTAGE_CD` : Customers lifestage: young adults, older adults, young families, older families, pensioners, other, unclassified
* `MOD_CUST_PRICE_SENSITIVITY_CD` : Customers price sensitivity: less affluent, mid market, upper market, unclassified. 
##### Price sensitivity Ratio
* `BASKET_PRICE_SENSITIVITY_LA` : The proportion of total purchase that is has price sensitivity of Less Affluent.
* `BASKET_PRICE_SENSITIVITY_MM` : The proportion of total purchase that is has price sensitivity of Mid Market.
* `BASKET_PRICE_SENSITIVITY_UM` : The proportion of total purchase that is has price sensitivity of Upper Market.
* `BASKET_PRICE_SENSITIVITY_XX` : The proportion of total purchase that is has price sensitivity of Unclassified.
##### Basket Type Ratio
* `BASKET_TYPE_Small_Shop` : The proportion of total purchase that is has basket type as Small Shop.
* `BASKET_TYPE_Top_Up` : The proportion of total purchase that is has basket type as Top Up.
* `BASKET_TYPE_Full_Shop` : The proportion of total purchase that is has basket type as Full Shop.
* `BASKET_TYPE_XX` : The proportion of total purchase that is has basket type as Unclassified. 
##### Mission Ratio
* `BASKET_MISSION_Fresh` : The proportion of total purchase that is has shopping mission for Fresh products.
* `BASKET_MISSION_Grocery` : The proportion of total purchase that is has shopping mission for Grocery products.
* `BASKET_MISSION_Mixed` : The proportion of total purchase that is has shopping mission for Mixed category products.
* `BASKET_MISSION_Non_Food` : The proportion of total purchase that is has shopping mission for Non Food products.
##### Basket Size Ratio
* `BASKET_SIZE_L%` : The proportion of total purchase that is basket size L.
* `BASKET_SIZE_M%` : The proportion of total purchase that is basket size M.
* `BASKET_SIZE_S%` : The proportion of total purchase that is basket size S. 
 
#### Choosing K number of clusters
Choose `K = 4` with the lowest silhoette score of 0.11
![elbow](./elbow.png)
![silhoetterscore](./silhoetterscore_compare.PNG)
![silhoetterplot](./silhoetterplot_K4.png)

#### Clustering Result
![clustering_result](./clustering_result.png)

## 4) Clustering Result Analysis
**Notebooks:** [Clustering Result EDA](./Revise_Clustering_Result.ipynb)  
**Google Colab:** [![Open In Collab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/jane-russ/MADT8101/blob/main/2.Basic%20Customer%20Analytics%20%26%20Single%20Customer%20View/Revise_Clustering_Result.ipynb)

#### EDA
##### Describe Features
![describe1](./Features_Describe_Buying1.PNG)
![describe2](./Features_Describe_Buying2.PNG)
![describe3](./Features_Describe_PriceSensitivity.PNG)
![describe4](./Features_Describe_BasketType.PNG)
![describe5](./Features_Describe_MIssion.PNG)
![describe6](./Features_Describe_Size.PNG)
##### KDE
![kdeplot](./Features_KDE.png)
##### Bloxplot
![boxplot](./Features_Boxplot.png)
#### Feature Importance
With the cluster labels as classes to predict, train a Random Forest classifier.
![importance](./Features_Importance.png) 

## 5) Interpretation
![Dashboard_ClusterAnalysis](./Dashboard_ClusterAnalysis.PNG)

### Cluster 0 : VIP Loyal Customers
**Description:** Large Shopping Mixed Basket, Smallest group but contribute 18% of total sales.  
**Recommended Action:** Ensure retention and decrease mean time between purchase.  
**Recommended Next steps:** Investigate in attractive loyalty scheme and gamification

### Cluster 1 : Regular Shoppers
**Description:** Mid Basket Size been a regular customer who comes consistently.  
**Recommended Action:** Increase basket size.  
**Recommended Next steps:** Explore if the segment can be further segments for more customized approach. 

### Cluster 2 : Daily Shoppers
**Description:** Small Basket size but come often, The group has the highest number of proportion of purchase with non-food products.  
**Recommended Action:** Increase basket size with upselling each time they visit the store to increase the value per visit.  
**Recommended Next steps:** Explore in detail on what are the non-food products they are interested in and how can it be upsell.  

### Cluster 3 : Large Top Up Shoppers
**Description:** Large Shopping Top Up Basket, Contribute almost 60% of sales.  
**Recommended Action:** Increase basket size with cross selling as they come for top up shopping.  
**Recommended Next steps:** Explore in details and product recommendation project.  

Note that for mean time between purchased, median is used as it is quite left-skewed.


# Churn Scoring
[![](https://img.shields.io/badge/-Classification-orange)](#) [![](https://img.shields.io/badge/-Python-green)](#) [![](https://img.shields.io/badge/-Google--Colab-green)](#) 

**Notebooks:** [Classification Model](./ChurnScoring.ipynb)  
**Google Colab:** [![Open In Collab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/jane-russ/MADT8101/blob/main/4.ChurnScoring/ChurnScoring.ipynb)

## 1) Import Dataset
The data is an ecommerce dataset including the following: 
- CustomerID	Unique = customer ID
- Churn = Churn Flag
- Tenure = Tenure of customer in organization
- PreferredLoginDevice = Preferred login device of customer
- CityTier = City tier
- WarehouseToHome = Distance in between warehouse to home of customer
- PreferredPaymentMode = Preferred payment method of customer
- Gender = Gender of customer
- HourSpendOnApp = Number of hours spend on mobile application or website
- NumberOfDeviceRegistered = Total number of deceives is registered on particular customer
- PreferedOrderCat = Preferred order category of customer in last month
- SatisfactionScore = Satisfactory score of customer on service
- MaritalStatus = Marital status of customer
- NumberOfAddress = Total number of added added on particular customer
- Complain = Any complaint has been raised in last month
- OrderAmountHikeFromlastYear = Percentage increases in order from last year
- CouponUsed = Total number of coupon has been used in last month
- OrderCount = Total number of orders has been places in last month
- DaySinceLastOrder = Day Since last order by customer
- CashbackAmount = Average cashback in last month

Number of observations: 5,630   
Number of variables: 20

## 2) EDA
EDA Shows that the data is quite imbalance between churn and not churn customers. 
### Frequency distribution of categorical variables:
![FrequencyDistribution](./img/FrequencyDistribution.png)  

### Summary statistics of numerical variables by Churn Flag:  
![Describe1](./img/Describe1.PNG)
![Describe2](./img/Describe2.PNG)
![Describe3](./img/Describe3.PNG)

### Nurmerical variable distribution:
![KDE](./img/KDE.png)   

### Missing Value: 
-  `Tenure `                         264
-  `WarehouseToHome `                251
-  `HourSpendOnApp `                 255
-  `OrderAmountHikeFromlastYear `    265
-  `CouponUsed `                     256
-  `OrderCount `                     258
-  `DaySinceLastOrder `              307

* Based on KDE plot, there features (`Tenure ` , `WarehouseToHome `, `OrderAmountHikeFromlastYear ` , `CouponUsed ` , `OrderCount ` , `DaySinceLastOrder `) are skewed hence we used median to impute missing value
* For  `HourSpendOnApp ` , it is multinomial so we used mode to impute missing value

### Bivariate Analysis: 
Looks like almost all feature are significant to churn flag.

#### Cat-Cat
![heatmap](./img/heatmap.png) 
- PreferredLoginDevice: Chi-square statistic: 73.536 | P-value: 1.0756922373255213e-16
- PreferredPaymentMode: Chi-square statistic: 77.897 | P-value: 9.708708511076305e-15
- Gender: Chi-square statistic: 4.663 | P-value: 0.030820940334890086
- PreferedOrderCat: Chi-square statistic: 288.639 | P-value: 2.7708325346337454e-60
- MaritalStatus: Chi-square statistic: 188.671 | P-value: 1.073011277910542e-41

#### Cat-Num
![boxplot](./img/boxplot.png) 
![Ttest](./img/Ttest.PNG) 

#### Feature engineering 
turning categorical columns into numeric value using one-hot end technique. Unique values for column:
- `PreferredLoginDevice`:['Mobile Phone' 'Phone' 'Computer']
- `PreferredPaymentModev`:['Debit Card' 'UPI' 'CC' 'Cash on Delivery' 'E wallet' 'COD' 'Credit Card']
- `Gender`: ['Female' 'Male']
- `PreferedOrderCat`: ['Laptop & Accessory' 'Mobile' 'Mobile Phone' 'Others' 'Fashion' 'Grocery']
- `MaritalStatus`:['Single' 'Divorced' 'Married']
  
## 3) Model Creation & Evaluation
- Model Used: 'Logistic Regression', 'Random Forest', 'KNeighbors','XGBoost'
- Fixing Imbalance Technique: none, under sampler, over sampler, SMOTE
- The best performing Model: XGBoost, Sampler: Over_Sampler

![ModelResults](./img/ModelResults.PNG) 
  
## 4) Result Feature Importance
The best performing Model: XGBoost, Sampler: Over_Sampler
### confusion matrix  
![confusionmatrix](./img/confusionmatrix.png)

### ROC-AUC  
![ROCAUC](./img/ROCAUC.png)

### evaulation  
![evaluation](./img/evaluation.PNG)

### feature importance  
![fimp](./img/fimp.png)
