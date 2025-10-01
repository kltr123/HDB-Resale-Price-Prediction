# HDB Resale Price Prediction (2017–2025)

This project applies multiple regression algorithms to predict resale flat prices in Singapore using the **HDB resale dataset** from [data.gov.sg](https://data.gov.sg/).

## Dataset
- Source: Housing & Development Board (HDB), “Resale flat prices based on registration date from Jan-2017 onwards”.
- Period: 2017–2025
- Size: ~217k transactions
- Key features: town, flat type, floor area, storey, flat model, flat age, remaining lease.

## Methods
Implemented and compared several models:
- **Linear Models:** Linear Regression, Ridge, Lasso, ElasticNet
- **Tree-Based:** Decision Tree, Random Forest
- **Boosting:** XGBoost
- **Instance-Based:** k-Nearest Neighbors (kNN)
- **Neural Networks:** TensorFlow & PyTorch

## Results (Test Set)

| Model              | R²    | MAE      | RMSE     | MAPE   |
|--------------------|-------|----------|----------|--------|
| Linear Regression  | 0.016 | 181,692  | 200,012  | 27.74% |
| Ridge Regression   | 0.016 | 181,666  | 200,000  | 27.73% |
| Lasso Regression   | 0.016 | 181,694  | 200,014  | 27.74% |
| ElasticNet         | -0.034| 177,419  | 205,013  | 26.08% |
| Decision Tree      | 0.333 | 138,275  | 164,654  | 20.42% |
| Random Forest      | 0.456 | 121,116  | 148,772  | 17.83% |
| XGBoost            | **0.517** | **114,140** | **140,134** | **16.88%** |
| kNN                | 0.469 | 123,398  | 146,946  | 18.39% |
| Neural Network (TF)| 0.502 | 117,598  | 142,290  | 17.43% |
| Neural Network (PT)| 0.498 | 119,710  | 142,906  | 17.69% |

## Key Takeaways
- Linear models fail to capture nonlinear patterns.  
- Decision Tree overfits but finds structure.  
- Random Forest and kNN improve generalization.  
- **XGBoost achieves the best overall test performance** (highest R², lowest MAE/RMSE/MAPE).  
- Neural Networks (both TensorFlow and PyTorch) achieve **competitive performance close to XGBoost**, showing deep learning can model complex interactions, but boosting remains slightly stronger for this tabular dataset.  
