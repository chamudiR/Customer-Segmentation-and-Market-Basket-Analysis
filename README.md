# Customer-Segmentation-and-Market-Basket-Analysis

## Project Overview
This project analyzes customer purchase behavior using the **Online Retail Dataset** from the UCI Repository. The main goals are:  

1. **Customer Segmentation** using **RFM (Recency, Frequency, Monetary) analysis** and **unsupervised learning (K-Means)**.  
2. **Market Basket Analysis** using the **Apriori algorithm** to find frequently co-purchased products.  
3. **Personalized Insights** by combining segmentation and basket analysis to recommend products to specific customer segments.

---

## Dataset
- **Source:** [UCI Online Retail Dataset](https://archive.ics.uci.edu/ml/datasets/Online+Retail)  
- **Description:** Contains transactions from a UK-based online retail store between 2010–2011. Includes:  
  - InvoiceNo: Invoice number  
  - StockCode: Product code  
  - Description: Product name  
  - Quantity: Quantity purchased  
  - InvoiceDate: Invoice date  
  - UnitPrice: Price per unit  
  - CustomerID: Unique customer identifier  
  - Country: Country of the customer  

---

## Key Steps

### 1. Data Cleaning
- Remove missing `CustomerID` values.  
- Remove cancelled orders (InvoiceNo starting with "C").  
- Remove negative quantities.  
- Create a `TotalPrice` column (`Quantity * UnitPrice`).  

### 2. RFM Feature Engineering
- **Recency (R):** Days since last purchase.  
- **Frequency (F):** Total number of invoices.  
- **Monetary (M):** Total money spent.  

### 3. Customer Segmentation (Unsupervised Learning)
- Scale RFM features using `StandardScaler`.  
- Use **K-Means clustering** to segment customers.  
- Determine optimal number of clusters using the **Elbow Method**.  
- Evaluate clusters using:  
  - **Silhouette Score**  
  - **Calinski-Harabasz Index**  
  - **Davies-Bouldin Index**  

### 4. Market Basket Analysis
- Convert transactions into a **basket matrix** (Invoice x Product, binary values).  
- Apply the **Apriori algorithm** to find frequent itemsets.  
- Generate **association rules** (`support`, `confidence`, `lift`).  

### 5. Combine Insights
- For each customer cluster, run market basket analysis only on that cluster’s transactions.  
- Identify **most relevant product combinations per segment**.  
- Result → **personalized recommendations and targeted marketing strategy**.

---

## Tools & Libraries
- Python 3.x  
- Pandas  
- NumPy  
- Scikit-learn  
- mlxtend (Apriori & Association Rules)  
- Seaborn & Matplotlib (Visua
