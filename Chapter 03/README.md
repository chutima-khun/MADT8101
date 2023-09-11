# Churn Prediction

### Content Overview 
![Churn](https://github.com/chutima-khun/MADT8101/blob/main/Chapter%2003/ChurnPrediction.png)

#### Churn prediction is used for estimate CLV of the Company and help business to take action in order to avoid upcoming churn event by approach target customer before they determine to churn from the Company.
#### The churn factor are vary according to each business industry and type of contractual with customer. Therefore, in order to perform churn prediction, it may need to identify churn factor that reflect to each customer type that need analysis.

# Class activity - ECommerce Churn

### Task 
Analyze the factor that cause to result of churn

## Result of workshop

### Project Overview
ECommerce dataset included the list of customer and current status of Active or Churn

### Analytic steps
1. Using dataiku for cleasing data.
![Flow](https://github.com/chutima-khun/MADT8101/blob/main/Chapter%2003/Flow.png)

2. Using AutoML feature to run model.
3. Before execute model, opt-out feature that should not be analyze for rational of churn (ex. CustomerID, Payment Mode, etc.)
![Feature1](https://github.com/chutima-khun/MADT8101/blob/main/Chapter%2003/Feature1.png)
![Feature2](https://github.com/chutima-khun/MADT8101/blob/main/Chapter%2003/Feature2.png)

4. Run model and inspect the result. It noted that the most accurate is Random Forest algorithm
![Result](https://github.com/chutima-khun/MADT8101/blob/main/Chapter%2003/ChurnResult.png)

5. Inspect the feature important of Top algorithm.
![FI](https://github.com/chutima-khun/MADT8101/blob/main/Chapter%2003/ImportantFeature.png)

6. Inspect the confusion matrix.
   
![Confusion](https://github.com/chutima-khun/MADT8101/blob/main/Chapter%2003/Confusion%20Matrix.png)

## Lesson Learn & What can improve
- Try other model or adjust feature to ensure the accurate of model.
- Try running random forest for all feature to inspect the important of feature before selection.
- Suggest action plan for churn factor and suggest time period for remidation in order to prevent customer actually churn in the future.
