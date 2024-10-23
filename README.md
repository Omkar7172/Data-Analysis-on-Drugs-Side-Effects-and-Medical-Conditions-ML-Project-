# Data-Analysis-on-Drugs-Side-Effects-and-Medical-Conditions-ML-Project-

1.Objective-
The goal is to analyze the relationships between drugs, their side effects, and the medical conditions they treat, as well as to explore the ratings and reviews associated with these drugs.

2. Dataset Overview-
The dataset contains the following columns:
● drug_name: Name of the drug.
● medical_condition: The condition the drug is used to treat.
● side_effects: Common side effects of the drug.
● generic_name: The generic name of the drug.
● drug_classes: The class of the drug (e.g., antibiotic, antihistamine).
● brand_names: Brand names under which the drug is sold.
● activity: The activity of the drug (e.g., active, inactive).
● rx_otc: Indicates if the drug is prescription (Rx) or over-the-counter (OTC).
● pregnancy_category: The drug's pregnancy risk category.
● csa: Controlled Substances Act schedule, if applicable.
● alcohol: Interactions with alcohol.
● related_drugs: Other drugs related to the primary drug.
● medical_condition_description: A brief description of the medical
condition.
● rating: Average user rating of the drug.
● no_of_reviews: Number of user reviews.
● drug_link: URL link to more information about the drug.
● medical_condition_url: URL link to more information about the medical
condition.

3. Tools Required-
● Python: The primary programming language for data analysis.
● Pandas: For data manipulation and analysis.
● Matplotlib/Seaborn: For data visualization.
● Jupyter Notebook: To write and run Python code.
4. Step-by-Step Guide-
Step 1: Import Libraries
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns
Step 2: Load the Dataset
Load your dataset
df = pd.read_csv('path_to_your_dataset.csv')
Display the first few rows of the dataset
df.head()
Step 3: Data Cleaning
● Check for missing values:
Check for missing values
df.isnull().sum()
● Handle missing values:
○ Drop or fill missing values depending on the context.
Example: Drop rows with missing values
df_cleaned = df.dropna()
 Or fill missing values with a placeholder
df_filled = df.fillna('Unknown')

Step 4: Basic Data Exploration
● Summary statistics:
 Summary statistics
df.describe()
● Distribution of Ratings:
 Distribution of drug ratings
plt.figure(figsize=(10, 6))
sns.histplot(df['rating'], bins=10, kde=True)
plt.title('Distribution of Drug Ratings')
plt.xlabel('Rating')
plt.ylabel('Frequency')
plt.show()

Step 5: Analyzing Relationships
● Top Drugs by Condition:
Count the most common drugs for each medical condition
top_drugs =
df.groupby('medical_condition')['drug_name'].value_counts().nla
rgest(10)
print(top_drugs)
● Side Effects Analysis:
Analyzing the most common side effects
side_effects = df['side_effects'].value_counts().head(10)
print(side_effects)
● Drug Ratings by Class:
Boxplot of ratings by drug class
plt.figure(figsize=(12, 8))
sns.boxplot(x='drug_classes', y='rating', data=df)
plt.xticks(rotation=90)
plt.title('Drug Ratings by Class')
plt.show()

Step 6: Conclusion
● Summarize findings:
○ Identify any trends or patterns in the data.
○ Discuss how certain drug classes or conditions are associated with
specific side effects or ratings.
5. Next Steps
● Advanced Analysis: Perform more sophisticated statistical tests or machine
learning techniques.
● Reporting: Create a report or presentation to share the findings.
6. Example Output
● Distribution of Drug Ratings:
○ A histogram showing how drug ratings are distributed, with peaks at
certain rating values.
● Top Drugs for a Condition:
○ A list or bar chart showing the most commonly prescribed drugs for a
particular condition.
● Side Effects Analysis:
○ A list of the most common side effects reported in the dataset.
