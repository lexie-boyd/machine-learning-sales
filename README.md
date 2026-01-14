# Predicting Customer Loyalty using UK Retail data from 2009-2011
## Transactions occurring for a United Kingdom based and registered non-store online retail business between December 1, 2009 and December 9, 2011. Python and R were both used in this project.

### Data 
Due to file size constraints, the raw data is not included in this repository.
The original dataset (Online Retail II, UCI Machine Learning Repository) can be downloaded from:
https://archive.ics.uci.edu/dataset/502/online+retail+ii

The dataset includes 1,067,371 transaction records and eight variables:
Invoice, StockCode, Description, Quantity, InvoiceDate, Price, CustomerID, and Country. It is stored in
XLSX format and represents actual transactional data. This dataset is interesting because it contains real
world business transactions with both customer and product information. Ultimately, this project aims to
build predictive models that generalize well using ridge regression, bagging, and neural network methods
inspired from STAT4630 Statistical Machine Learning classwork. 

### Approach
Data Preparation & Feature Engineering

- Cleaned and standardized transaction-level retail data, removing invalid records

- Aggregated transactions to the customer level, engineering behavioral features such as spending intensity, purchase frequency, recency, customer lifetime, basket characteristics, and return behavior

Exploratory Data Analysis

- Analyzed distributions and summary statistics of key customer metrics to understand purchasing behavior

- Visualized differences between repeat and non-repeat customers across spending, recency, and engagement measures

- Examined correlations and geographic patterns to inform feature selection and modeling choices

Predictive Modeling

- Built regularized logistic regression (ridge) models to predict repeat purchasing behavior

- Implemented decision trees and random forests to capture nonlinear relationships and interactions

- Developed a neural network model to further explore complex patterns in customer behavior

- Evaluated both first-purchase-only and fully aggregated customer models to assess early vs. mature customer prediction

Model Evaluation & Comparison

- Used train–test splits and cross-validation to assess out-of-sample performance

- Evaluated models using ROC-AUC, log loss, accuracy, sensitivity, and specificity

- Compared model performance against baseline classifiers and analyzed trade-offs between interpretability and predictive power


### Results
Across all models, predictive performance was weak when using only first‑purchase information, with ridge regression, decision trees, and random forests all performing near baseline due to limited early‑stage signal. Once aggregated behavioral data was introduced, performance improved substantially: ridge regression reached an AUC of about 0.65, the decision tree achieved roughly 74% accuracy, and the random forest delivered the strongest results with 96% accuracy and balanced sensitivity and specificity. The neural network also performed well with an AUC of 0.82, showing that nonlinear patterns in customer behavior provide meaningful predictive value once sufficient history is available.

### Business Takeaway
Predicting repeat purchasing is limited at the first purchase, meaning early targeting should remain broad and low‑cost. Once customers accumulate purchase history, behavioral variables such as recency and returns provide strong predictive power, enabling far more effective and efficient retention strategies. 

### Limitations
Model performance is constrained by class imbalance, the removal of leakage variables, and the coarse geographic grouping required for modeling. The dataset is also more than a decade old and lacks modern behavioral or marketing features, limiting generalizability to today’s retail environment. Additionally, results depend heavily on having longitudinal customer data, which may not be available in all business contexts.
