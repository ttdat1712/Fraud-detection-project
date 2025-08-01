# 💳 Fraud Detection in Bank Transactions

This project applies **unsupervised machine learning techniques** to detect potential fraudulent transactions in a banking dataset.  

---

## 📌 Overview

With the rapid growth of digital banking, fraud detection has become a top priority for financial institutions.  
This project explores how unsupervised learning methods like **clustering** and **anomaly detection** can be used to identify suspicious transaction behavior and enhance fraud prevention systems.

---

## 📊 Dataset

- **Source File**: `data.csv`  
- **Total Records**: **2,512 transactions**  
- **Features Include**:  
  - `TransactionAmount`, `TransactionDate`, `TransactionType` (Credit/Debit)  
  - `Location`, `DeviceID`, `IP Address`, `Channel` (ATM, Online, etc.)  
  - `AccountBalance`, `TransactionDuration`, `LoginAttempts`  
- **Data Quality**:  
  - No missing values or duplicate entries  
  - Numeric, categorical, and time-based features suitable for clustering and anomaly detection

---

## 🎯 Project Goals

- Detect potential fraudulent activities using unsupervised machine learning techniques  
- Visualize behavioral patterns and transaction anomalies  
- Analyze transaction behavior across channels, times, locations, and devices  

---

## 🤖 Algorithms Used

### 1. **K-Means Clustering**
- Identifies natural groupings in the dataset  
- Optimal **k = 3** selected using the Elbow Method  
- Outliers (transactions far from cluster centroids) flagged as potential frauds  

### 2. **DBSCAN Clustering**
- Density-based clustering automatically detecting noise points (anomalies)  
- No need to predefine number of clusters  
- Parameters tuned: `eps = 1.5`, `min_samples = 5`  

### 3. **Isolation Forest**
- Tree-based ensemble method for anomaly detection  
- Works well in high-dimensional data  
- Flags outliers based on degree of isolation in feature space  

---

## 📈 Exploratory Data Analysis (EDA)

- **Distributions**: Histograms of transaction amount, duration, and account balance  
- **Correlations**: Numeric relationship analysis  
- **Category Analysis**: Pie charts and bar plots for `TransactionType`, `Channel`, etc.  
- **Behavioral Patterns**:  
  - High-frequency login attempts  
  - Transactions outside business hours  
  - Multiple accounts using same device or IP  
  - Transactions across multiple locations  
  - High-value or long-duration transactions  

---

## 🔍 Anomaly Detection Models

| Algorithm        | Key Strengths                              | Output Type             |
|------------------|-------------------------------------------|-------------------------|
| **K-Means**      | Fast, interpretable, scalable            | Cluster-based outliers  |
| **DBSCAN**       | Handles arbitrary shapes and densities    | Noise points (`-1`)     |
| **Isolation Forest** | Effective in high dimensions, robust | Binary (fraud/normal)   |

---

## ✅ Results & Insights

- **K-Means**: Detected several statistically distant transactions  
- **DBSCAN**: Automatically identified noise points not belonging to any cluster  
- **Isolation Forest**: Flagged ~5% of records as anomalies based on isolation depth  

**Behavioral Findings**:
- Debit transactions more prone to fraud  
- Nighttime transactions more suspicious  
- Certain IPs and devices used by multiple accounts  
- Login attempts often correlated with higher fraud likelihood  

These insights can help design **real-time fraud detection systems** in practice.

---

## 🗂️ Project Structure
- `code.ipynb` – Jupyter notebook containing full analysis and models  
- `requirements.txt` – Python dependencies  
- `Report.pdf` – Project report  
- `README.md` – Project documentation  

## ⚙️ Setup Instructions

1. **Clone the Repository**  
   `git clone https://github.com/ttdat1712/Fraud-detection-project.git`  
   `cd Fraud-detection-project`  

2. **Create a Virtual Environment**  
   `python -m venv .venv`  
   - Activate the environment:  
     - **Windows**: `.venv\Scripts\activate`  
     - **macOS/Linux**: `source .venv/bin/activate`  

3. **Install Dependencies**  
   `pip install -r requirements.txt`  

4. **Run the Jupyter Notebook**  
   `jupyter notebook code.ipynb`  

5. **(Optional) Run as a Streamlit App**  
   `streamlit run code.ipynb`

