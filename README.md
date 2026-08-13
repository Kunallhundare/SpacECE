# SpacECE Internship Assessment | Sales Data Analysis

![Python](https://img.shields.io/badge/Python-Data%20Analysis-blue)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Processing-green)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange)
![Status](https://img.shields.io/badge/Project-Completed-success)

> **A comprehensive sales data analysis project focused on data cleaning, feature engineering, and exploratory data analysis to uncover meaningful business insights.**

---

## 📌 Table of Contents

* [Project Overview](#-project-overview)
* [Objectives](#-objectives)
* [Dataset](#-dataset)
* [Project Workflow](#-project-workflow)
* [Data Preprocessing](#-data-preprocessing)
* [Feature Engineering](#-feature-engineering)
* [Exploratory Data Analysis](#-exploratory-data-analysis)
* [Technologies Used](#-technologies-used)
* [Repository Structure](#-repository-structure)
* [Installation and Usage](#-installation-and-usage)
* [Key Skills Demonstrated](#-key-skills-demonstrated)
* [Future Improvements](#-future-improvements)
* [Author](#-author)

---

## 🚀 Project Overview

This project was developed as part of the **SpacECE Internship Assessment**.

The objective of the project is to perform a structured analysis of a sales dataset using Python. The project demonstrates the complete data analysis workflow, starting from raw data inspection and cleaning to feature engineering and exploratory data analysis.

The analysis helps transform raw transactional data into meaningful information that can support business understanding and decision-making.

### The project follows this workflow:

```text
Raw Dataset
     │
     ▼
Data Understanding
     │
     ▼
Data Cleaning
     │
     ▼
Data Preprocessing
     │
     ▼
Feature Engineering
     │
     ▼
Exploratory Data Analysis
     │
     ▼
Business Insights
```

---

## 🎯 Objectives

The main objectives of this project are to:

* Analyze the structure and quality of the dataset.
* Identify and handle missing values.
* Detect duplicate records.
* Convert date columns into appropriate datetime formats.
* Create new features from existing data.
* Analyze sales trends over time.
* Understand shipping performance.
* Explore patterns across customers, products, categories, and regions.
* Generate meaningful insights through Exploratory Data Analysis.

---

## 📂 Dataset

The project uses the `train.csv` dataset containing **9,800 records and 18 features**.

The dataset contains information related to:

* Orders
* Customers
* Products
* Sales
* Categories
* Geographic regions
* Shipping details

### Key Dataset Features

| Feature         | Description                       |
| --------------- | --------------------------------- |
| `Row ID`        | Unique identifier for each record |
| `Order ID`      | Unique identifier for an order    |
| `Order Date`    | Date when the order was placed    |
| `Ship Date`     | Date when the order was shipped   |
| `Ship Mode`     | Method used for shipping          |
| `Customer ID`   | Unique customer identifier        |
| `Customer Name` | Name of the customer              |
| `Segment`       | Customer segment                  |
| `Country`       | Customer's country                |
| `City`          | Customer's city                   |
| `State`         | Customer's state                  |
| `Postal Code`   | Customer postal code              |
| `Region`        | Geographic region                 |
| `Product ID`    | Unique identifier for a product   |
| `Category`      | Product category                  |
| `Sub-Category`  | Product sub-category              |
| `Product Name`  | Name of the product               |
| `Sales`         | Sales value of the order          |

---

## 🔄 Project Workflow

### 1️⃣ Data Loading

The dataset is imported using the Pandas library.

```python
import pandas as pd

df = pd.read_csv("train.csv")
```

Initial records are inspected using:

```python
df.head()
```

---

### 2️⃣ Data Understanding

The dataset is analyzed to understand:

* Number of rows and columns
* Column names
* Data types
* Missing values
* Dataset structure

```python
df.shape
df.info()
df.describe()
```

---

## 🧹 Data Preprocessing

### Missing Value Analysis

Missing values are identified using:

```python
df.isnull().sum()
```

The missing values in the `Postal Code` column are handled using the median value.

```python
df["Postal Code"] = df["Postal Code"].fillna(
    df["Postal Code"].median()
)
```

### Duplicate Record Check

The dataset is checked for duplicate records.

```python
df.duplicated().sum()
```

This step ensures the dataset is suitable for further analysis.

---

## ⚙️ Feature Engineering

New features are created to extract additional information from the date columns.

### Shipping Days

The time taken to ship an order is calculated using:

```python
df["Shipping Days"] = (
    df["Ship Date"] - df["Order Date"]
).dt.days
```

### Year

```python
df["Year"] = df["Order Date"].dt.year
```

### Month Number

```python
df["Month_Number"] = df["Order Date"].dt.month
```

### Month

```python
df["Month"] = df["Order Date"].dt.to_period("M")
```

These newly created features help analyze sales and shipping patterns over time.

---

## 📊 Exploratory Data Analysis

Exploratory Data Analysis is performed to identify important patterns and trends in the dataset.

The analysis includes:

### 📅 Sales Trend Analysis

* Monthly sales performance
* Sales trends over time
* Year-wise sales analysis

### 🛍️ Product Analysis

* Category-wise sales
* Sub-category performance
* Product-level analysis

### 👥 Customer Analysis

* Customer segments
* Sales distribution across segments
* Customer purchasing patterns

### 🌍 Regional Analysis

* Region-wise sales
* State-wise analysis
* Geographic sales performance

### 🚚 Shipping Analysis

* Shipping modes
* Average shipping duration
* Order-to-shipment time analysis

---

## 🛠️ Technologies Used

| Technology       | Purpose                              |
| ---------------- | ------------------------------------ |
| Python           | Core programming language            |
| Pandas           | Data manipulation and analysis       |
| Jupyter Notebook | Interactive development and analysis |

---

## 📁 Repository Structure

```text
SpacECE/
│
├── Internship Assesment.ipynb
│   └── Complete data analysis workflow
│
├── train.csv
│   └── Dataset used for analysis
│
└── README.md
    └── Project documentation
```

---

## 💻 Installation and Usage

### 1. Clone the Repository

```bash
git clone https://github.com/Kunallhundare/SpacECE.git
```

### 2. Navigate to the Project Directory

```bash
cd SpacECE
```

### 3. Install Dependencies

```bash
pip install pandas jupyter
```

### 4. Start Jupyter Notebook

```bash
jupyter notebook
```

### 5. Run the Project

Open the following file:

```text
Internship Assesment.ipynb
```

Run all cells sequentially to execute the complete analysis.

---

## 🧠 Key Skills Demonstrated

This project demonstrates practical knowledge of:

* Python Programming
* Data Analysis
* Data Cleaning
* Missing Value Handling
* Duplicate Detection
* Data Preprocessing
* Datetime Manipulation
* Feature Engineering
* Exploratory Data Analysis
* Sales Trend Analysis
* Business Data Interpretation
* Pandas Library
* Jupyter Notebook

---

## 📈 Key Outcomes

Through this project, the raw sales data is transformed into an analysis-ready dataset.

The project demonstrates how data can be:

```text
Collected
   ↓
Cleaned
   ↓
Processed
   ↓
Analyzed
   ↓
Converted into Insights
```

This workflow reflects a practical approach used in real-world **Data Analyst and Data Science projects**.

---

## 🔮 Future Improvements

The project can be extended with the following improvements:

* [ ] Add advanced data visualizations using Matplotlib and Seaborn.
* [ ] Create an interactive Power BI dashboard.
* [ ] Perform customer segmentation.
* [ ] Build sales forecasting models.
* [ ] Add machine learning models for sales prediction.
* [ ] Create an interactive Streamlit web application.
* [ ] Add automated data validation.
* [ ] Generate downloadable business reports.

---

## 👨‍💻 Author

### **Kunal Hundare**

**B.Sc. Computer Science | Aspiring Data Analyst | Python & Data Analytics Enthusiast**

🔗 GitHub: https://github.com/Kunallhundare

📂 Project Repository: https://github.com/Kunallhundare/SpacECE

---

## 🙏 Acknowledgment

This project was completed as part of the **SpacECE Internship Assessment**.

---

### ⭐ Support

If you found this project interesting or useful, please consider giving the repository a **Star ⭐**.

Your support motivates me to build and share more projects!

**Thank you for visiting this repository!**
