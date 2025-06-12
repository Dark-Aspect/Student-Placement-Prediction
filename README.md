# Student Placement Prediction Project

<div style="text-align: center;">
  <img src="images/Placement.png" alt="Placement Banner" width="600"/>
</div>

## Project Overview
This project utilizes the [Placement Prediction Dataset](https://www.kaggle.com/datasets/ruchikakumbhar/placement-prediction-dataset) from Kaggle to analyze and predict **Student Placement Outcomes**. By exploring academic, soft skill, and extracurricular data, we aim to develop machine learning models that classify whether a student is likely to be placed or not. Understanding the drivers of placement success can help both students and institutions align their training, preparation, and career guidance efforts with industry expectations.

## Problem Statement:
Many students with solid academic records still struggle to secure job placements. This project investigates which factors most significantly influence placement outcomes and builds predictive models to identify students at risk of not being placed. By doing so, stakeholders can take informed action to improve employability.

## Dataset Overview:
The dataset contains **10,000 rows** and **12 columns**. After removing duplicates, **9,928** valid entries remain. Key attributes include:

1. **CGPA** – Academic performance indicator
2. **Internships** – Count of completed internships
3. **Projects** – Number of completed academic/industry projects
4. **Workshops/Certifications** – Participation in skill-enhancing events (renamed as "Trainings")
5. **Aptitude Test Score** – Logical and quantitative aptitude metric
6. **Soft Skills Rating** – Assessment of communication and interpersonal skills
7. **Extracurricular Activities** – Indicates holistic development
8. **Placement Training** – Whether placement training was taken
9. **SSC & HSC Marks** – Secondary and higher secondary education performance
10. **Placement Status** – Target variable: **Placed** or **Not Placed**

> ⚠️ *Disclaimer*: The goal is to build predictive tools and derive insights, not to stereotype or oversimplify student capabilities. Ethical analysis and transparency are essential throughout the process.

## Links to Notebooks

* **Step 1: Data Wrangling**
  `01_data_wrangling.ipynb` – Cleans, deduplicates, and renames columns. Feature engineering and data inspection are also covered.
  🔗 [View Notebook](./01_data_wrangling.ipynb)

* **Step 2: EDA – Visualization**
  `02_eda_visualization.ipynb` – Uses plots and charts to explore relationships between academic, soft skill, and placement factors.
  🔗 [View Notebook](./02_eda_visualization.ipynb)

* **Step 3: EDA – SQL Queries**
  `03_eda_sql_queries.ipynb` – SQL analysis for summarizing numerical trends across placement groups.
  🔗 [View Notebook](./03_eda_sql_queries.ipynb)

* **Step 4: Modeling & Prediction**
  `04_modeling_prediction.ipynb` – Builds machine learning models to predict Placement Status using the prepared dataset.
  🔗 [View Notebook](./04_modeling_prediction.ipynb)

## Section Summaries

### Step 1: Data Wrangling & Cleaning

The data wrangling phase ensured quality and consistency. A total of 72 duplicate entries were removed, leaving 9,928 valid records. The column "Workshops/Certifications" was renamed to Trainings for clarity, and no missing values were detected. Summaries revealed an average CGPA of 7.7, most students completed about two projects, and 73% attended placement training. Despite strong academic indicators, many students remained unplaced, hinting that non-academic factors may also influence placement decisions.

### Step 2: Exploratory Data Analysis (EDA)

This step explores patterns in both categorical and numerical features through visualizations. Insights showed that students with 1–2 internships, at least two projects, and those who participated in placement training or extracurricular activities had higher placement odds. Numerical variables such as CGPA, aptitude scores, soft skills, and academic marks (SSC and HSC) also revealed strong associations with placement outcomes. Students with higher scores were generally more likely to be placed, and outliers were minimal, indicating clean and consistent trends.

<p align="center">
  <img src="images/Boxplots.png" alt="Relationship Between Each Numerical Variable and Placement Status" />
</p>

This boxplot visualization compares numerical features between placed and not-placed students. It reveals that higher CGPA, aptitude, and soft skills scores are commonly associated with successful placement outcomes.

<p align="center">
  <img src="images/Correlation_Heatmap.png" alt="Correlation Heatmap" />
</p>

The heatmap displays correlations between numerical variables in the dataset.
CGPA, aptitude scores, and project show strong positive relationships with each other and placement status.

### Step 3: SQL-Based Analysis

To validate visual findings, SQL queries were used to analyze trends between placed and not-placed students. Placed students had an average CGPA of 8.01 compared to 7.47 for not placed, and higher ratings in soft skills (4.53 vs. 4.17) and aptitude (84.36 vs. 75.83). A clear correlation was found with the number of projects completed, as students with three projects had the highest placement rate. However, internship experience showed less impact in this dataset. These results reaffirm that academic performance, aptitude, and soft skills are key placement predictors.

### Step 4: Modeling and Hyperparameter Tuning

In this phase, four models—Decision Tree, KNN, Random Forest, and Gradient Boosting—were trained and evaluated. After preprocessing and cross-validation, Gradient Boosting emerged as the best model with the highest accuracy (80.11%) and F1-score. It demonstrated strong balance across precision and recall for both "Placed" and "Not Placed" classes. Hyperparameter tuning further enhanced model performance. Gradient Boosting had the fewest misclassifications, making it the most robust choice for student placement prediction.

<p align="center">
  <img src="images/Cross_Validation_Distribution.png" alt="Cross Validation Score Distribution" />
</p>

This plot illustrates the distribution of cross-validation scores across the trained models.
Gradient Boosting delivered the most consistent and highest performance.

<p align="center">
  <img src="images/Confusion_Matrix.png" alt="Confusion Matrix" />
</p>

The confusion matrix reveals the prediction accuracy for both placed and not-placed students.
It shows fewer misclassifications, confirming strong model reliability.

<p align="center">
  <img src="images/Feature_Importance_Ranking.png" alt="Feature Importance Ranking" />
</p>

This plot shows which features most influenced placement predictions.
Extracircular activities, HSC marks, and Aptitude scores were among the top contributors.

### Model Comparison

In the modeling phase, four classifiers were evaluated to predict student placement outcomes. Gradient Boosting emerged as the top-performing model, achieving 80.11% accuracy after hyperparameter tuning, along with the highest F1-score and balanced precision-recall across both classes. Random Forest and KNN also performed well but showed slightly lower precision or recall for placed students. Decision Tree underperformed and was excluded from final selection. Overall, Gradient Boosting proved the most reliable and interpretable model for this dataset, making it the best choice for placement prediction.

## Conclusion

This project emphasizes the importance of integrating academic performance, technical skills, and soft skill metrics to effectively assess placement readiness. It highlights the value of clean and well-prepared data, along with thoughtful feature selection. Through balanced model evaluation using cross-validation and F1-scores, it underscores the critical role of real-world experiences like projects, aptitude, and soft skills in driving student employability.

### Future Work

* Explore advanced models like XGBoost and LightGBM.
* Include college name, industry domain, or job role if available.
* Apply stratified k-fold cross-validation for more consistent evaluation.

#### Thank you, Feedback would be appreciated!!!