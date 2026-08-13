# SpacECE Internship Assessment

## 📊 Sales Data Analysis and Machine Learning Project

This repository contains my internship assessment project for **SpacECE**. The project focuses on analyzing a sales dataset, performing data cleaning, exploratory data analysis (EDA), feature engineering, and building a foundation for data-driven insights using Python.

## 🚀 Project Overview

The main objective of this project is to analyze sales data and identify meaningful patterns and trends.

The project includes:

* Data loading and inspection
* Data cleaning
* Missing value handling
* Duplicate value checking
* Date conversion
* Feature engineering
* Exploratory Data Analysis (EDA)
* Monthly sales trend analysis

## 📁 Repository Structure

```text
SpacECE/
│
├── Internship Assesment.ipynb   # Main Python notebook containing the analysis
├── train.csv                    # Sales dataset
└── README.md                    # Project documentation
```

## 📊 Dataset Information

The dataset contains **9,800 records and 18 columns**.

Some important columns include:

| Column        | Description                      |
| ------------- | -------------------------------- |
| Row ID        | Unique row identifier            |
| Order ID      | Unique identifier for each order |
| Order Date    | Date when the order was placed   |
| Ship Date     | Date when the order was shipped  |
| Ship Mode     | Shipping method                  |
| Customer ID   | Unique customer identifier       |
| Customer Name | Name of the customer             |
| Segment       | Customer segment                 |
| Country       | Country of the customer          |
| City          | Customer city                    |
| State         | Customer state                   |
| Postal Code   | Postal code                      |
| Region        | Geographic region                |
| Product ID    | Unique product identifier        |
| Category      | Product category                 |
| Sub-Category  | Product sub-category             |
| Product Name  | Name of the product              |
| Sales         | Sales amount                     |

## 🛠️ Technologies Used

* Python
* Pandas
* Jupyter Notebook

## 🔍 Project Workflow

### 1. Data Loading

The dataset is loaded using the Pandas library.

```python
import pandas as pd

df = pd.read_csv('train.csv')
df.head()
```

### 2. Data Inspection

The dataset is inspected to understand its structure, size, column names, and data types.

```python
print("Shape of Data:", df.shape)
print("Column Names:", df.columns)

df.info()
```

### 3. Data Cleaning

The project checks for missing values in the dataset.

```python
print("Missing Values:\n", df.isnull().sum())
```

Missing values in the `Postal Code` column are handled using the median value.

```python
df["Postal Code"] = df["Postal Code"].fillna(
    df["Postal Code"].median()
)
```

### 4. Duplicate Data Check

The dataset is checked for duplicate records.

```python
print("Duplicates:", df.duplicated().sum())
```

### 5. Date Conversion

The `Order Date` and `Ship Date` columns are converted into datetime format for further analysis.

```python
df["Order Date"] = pd.to_datetime(
    df["Order Date"],
    format="mixed",
    dayfirst=True
)

df["Ship Date"] = pd.to_datetime(
    df["Ship Date"],
    format="mixed",
    dayfirst=True
)
```

### 6. Feature Engineering

Additional features are created from the existing data.

#### Shipping Days

The number of days required to ship an order is calculated.

```python
df["Shipping Days"] = (
    df["Ship Date"] - df["Order Date"]
).dt.days
```

#### Year

The year is extracted from the order date.

```python
df["Year"] = df["Order Date"].dt.year
```

#### Month Number

The month number is extracted from the order date.

```python
df["Month_Number"] = df["Order Date"].dt.month
```

#### Month

A monthly period feature is created for trend analysis.

```python
df["Month"] = df["Order Date"].dt.to_period("M")
```

## 📈 Exploratory Data Analysis

Exploratory Data Analysis (EDA) is performed to understand patterns and trends in the sales data.

The analysis focuses on areas such as:

* Monthly sales trends
* Sales performance over time
* Product categories
* Customer segments
* Regional data
* Shipping information

## 📌 Key Learning Outcomes

Through this project, I gained practical experience in:

* Working with real-world datasets
* Data cleaning using Pandas
* Handling missing values
* Checking duplicate records
* Converting and working with datetime data
* Feature engineering
* Exploratory Data Analysis
* Identifying sales trends from data

## ▶️ How to Run the Project

### Step 1: Clone the Repository

```bash
git clone https://github.com/Kunallhundare/SpacECE.git
```

### Step 2: Navigate to the Project Folder

```bash
cd SpacECE
```

### Step 3: Install Required Libraries

```bash
pip install pandas jupyter
```

### Step 4: Start Jupyter Notebook

```bash
jupyter notebook
```

### Step 5: Open the Notebook

Open:

```text
Internship Assesment.ipynb
```

Run the cells sequentially to reproduce the complete analysis.

## 👨‍💻 Author

**Kunal Hundare**

B.Sc. Computer Science Student

GitHub: https://github.com/Kunallhundare

## 🙏 Acknowledgment

This project was completed as part of the **SpacECE Internship Assessment**.

---

⭐ If you found this project useful, please consider giving the repository a star!
