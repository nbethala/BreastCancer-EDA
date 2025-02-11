# Exploratory Data Analysis - Breast Cancer

## Synthetic Breast Cancer Survival Prediction


## Table of Contents  

 [Project Introduction](#project-introduction)\
 [Data Overview](#data-overview)\
 [Data Cleaning and Preprocessing](#data-cleaning-and-preprocessing)\
        [1.Box Plots](#1box-plots)\
        [2.Z-Scores](#2z-scores)\
        [3.IQR-Interquartile Range](#3iqr-interquartile-range)\
 [Data Visualization](#data-visualization)\
 [Univariate Analysis:](#univariate-analysis-)\
 [Bivariate and Multivariate Analysis](#bivariate-and-multivariate-analysis)\
 [Conclusion](#conclusion-)


# Project Introduction
Breast cancer remains one of the most prevalent and significant health concerns globally, making early detection and accurate prognosis is critical for patient care. Predicting breast cancer survival plays a pivotal role in guiding treatment decisions and improving patient outcomes. This project aims to apply Exploratory Data Analysis (EDA) techniques to a synthetic dataset for predicting breast cancer survival.

By the end of the analysis, we hope to gain valuable insights that not only contribute to better survival prediction but also aid in understanding the key factors affecting breast cancer survival rates. This project emphasizes the importance of data-driven decisions in the healthcare field and aims to provide a meaningful impact on the fight against breast cancer.

# Data Overview
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

- **Data Transformation:** Visualization tools require numerical input, so categorical variables (such as labels, categories, or strings) need to be encoded into a numerical format. There are several methods to encode categorical variables, depending on the nature of the data and the tool being used. Since our data contains ordinal relationship between categories, Label Encoding technique will be used to assign each category a unique integer value.  
  
  
- **Outlier Detection:**
  Outliers are data points that deviate significantly from other observations. Identifying and understanding outliers is crucial for a comprehensive analysis, as they can influence statistical measures and provide insights into the diversity and complexity of the underlying medical conditions within the dataset. 

In this dataset, the methods used are box plots, z-scores, or the IQR (Interquartile Range) method to detect outliers. Depending on the analysis outliers can be removed, transformed or kept. 

   #### 1.Box Plots
 To visualize the distribution of each numerical feature in the dataset, box plots are an effective way to identify outliers. The box plot shows the spread of the data, with the whiskers representing the range of the data within 1.5 times the interquartile range (IQR). Data points beyond these whiskers are considered potential outliers.
 
  ![Boxplot_PositiveAxillaryNodes](https://github.com/user-attachments/assets/6f4be8f0-1087-49a7-9c67-a802c75ddea0)

    
  ![Boxplot_Tumorsize](https://github.com/user-attachments/assets/ed17a5d1-da63-46d5-9aaa-d6da4b41d35b)


   #### 2.Z-Scores
   Outliers are typically defined as data points with a Z-score greater than 3 or less than -3, although this threshold can vary depending on the context.

   

   #### 3.IQR-Interquartile Range
Outliers are data points that fall below the lower bound or above the upper bound.
Lower Bound: Q1 - 1.5 * IQR
Upper Bound: Q3 + 1.5 * IQR
  

# Data Visualization

# Univariate Analysis
 Univariate analysis focuses on the examination of a single variable at a time. It's an essential part of Exploratory Data Analysis 
 (EDA), as it allows to summarize, understand, and explore the underlying characteristics and patterns of individual variables. This 
  helps in identifying important characteristics, distributions, and potential issues such as outliers or skewness. 
  
  **Question:** What is the distribution of positive axillary nodes in the patients?
  
  **Analysis:** The distribution appears to be left skewed indicating that the majority of the observations have a lower number of positive axillary nodes, with fewer observations having high numbers. The curve suggests that lower number of positive nodes are more frequent, with the frequency decreasing as the number of nodes increases. This type of distribution is common in medical data, where a majority of cases fall within a certain range, with fewer cases at the extremes. 

  ![distribuition_positiveNodes](https://github.com/user-attachments/assets/7150b082-9687-474e-bfd2-acb03c3eb305)


   **Question:**  What is the distribution of Tumor size in the patients ?
   
   **Analysis:** The smallest tumor size is 0.5 mm and the largest tumor size is 5 mm. Majority of tumors appear between 3-5 mm in distribution.    
The tumor size distribution, as depicted by the boxplot, reveals several key insights into the variability and spread of tumor sizes among the patients.The distribution's wide IQR and long whiskers suggest that while most patients’ tumor sizes are concentrated within a moderate range, there are still substantial differences, indicating diversity in the data. This variability could have important implications for understanding treatment efficacy, prognosis, and individual patient care.

Absence of Outliers: One noteworthy feature is the lack of outliers in the dataset. Outliers are often indicative of rare or extreme cases, and their absence in this case suggests that tumor sizes are relatively consistent across the patient population. This is important for making general conclusions, as it means that there aren’t any data points that deviate drastically from the rest of the group, which could have skewed the analysis or led to misleading interpretations.


 ![distribuition_Tumorsize](https://github.com/user-attachments/assets/807eb29b-bdc1-4aae-b2b9-90e0d67c4047)


 **Question:** How is the dataset distributed across different marital statuses? What percentage of patients belong to each category?

**Analysis:** There are 70.4% of married people and 29.6% of Single people in our dataset

 ![distribuition_MaritalStatus](https://github.com/user-attachments/assets/e71db5bf-43b2-4b57-a8d5-95b32601cd73)


**Question:** What is the cumulative distribution of age groups? How does it illustrate the overall distribution of patients across different age groups?

**Analysis:** The steepest rise in the curve occurs in the below 50 age group, indicating that a large proportion of individuals fall within this category. 

![Cumulative_distributionPlot](https://github.com/user-attachments/assets/d56064de-7151-4937-a83f-23e3aaf6f23a)


# Bivariate and Multivariate Analysis 
Bivariate and Multivariate analysis is a crucial step in understanding the relationships between pairs of variables. Using scatter plots, line charts, box plots, and heatmaps, you can uncover connections, identify trends, and visualize the distribution of variables. These techniques help in drawing insights from the data, whether you're exploring clinical outcomes, treatment effectiveness, or disease progression. 

Below is a breakdown of each of the methods to analyze the dataset: 

1. **Correlation Heatmap:** Using a correlation heatmap is an effective way to perform bivariate correlation analysis in a dataset.
      The correlation coefficient can range from -1 (perfect negative correlation) to +1 (perfect positive correlation). A coefficient of 0 indicates no correlation.

   **Analysis:** Age and Year of Operation show the strongest positive correlation at 0.05. 
              Radiotherapy and Survival status show the strongest negative correlation at -0.055
              Many variables show weak correlations close to zero, indicating little to no linear relationship between them. 

  ![CorrelationMatrix_Heatmap](https://github.com/user-attachments/assets/9c76648d-b3bc-4db0-827e-0d557baa5e25)


  2. **Question:** How many patients in each age group underwent surgery each year? Is there a relationship between age group and operational activities during that time period?
     
     **Analysis:** Key observations from the heat map:
     
     The 65-70 age group shows a relatively high count accross the years, particularly in the mid 60's. The 30-35 and 80-85 age groups generally have lower counts 
    throughout the observed time period. The years 1964 and 1968 appear to have higher counts accross several age groups compared to 1958,1960 and 1962. This suggests a 
    potential increase in the number of individuals observed during these years. There is a noticeable concentration of higher counts within the 65-70 age during 1960 
   showing a strong relationship.
     

![BivariateAnalysis_Heatmap](https://github.com/user-attachments/assets/4a03bc28-c78f-4350-8f46-b5118fec8185)

     
3. **Box Plot:** A box and whisker plot is an effective tool for visualizing the distribution, central tendency, spread, and outliers in a dataset, allowing for a quick understanding of the data's overall characteristics. Lets answer some of the below questions:

   **Questions:**
   Plot1: Does the age distribution differ between patients who survived and those who did not? Are there any significant variations in the median age or the range of ages 
   across different survival outcomes?

   Plot2: Are there any trends or patterns in the distribution of operation years based on patient survival status? Does the boxplot show any significant differences in 
   the years of operation between patients who survived and those who did not?

   Plot3: How does the distribution of positive axillary nodes vary between patients with different survival outcomes? Are there notable differences in the spread of 
   positive axillary nodes between survivors and non-survivors?

   **Analysis:** The box plots for patient age and year of operation show similar statistical patterns, indicating that the distribution of these variables may share 
    comparable characteristics. In contrast, the box plot for positive axillary nodes highlights a significant presence of outliers, a typical feature in medical datasets. 
    This is an exploratory analysis, and further testing would be needed to confirm the significance of this observation. 


![SurvivalStatus_Boxplot](https://github.com/user-attachments/assets/23f04ee5-f2e3-42a6-9770-faf3c0910226)



4. **Violin plot:** A violin plot is a data visualization that combines aspects of a box plot and a kernel density plot to provide a more detailed view of the distribution of a dataset.

    **Question:**
   
    Plot1: How does the age distribution differ between patients who survived and those who did not?

    Plot2: What insights can be drawn from the year of operation for patients with varying survival outcomes?

    Plot3: How does the distribution of positive axillary nodes differ between patients with different survival outcomes?

    Plot4: How does the distribution of tumor size differ between patients with varying survival outcomes?
   

    **Analysis:** In the violin plot of positive axillary nodes, the distribution is observed to be highly skewed for both the survival/deceased groups. This suggests that 
    for the majority of patients in both groups, the number of positive axillary nodes detected is relatively low. The distribution is right-skewed, it means that most 
    patients in both groups have fewer positive axillary nodes, but there are a smaller number of patients with a much higher number of positive nodes. 


![Violinplot_Age](https://github.com/user-attachments/assets/1b6b863e-e667-4acb-a182-9a6b7d69a0c5)
![Violinplot_YearofOperation](https://github.com/user-attachments/assets/7c0a9ca5-d984-4607-8cc5-dac54104a7c7)
![ViolinPlot_PositiveNodes](https://github.com/user-attachments/assets/4899e028-5ad2-4220-a162-9f6b3d4c6ce4)
![ViolinPlot_TumorSize](https://github.com/user-attachments/assets/d85b34fe-5481-4f9a-bfac-acaf0d91daa4)



5. **Pair Plot:** We used a pair plot to explore the relationships between variables and to distinguish patterns based on survival status. By color-coding the data points according to whether patients survived or not, we can identify if certain combinations of features are linked to better or worse outcomes. This method provides valuable insights into the complex factors influencing breast cancer survival.

   **Analysis:** The pair plot shows symmetry between the upper and lower halves of the diagonal, meaning the relationships between feature pairs remain the same when the 
    axes are swapped. Therefore, analyzing just one half of the plot provides the same insights as analyzing both.

    The diagonal displays kernel density-smoothed histograms, which help us understand the distribution of each feature and identify any patterns, such as skewness or 
   peaks.

    A key observation is the significant overlap between feature pairs in the scatter plots. This overlap suggests that the features do not clearly separate the different 
    class labels (e.g., cancer survivors vs. non-survivors), indicating that these features might not be the best for distinguishing between classes.


![PairPlot](https://github.com/user-attachments/assets/f9f7ea76-9c50-4bba-bc39-0a2ae6cbffe6)


6. **Scatter Plot:** Is there a correlation between Tumor_Size and the number of Positive_Axillary_Nodes?

   **Analysis:** Based on the scatter plot, a higher concentration of patients survived is observed towards the lower end of positive axillary nodes (0-10), suggesting a correlation between fewer positive nodes and better survival rates. The patients deceased are more scattered across the range of positive axillary nodes in the 10-40 range, indicating that a higher number of nodes might be associated with a lower survival rate. For the smaller Tumor sizes (0-2) the survival rate appears higher. There are outliers, particularly with a higher number of positive axillary nodes (above 40), where some patients did survive, indicating that other factors might influence survival outcomes. However, more comprehensive analysis is needed to draw definitive conclusions for healthcare decision-making.


![ScatterPlot](https://github.com/user-attachments/assets/c9c9257f-b559-44bc-8d3f-22945ad191dd)
 

7. **Joint Plot:** The joint plot visualizes the relationship between two features by combining a scatter plot in the center displaying data as points, while the histograms at the top margin and the right margins showing the distribution of the respective features.

   **Question:** Is there a relationship between Age and the positive axillary nodes ?

   **Analysis:** The Histogram at the top displays a uniform distribution of patient ages, with a slight peak around 50-60 age range. The histogram on the right shows a skewed distribuition with most patients having (0-10) positive axillary nodes. The plot reveals that most patients regardless of age tend to have a lower number of nodes. There is a higher density of points clustered near the bottom of the plot (0-10), suggesting that this is a common occurence. There are few outliers indicating data points with higher number of positive nodes even at older ages that warrant further investigation. In summary age does not strongly correlate with the number of positive axillary nodes.


![JointPlot](https://github.com/user-attachments/assets/6393dc33-28f8-4421-a4f5-688829b818ab)


8. **Distribution plot:** A distribution plot, or probability density function (PDF) plot, is a useful visualization that shows how data points are spread across a range of values. It helps analysts see the underlying distribution, which can inform decisions about statistical modeling or hypothesis testing.

    **Analysis:** The plot visualizes the distribution of age differentiated by survival status. The plot indicates that the age distribution of deceased individuals skews slightly older compared to those who survived, with both groups peaking between approximately 50 and 60 years old. The density is higher in the older ranges 60-80 and lower in the younger age ranges 20-40. This suggests that older individuals in this dataset have a higher likelihood of not surviving while younger individuals have a higher likelyhood of survival. 


![DistributionPlot](https://github.com/user-attachments/assets/50b15137-7d09-429d-a2fa-d7c47c62d285)

    
9. **Contour Plot:** The contour plot visualizes the relationship between Age and Year of Operation, displaying the density distribution of data points accross these two variables. 

    **Analysis:** The plot shows a higher concentration of data points in the age range of approximately 30 to 70 years and the year of operation ranges of 1960-1968 suggesting that most of the operations occured within this time frame and age groups. 

  
  ![ContourPlot](https://github.com/user-attachments/assets/9fdfc93c-1325-4999-aadf-84ae598d0254)

   

# Conclusion
In Exploratory Data Analysis (EDA) of the breast cancer survival prediction dataset, our primary objective was to uncover patterns, identify anomalies, and extract insights that could influence survival outcomes. By utilizing various EDA techniques and tools such as Python and the pandas library, we successfully gained a clearer understanding of the dataset. Descriptive statistics and visualizations revealed key trends, identified outliers, and highlighted potential factors impacting survival rates.This EDA phase has not only provided valuable insights but also set the stage for further modeling and hypothesis testing, with the aim of developing an effective prediction model for breast cancer survival.







