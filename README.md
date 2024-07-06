<h1 align="center">HR Analytics Employee Attrition & Performance </h1>

##### 
<p align="center">
  <img src="https://github.com/gentallman/HR_Attrition_Analytics/assets/78334851/b37e59f3-3c58-4e17-bb87-60640f892807" width="300">
</p>

####

<a href="https://app.powerbi.com/view?r=eyJrIjoiOGU3MTE4OTUtNGM5MS00ZTAyLTk1MjAtZGVjZmIyZmFjNmU4IiwidCI6IjNmMTcwMmFmLTNmNGUtNDk1ZS04YzhiLTEzNzIxZjM5YjFiMCJ9">
  <img src="https://github.com/gentallman/Retail-Supply-Chain-Operations-Management/assets/78334851/ed21a0ff-f400-4a4d-9a6c-80c76bf137e7" alt="Live Project" width="100">
</a>


####

HR Analytics involves methodically gathering, analyzing, and interpreting Human Resource (HR) data to boost organizational efficiency and guide strategic decision-making. Through employing sophisticated analytical methods, HR Analytics converts raw HR data into practical insights, empowering organizations to refine their workforce management strategies and synchronize HR efforts with overarching business goals.

![HR Dashboard](https://github.com/gentallman/HR_Attrition_Analytics/assets/78334851/2a6daa5b-f9cd-4944-bf53-7f295b4af6a0)

<h2> Call for HR Analytics </h2>

* The necessity of HR Analytics arises from:  
  * The increasing complexity of the modern business landscape
  * The growing importance of human capital in driving organizational success

* While organizations may possess vast amounts of HR data, access alone is insufficient for deriving meaningful insights.
* HR Analytics bridges this gap by:
  * Providing HR professionals with tools and methodologies to extract actionable insights from HR data
  * Empowering them to address critical business challenges such as talent retention, recruitment optimization, and performance management
* Employee Attrition:
  * Refers to the process of employees leaving an organization voluntarily
  * Can result from resignation, retirement, or other reasons
  * Leads to a reduction in the organization's workforce size
* Implications of employee attrition include:
  * Increased recruitment costs
  * Loss of institutional knowledge
  * Decreased morale among remaining employees
* Understanding the drivers of employee attrition and implementing strategies to mitigate its impact is essential for organizations to maintain a stable and productive workforce.

## The HR Analytics process comprises several essential steps:

1. Data Collection: Gather pertinent HR data, including employee demographics, performance indicators, and turnover statistics.
2. Data Preparation: Clean, structure, and standardize collected data to ensure accuracy and uniformity.
3. Data Analysis: Employ advanced analytical methods to uncover patterns and trends within the data.
4. Insight Generation: Extract actionable insights and recommendations from the analysis.
5. Decision Making: Implement data-driven strategies to enhance workforce efficiency and accomplish organizational goals.

Data Reference : https://www.kaggle.com/datasets/pavansubhasht/ibm-hr-analytics-attrition-dataset

## Treating Imbalance Data

The dataset exhibits imbalance, with a bias favoring Retained Employees in a ratio of 5.2:1 compared to Attrited Employees. Common techniques for handling imbalanced data include:

* Resampling Techniques:
  1. Over-sampling: Increase minority class instances (Attrited Employees) using methods like SMOTE.
  2. Under-sampling: Decrease majority class instances (Retained Employees), with caution to avoid information loss.

* Algorithmic Techniques:
  1. Cost-sensitive learning: Penalize minority class misclassifications more.
  2. Algorithm-specific techniques: Adjust parameters to handle imbalance, such as setting 'balanced' class weights.

* Ensemble Methods:
  * Bagging and Boosting: Utilize methods like Random Forest or AdaBoost for improved performance on imbalanced data.

* Evaluation Metrics: Prioritize metrics like precision, recall, F1-score, or AUC-ROC over accuracy for imbalanced datasets.

* Data Preprocessing:
  1. Feature Engineering: Create features to aid class separation.
  2. Anomaly Detection: Identify outliers that may skew results.

## Resampling Techniques

### 1. Oversampling with SMOTE:

We apply SMOTE with a sampling_strategy of 0.85, aiming to increase the minority class (Class 1) to 85% of the majority class (Class 0).
* After oversampling:
  * Class 0 remains unchanged with 1233 samples.
  * Class 1 is increased through SMOTE to match 85% of Class 0: (0.85 x 1233) = 1048.05, approximately 1048 samples.
* Therefore, after oversampling:
  * Class 0: 1233 samples (unchanged)
  * Class 1: 1048 samples

### 2. Undersampling with RandomUnderSampler:

We employ RandomUnderSampler with sampling_strategy='auto', which automatically adjusts the undersampling strategy to balance the class distribution.
* After undersampling:
  * Both classes are reduced to have the same number of samples, equal to the number of samples in the minority class.
* Thus, after undersampling:
* Class 0: 1048 samples
* Class 1: 1048 samples

## Chi-squared Test
The Chi-squared (χ²) test is a statistical method employed to assess the presence of a meaningful connection between categorical variables. It proves valuable when investigating the correlation between two categorical variables within a given dataset.

A high Chi-squared score indicates substantial variance between the observed and anticipated frequencies, signaling a robust relationship between the analyzed variables. Conversely, a low Chi-squared score implies close resemblance between observed and expected frequencies, indicating minimal or negligible association between the variables under scrutiny.

We will drop the these features : Gender, BusinessTravel, EducationField, OverTime,Department, MaritalStatus,JobRole

<img src="https://raw.githubusercontent.com/gentallman/HR_Attrition_Analytics/main/assest/Chi-squared%20Test.png" width="500" >

## ANOVA Score Test
The ANOVA F-test is a common tool used to assess how strongly each feature is linked to the target variable in a classification job.

It's especially handy when you're dealing with a categorical target and numerical predictors. This test helps pick out numeric features that show big differences in their average values across various categories of the target. This ability makes it a great method for choosing relevant numeric features for classification tasks.

When you use the ANOVA F-test for feature selection, the ANOVA score shows the F-value for each feature. This value is the ratio of variance between groups to variance within groups.

A high ANOVA score means the feature has a strong connection with the target variable, suggesting it could be really useful for predicting the target.
We will drop the these features : YearsSinceLastPromotion, DailyRate, PercentSalaryHike, DistanceFromHome, NumCompaniesWorked, HourlyRate, MonthlyRate

<img src="https://raw.githubusercontent.com/gentallman/HR_Attrition_Analytics/main/assest/ANOVA%20Score%20Test.png" width="600" >

## Machine Learing Models

![image](https://github.com/gentallman/HR_Attrition_Analytics/assets/78334851/f8389b5a-1400-4d81-a4a4-14edf7b5209a)

## Key Findings
1. **Gender Disparity**: Males exhibit a higher attrition rate compared to females, hinting at potential disparities in job satisfaction, career opportunities, and workplace environment.

2. **Age Dynamics**: Attrition rates vary across different age groups, with individuals between 28-32 experiencing the highest attrition. This trend declines with advancing age, indicating a shift towards job stability and long-term commitments as individuals progress in their careers.

3. **Income Levels**: Attrition rates are influenced by income levels, with significant spikes observed at very low income levels and a gradual decrease as income rises. This underscores the importance of financial stability in employee retention.

4. **Job Satisfaction**:  Lower levels of job satisfaction correlate with higher attrition rates, particularly among employees with average monthly salaries of 4596. Conversely, higher satisfaction levels, especially among those earning 6853, contribute to employee retention.

5. **Departmental Differences**: The Sales department exhibits the highest attrition rate, followed by Human Resources, while Research and Development demonstrate lower rates. This suggests variations in work culture, opportunities, and satisfaction levels across departments.

6. **Job Role Impact**:  Higher-level job roles show lower attrition rates compared to lower-level roles, indicating the importance of career advancement opportunities and job stability in retaining talent.

7. **Salary Increment Influence**: Enhanced salary increments serve as a significant incentive for retention, motivating employees to perform better and remain committed to the organization.

8. **Educational Background**: Individuals with higher education levels, such as master's and doctorate degrees, demonstrate lower attrition rates, highlighting the value of specialized skills and advanced qualifications in job satisfaction and retention.

9. **Salary and Stock Options**:  Salary and stock options serve as significant motivators for employees, leading to higher loyalty and reduced attrition rates. Employees who receive higher pay and more stock options are more likely to remain committed to their organization, highlighting the importance of competitive compensation packages in retaining talent.

10. **Work-Life Balance**: Work-life balance emerges as a crucial factor influencing employee motivation and retention. While a good work-life balance is often considered a motivation factor, it can also lead employees to seek better opportunities and a higher standard of living elsewhere. Balancing work demands with personal life priorities is essential for maintaining employee satisfaction and reducing turnover.

Additional Observations:

- Single employees leave more than married or divorced ones.
- Around 10% leave after a 2-year anniversary.
- Loyal, higher-paid employees stay longer.
- Distance from work affects attrition.
- Frequent travelers and those with overtime have higher turnover.
- Sales representatives leave significantly.
- Past employment at multiple companies increases turnover likelihood.

## Here are few recommendations :

- Ensure equal opportunities for all genders, addressing potential disparities in job satisfaction and career advancement.
- Provide support and development opportunities for employees in their late twenties to early thirties to improve retention during this pivotal career phase.
- Adjust salary structures to offer competitive compensation, particularly for lower income levels, enhancing financial stability and reducing turnover.
- Prioritize initiatives to enhance job satisfaction, such as recognition programs and skill development opportunities.
- Assess and address factors contributing to higher attrition in departments like Sales and Human Resources, improving workload management and work culture.
- Provide clear career paths and skill development opportunities for lower-level roles to increase job stability.
- Review and optimize salary increment policies and offer competitive compensation packages, including stock options, to motivate loyalty.
- Implement policies promoting work-life balance, such as flexible work arrangements and wellness programs, to improve satisfaction and reduce turnover.
- Address specific factors such as support for single employees, workload management for anniversary dates, and challenges faced by employees who live far or travel frequently.

Implementing these strategies will help mitigate attrition rates and retain valuable talent, contributing to long-term organizational success.

## Contact

Author: Smit Rana

LinkedIn: https://www.linkedin.com/in/smit98rana/

<p align="center">
        <img src="https://raw.githubusercontent.com/mayhemantt/mayhemantt/Update/svg/Bottom.svg" alt="Github Stats" />
</p>

