# 🏠 Real Estate Price Prediction with Feature Engineering & ML

## Project Overview

This project focuses on predicting real estate prices using raw property data that initially lacked clear structure or meaningful trends. The original dataset showed little alignment or predictive value, making it difficult to extract insights directly.

### Data Exploration and Model Evolution

1. **Initial Model (Linear Regression)**:
   - The first approach involved using a simple **linear regression model** to predict real estate prices. However, this didn't perform well because the raw data didn't capture enough patterns, particularly with respect to categorical features like **zipcode**.

2. **Random Forest (Handling Categorical Data)**:
   - Next, a **random forest** model was applied to account for the categorical feature **zipcode**. Although random forests are better at handling such features, the performance was still subpar, showing that more preprocessing was needed.

3. **Log Transformations for Skewed Features**:
   - To address the **skewness** of certain numerical features, including **price**, **squarefeet**, and **lot size**, a **log transformation** was applied. This helped in normalizing the distribution of the data, which improved the model’s ability to learn patterns.
   - After applying these transformations, **ridge** and **lasso regression models** were trained using the newly created **log-transformed columns**. However, performance was still not optimal, especially when the **zipcode** feature was included.

4. **Group by Zipcode and Aggregation**:
   - To further refine the model, a **group-by operation** was performed on the **zipcode** feature, aggregating **price** by **zipcode**. This was done to capture regional price variations. Despite these efforts, the model performance remained lacking.

5. **New Feature Engineering (Price Per Square Foot & Lot Size)**:
   - The breakthrough came after introducing new features such as **price per square foot** and a **large lot indicator**. These features captured important relationships that were not apparent in the raw data.
   - After adding these features, the models were retrained, and the performance showed a significant improvement, with a **model performance of 0.98** (R² score), indicating a much better fit.

6. **Final Evaluation with Zipcode and Random Forest**:
   - Finally, a **random forest** model was retrained after excluding the **zipcode** feature, and the performance dramatically improved. This showed that, although the **zipcode** feature was important in segmenting prices, other factors like **price per square foot** and **lot size** played a bigger role in predicting prices accurately.

### Key Insights

- **Price per square foot** and **lot size** were identified as key features. With every **unit increase** in these features, the predicted price **increased**.
- **Zipcode** was found to be an important feature, but not the most significant predictor after feature engineering and transformations.
- By focusing on **feature engineering**, such as the creation of new variables and applying transformations, significant improvements in the model’s performance were achieved.

This project demonstrates the power of **thoughtful preprocessing**, **feature engineering**, and **model refinement** in turning noisy, unstructured data into a predictive asset for real-world applications like real estate valuation.

## Features

- Raw data preprocessing and feature extraction
- Log transformations to eliminate skewness
- Grouping by zipcode for regional price insights
- New feature creation: price per square foot and large lot indicator
- Application of multiple machine learning models: Linear Regression, Ridge, Lasso, Random Forest

## Technologies Used

- **Python**
- **Pandas**, **NumPy** for data manipulation
- **Scikit-learn**
- - **Matplotlib**, **Seaborn** for data visualization

## Installation

To set up this project on your local machine, follow these steps:

1. Clone the repository:
   ```bash
   git clone https://github.com/Gagandeep-1/-Real-Estate-Price-Prediction-with-Feature-Engineering-ML.git
