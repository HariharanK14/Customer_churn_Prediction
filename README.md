# Customer Lifetime Value (CLV) Analysis

This project is a comprehensive analysis of Customer Lifetime Value (CLV) using historical transaction data. It leverages Python and several libraries, such as `pandas`, `numpy`, `matplotlib`, and `lifetimes`, to calculate CLV and model customer behavior metrics like purchase frequency and retention rate.

## Project Overview

The notebook processes a retail dataset to:
1. Import and clean transaction data.
2. Calculate the total sales and customer frequency metrics.
3. Compute Customer Lifetime Value (CLV) at both monthly and overall levels.
4. Build models to estimate the probability that a customer is "alive" based on their purchasing behavior.
5. Predict future transactions and average sales per customer using a Gamma-Gamma model.

## Dataset

The dataset used is `Online_Retail.csv`, which contains transactional data for an online retail business. Key fields include:
- `CustomerID`: Unique identifier for each customer
- `InvoiceNo`: Transaction identifier
- `InvoiceDate`: Date of the transaction
- `Quantity`: Quantity purchased
- `UnitPrice`: Price per unit of the item

## Setup

### Prerequisites

Ensure the following libraries are installed:
```bash
pip install pandas numpy matplotlib lifetimes
```

### How to Run

1. Mount Google Drive to access the dataset:
   ```python
   from google.colab import drive
   drive.mount('/content/drive')
   ```
2. Load and preprocess the data:
   ```python
   data = pd.read_csv("/content/drive/MyDrive/Online_Retail.csv", encoding="unicode_escape", parse_dates=['InvoiceDate'])
   ```
3. Execute the code cells sequentially to perform analysis and visualize results.

### Key Code Sections

- **Data Loading**: Reads the dataset and previews the transactions.
- **Data Aggregation**: Groups data by `CustomerID` to compute CLV, total sales, and frequency of purchases.
- **CLV Calculation**: Calculates CLV using the formula:
  \[
  \text{CLV} = \left(\frac{\text{Average Sales} \times \text{Purchase Frequency}}{\text{Churn Rate}}\right) \times \text{Profit Margin}
  \]
- **Modeling**: Implements a Beta-Geometric/NBD model to predict the probability of repeat purchases.

### Visualization

Several plots are generated, including:
- Sales trends
- CLV distribution by month
- Probability that customers remain active

## Results

- **Time Range of Data**: 2010-12-01 to 2011-12-09
- **Total Sales**: $9,747,747.93
- **Customer Retention and Churn Rate**: Retention and churn rates are calculated to assess repeat customer probability.
- **Monthly CLV**: Monthly CLV values are computed for more granular insights.

## Conclusion

This project provides insights into the customer purchasing behavior and projected lifetime value using both transactional data and predictive models. 

---
