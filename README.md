# Exploratory Data Analysis - Breast Cancer

## EDA of Synthetic Breast Cancer Survival Data

## Table of Contents  
#### [1.Project Introduction](https://github.com/nbethala/BreastCancer-EDA/edit/main/README.md#project-introduction)  

#### [2.Data Overview](https://github.com/nbethala/BreastCancer-EDA/edit/main/README.md#data-overview)         
 - #### [Data Source]()
 - #### [Features]()      
 - #### [Variables]()

       
#### [3.Data Cleaning and Preprocessing](https://github.com/nbethala/BreastCancer-EDA/edit/main/README.md#data-cleaning-and-preprocessing)
  - #### [Handling Missing Values]()
   - #### [Removing Irrelevant Features]()
   - #### [Eliminate Duplicate Rows]()
   - #### [Outlier Detection]()
   - #### [Data Transformation]()

#### [4.Data Visualization](https://github.com/nbethala/BreastCancer-EDA/edit/main/README.md#data-visualization)

#### [5.Univariate Analysis](https://github.com/nbethala/BreastCancer-EDA/edit/main/README.md#univariate-analysis)
 
#### [6.Bivariate Analysis](https://github.com/nbethala/BreastCancer-EDA/edit/main/README.md#bivariate-analysis)
 
#### [7.Multivariate Analysis](https://github.com/nbethala/BreastCancer-EDA/edit/main/README.md#multivariate-analysis)
    
#### [8.Key Findings and Insights](https://github.com/nbethala/BreastCancer-EDA/edit/main/README.md#key-findings-and-insights)

#### [9.Limitations and Considerations](https://github.com/nbethala/BreastCancer-EDA/edit/main/README.md#limitations-and-considerations)

#### [10.conclusion](https://github.com/nbethala/BreastCancer-EDA/edit/main/README.md#conclusion)



# Project Introduction
Breast cancer remains one of the most prevalent and significant health concerns globally, making early detection and accurate prognosis is critical for patient care. Predicting breast cancer survival plays a pivotal role in guiding treatment decisions and improving patient outcomes. This project aims to apply Exploratory Data Analysis (EDA) techniques to a synthetic dataset for predicting breast cancer survival.

By the end of the analysis, we hope to gain valuable insights that not only contribute to better survival prediction but also aid in understanding the key factors affecting breast cancer survival rates. This project emphasizes the importance of data-driven decisions in the healthcare field and aims to provide a meaningful impact on the fight against breast cancer.

# Data Overview:
The dataset includes a variety of features such as the patient's age at diagnosis, tumor size, number of positive axillary nodes, and the year of surgery. By analyzing these factors, we seek to uncover patterns and relationships that can help predict patient survival. Through the application of EDA, we will first explore the data, identify trends, detect any missing values or anomalies, and visualize critical features to gain insights into their impact on survival.

 - **Data Source:**
     The data used in this project is sourced from a synthetic breast cancer survival dataset from Kaggle. While this dataset is synthetic, it is 
    constructed to closely resemble real-world data and is frequently used in various studies to explore survival prediction 
    techniques.
 - **Number of Observations:**
     The dataset contains 2000 observations and 10 features
 - **Features:**
     The dataset contains a variety of features, each categorized into different data types, including categorical and numerical variables.
   
    Patient_ID: A unique identifier for each patient in numeric values
   
    Age Range: 30 to 84 (Numeric)
   
    Marital Status: Single, Married(Categorical)
   
   Year of Operation: Ranges from 1958 to 1970(Numeric)
   
   Positive Axillary Nodes (Lymph Nodes): Numeric
   
   Tumor Size: Numeric ranges from 0.5 to 5.0
   
   Radiation Therapy, Chemotherapy, Hormone Therapy: Categorical Values
   
   Survival Status: Numeric 1 (Survived), 2 (Deceased)

   --Descriptive statistics Image--

# Data Cleaning and Preprocessing
 Data cleaning is a critical part of the Exploratory Data Analysis (EDA) process. It ensures the dataset is free from errors, inconsistencies, and missing values, which could distort the analysis and model performance.
 
- **Impute missing values:**
    In this dataset, only the ‘Age’ and the ‘Marital_Status’ columns has missing values.
     Age: For numerical feature, replace missing values with the mean of the column.
     Marital Status: For categorical variable, replace missing values with the most frequent value (mode).
  
- **Removing Irrelevant Features:**
    The Patient_ID column, which has no predictive value for the survival status, can be dropped. Removing irrelevant features like Patient_ID helps simplify the dataset and improve model performance by focusing only on meaningful variables. 
  
- **Eliminate Duplicate Rows:**
  The Datasets contained duplicate rows or records. Use drop_duplicates() in Python to identify and remove any duplicated data.
  
- **Outlier Detection:**
  Outliers are data points that deviate significantly from other observations. Identifying and understanding outliers is crucial for a comprehensive analysis, as they can influence statistical measures and provide insights into the diversity and complexity of the underlying medical conditions within the dataset. 

In this dataset, the methods used are box plots, z-scores, or the IQR (Interquartile Range) method to detect outliers. Depending on the analysis outliers can be removed, transformed or kept. 

   #### 1.Box Plots
    Boxplots provide a visual representation of data distribution and highlight potential outliers by showing the interquartile range (IQR). Data points outside 1.5 times the IQR above Q3 or below Q1 are typically considered outliers.

 In this dataset, the feature Positive_Axillary_Nodes is identified as an outlier.
 
    --BOX PLOT IMAGE --

   #### 2.Z-Scores
   Outliers are typically defined as data points with a Z-score greater than 3 or less than -3, although this threshold can vary depending on the context.

   #### 3.IQR (Interquartile Range)
Outliers are data points that fall below the lower bound or above the upper bound.
Lower Bound: Q1 - 1.5 * IQR
Upper Bound: Q3 + 1.5 * IQR
  
- **Data Transformation:** encoding categorical variables

# Data Visualization

# Univariate Analysis:
 Univariate analysis focuses on the examination of a single variable at a time. It's an essential part of Exploratory Data Analysis 
 (EDA), as it allows to summarize, understand, and explore the underlying characteristics and patterns of individual variables. This 
  helps in identifying important characteristics, distributions, and potential issues such as outliers or skewness. 
  
  **Question:** What is the distribution of positive axillary nodes in the patients?
  **Analysis:** The distribution seems to be left-skewed, with the mode (most frequent value) located around 0 positive axillary nodes. A few data points extend toward the higher end, reaching up to 50 positive axillary nodes. The left tail of the distribution is longer than the right, indicating that there are more instances with lower numbers of positive axillary nodes compared to those with higher values.

  --Image Distribution of positive axillary node---

    **Question:** What is the distribution of Tumor size in the patients ?
    **Analysis:** The smallest tumor size is 0.5 mm and the largest tumor size is 5 mm. Majority of tumors appear between 3-5 mm in distribution.    
The tumor size distribution, as depicted by the boxplot, reveals several key insights into the variability and spread of tumor sizes among the patients.The distribution's wide IQR and long whiskers suggest that while most patients’ tumor sizes are concentrated within a moderate range, there are still substantial differences, indicating diversity in the data. This variability could have important implications for understanding treatment efficacy, prognosis, and individual patient care.

Absence of Outliers: One noteworthy feature is the lack of outliers in the dataset. Outliers are often indicative of rare or extreme cases, and their absence in this case suggests that tumor sizes are relatively consistent across the patient population. This is important for making general conclusions, as it means that there aren’t any data points that deviate drastically from the rest of the group, which could have skewed the analysis or led to misleading interpretations.

 --Image Distribution of Tumor Size---

# Bivariate Analysis:

# Multivariate Analysis:

# Key Findings and Insights:

# Limitations and Considerations:

# Conclusion:







