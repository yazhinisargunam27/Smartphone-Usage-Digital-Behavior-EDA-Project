# 📊 Social Media Usage Analysis – Exploratory Data Analysis (EDA)

## 📌 Project Overview

This project performs **Exploratory Data Analysis (EDA)** on a large-scale **Social Media Usage dataset containing 1 million records**.

The main objective of this project is to understand user digital behavior, including:

* Daily screen time
* Social media usage
* Gaming habits
* Work/Study time
* Sleep patterns
* App usage
* Notifications
* Age and gender distribution

The project uses Python libraries such as **Pandas, NumPy, Matplotlib, and Seaborn** to clean, analyze, and visualize the data.

---

# 🎯 Project Objectives

The main objectives of this project are:

* Understand the dataset structure
* Perform data cleaning
* Identify missing values
* Detect duplicate records
* Analyze numerical and categorical variables
* Perform univariate analysis
* Perform bivariate analysis
* Study correlations between variables
* Analyze data distribution
* Calculate skewness and kurtosis
* Detect outliers using IQR and Z-score
* Generate meaningful insights

---

# 📂 Dataset Information

The dataset contains approximately **1,000,000 records**, making this a large-scale data analysis project.

### Important Columns

| Column Name             | Description                                |
| ----------------------- | ------------------------------------------ |
| User_ID                 | Unique identification number for each user |
| Age                     | Age of the user                            |
| Gender                  | Gender of the user                         |
| Daily_Screen_Time_Hours | Total daily screen time                    |
| Social_Media_Hours      | Daily time spent on social media           |
| Gaming_Hours            | Daily time spent gaming                    |
| Work_Study_Hours        | Daily time spent on work or studies        |
| Sleep_Hours             | Daily sleeping hours                       |
| Notifications_Per_Day   | Number of notifications received per day   |
| App_Open_Per_Day        | Number of times apps are opened per day    |

---

# 🛠️ Technologies Used

* Python
* Jupyter Notebook
* Pandas
* NumPy
* Matplotlib
* Seaborn
* SciPy

---

# 📊 Exploratory Data Analysis Process

## 1️⃣ Importing Libraries

The required Python libraries were imported for data manipulation, visualization, and statistical analysis.

```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
```

---

## 2️⃣ Loading the Dataset

The dataset was loaded into a Pandas DataFrame.

```python
df = pd.read_csv("social_media_usage.csv")
```

---

## 3️⃣ Understanding the Dataset

The following functions were used:

```python
df.head()
df.tail()
df.shape
df.columns
df.info()
df.describe()
```

These functions help understand:

* Number of rows and columns
* Column names
* Data types
* Statistical summary

---

# 🧹 Data Quality Analysis

## Missing Values

Missing values were checked using:

```python
df.isnull().sum()
```

This helps identify incomplete data.

---

## Duplicate Records

Duplicate records were checked using:

```python
df.duplicated().sum()
```

Duplicates can affect the accuracy of analysis.

---

## Data Types

Data types were checked using:

```python
df.dtypes
```

Correct data types are important for proper analysis.

---

# 📈 Univariate Analysis

Univariate analysis was performed to understand individual variables.

The following visualizations were used:

* Histogram
* Boxplot
* Countplot
* Distribution Plot

Example:

```python
sns.histplot(df["Daily_Screen_Time_Hours"], kde=True)
plt.show()
```

---

# 📊 Categorical Data Analysis

Categorical variables such as **Gender** were analyzed using count plots.

```python
sns.countplot(data=df, x="Gender")
plt.show()
```

This helps understand the distribution of users across different categories.

---

# 📉 Distribution Analysis

The distribution of numerical variables was analyzed using:

* Mean
* Median
* Mode
* Histogram
* Boxplot
* Skewness
* Kurtosis

Example:

```python
df["Daily_Screen_Time_Hours"].mean()

df["Daily_Screen_Time_Hours"].median()

df["Daily_Screen_Time_Hours"].skew()

df["Daily_Screen_Time_Hours"].kurt()
```

---

# 🔗 Bivariate Analysis

Bivariate analysis was performed to study relationships between two variables.

Scatterplots were used to analyze relationships such as:

* Notifications vs App Opens
* Social Media Hours vs Screen Time
* Gaming Hours vs Screen Time
* Sleep Hours vs Screen Time

Example:

```python
sns.scatterplot(
    data=df,
    x="Notifications_Per_Day",
    y="App_Open_Per_Day"
)

plt.show()
```

---

# 🔥 Correlation Analysis

A correlation matrix was created to understand relationships between numerical variables.

```python
corr = df.select_dtypes(include=np.number).corr()

plt.figure(figsize=(12, 8))

sns.heatmap(
    corr,
    annot=True,
    cmap="coolwarm"
)

plt.show()
```

The correlation heatmap helps identify:

* Strong positive relationships
* Strong negative relationships
* Weak relationships

---

# 📦 Outlier Detection

Outliers were detected using two methods.

## IQR Method

```python
Q1 = df["Daily_Screen_Time_Hours"].quantile(0.25)

Q3 = df["Daily_Screen_Time_Hours"].quantile(0.75)

IQR = Q3 - Q1

lower_bound = Q1 - 1.5 * IQR

upper_bound = Q3 + 1.5 * IQR
```

---

## Z-Score Method

```python
from scipy.stats import zscore

z_scores = zscore(df["Daily_Screen_Time_Hours"])

outliers_z = df[np.abs(z_scores) > 3]

outliers_z.shape
```

The Z-score method identifies values that are more than **3 standard deviations away from the mean**.

---

# 📊 Visualizations Used

The following visualizations were created during the analysis:

* 📊 Histograms
* 📦 Boxplots
* 📉 Scatterplots
* 📊 Countplots
* 🔥 Correlation Heatmap

These visualizations help understand data distribution, relationships, and unusual patterns.

---

# 💡 Final Insights

1. The dataset contains approximately **1 million user records**, allowing large-scale analysis of digital behavior.

2. Users show different patterns in **daily screen time**, indicating variations in digital device usage.

3. **Social media usage** is an important component of overall screen time.

4. **Notifications and app opens** help measure user engagement with digital devices.

5. Users demonstrate different behavior patterns related to **social media, gaming, work/study, and sleep**.

6. Correlation analysis helps identify relationships between numerical variables.

7. Distribution analysis using **skewness and kurtosis** helps understand the shape and characteristics of numerical data.

8. Outlier detection using **IQR and Z-score methods** helps identify unusual observations.

9. Visualization techniques make it easier to identify patterns, trends, and relationships in large datasets.

10. The EDA process successfully transformed a large raw dataset into meaningful insights about user digital behavior.

---

# 🧠 Key Learning Outcomes

Through this project, I learned:

* Data loading and exploration
* Data cleaning
* Missing value analysis
* Duplicate analysis
* Data type checking
* Univariate analysis
* Bivariate analysis
* Data visualization
* Correlation analysis
* Distribution analysis
* Skewness and kurtosis
* Outlier detection using IQR
* Outlier detection using Z-score
* Extracting insights from large datasets

---

# 📁 Project Structure

```text
Social-Media-Usage-EDA/
│
├── social_media_usage.csv
│
├── Social_Media_Usage_EDA.ipynb
│
├── images/
│   ├── histogram.png
│   ├── boxplot.png
│   ├── scatterplot.png
│   ├── correlation_heatmap.png
│
└── README.md
```

---

# 🚀 How to Run the Project

### Step 1: Clone the Repository

```bash
git clone <your-repository-link>
```

### Step 2: Install Required Libraries

```bash
pip install pandas numpy matplotlib seaborn scipy
```

### Step 3: Open Jupyter Notebook

```bash
jupyter notebook
```

### Step 4: Run the Notebook

Open:

```text
Social_Media_Usage_EDA.ipynb
```

Run all the cells to perform the complete analysis.

---


# ⭐ Conclusion

This project demonstrates a complete **Exploratory Data Analysis workflow** using a large dataset containing **1 million records**.

The analysis includes data understanding, data quality checks, visualization, distribution analysis, correlation analysis, and outlier detection.

This project helped develop practical skills in **Python, Pandas, NumPy, Matplotlib, Seaborn, and Exploratory Data Analysis**.
