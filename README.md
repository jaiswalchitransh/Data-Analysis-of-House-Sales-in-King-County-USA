# Data Analysis of House Sales in King County, USA

## Table of Contents
- [Project Overview](#project-overview)
- [Installation](#installation)
- [Usage](#usage)
- [Features](#features)
- [Results](#results)
- [Contribution](#contribution)

## Project Overview
This project focuses on analyzing house sales data in King County, which includes Seattle, USA. The dataset contains home sale prices and related attributes for houses sold between May 2014 and May 2015. The analysis explores various relationships between housing features and sale prices, such as square footage, number of bedrooms and bathrooms, waterfront views, and more.

The project involves:
- Data preprocessing and handling missing values.
- Exploratory data analysis (EDA) including visualizations and statistical summaries.
- Development and evaluation of machine learning models like Linear Regression and Ridge Regression.
- Use of polynomial transformations for improved model accuracy.

## Installation
This project requires Python 3.12.1 or later.
To set up the project:
1. Ensure Python 3.12.1 or a later version is installed on your system. You can download Python from [python.org](https://www.python.org/downloads/).
2. Clone or download the repository to your local machine.
    
       git clone https://github.com/jaiswalchitransh/Data-Analysis-of-House-Sales-in-King-County-USA.git
  
3. Install the necessary Python packages:
   
   Required packages:
   - `pandas`
   - `numpy`
   - `matplotlib`
   - `seaborn`
   - `scikit-learn`
  
         pip install pandas numpy matplotlib seaborn scikit-learn
     

4. Open the project in Jupyter Notebook or any Python IDE.
5. Run the script in your Python environment.

## Usage
1. Load the dataset:
    ```python
    file_name='https://s3-api.us-geo.objectstorage.softlayer.net/cf-courses-data/CognitiveClass/DA0101EN/coursera/project/kc_house_data_NaN.csv'
    df = pd.read_csv(file_name)
    ```
2. Preprocess the data by handling missing values and dropping irrelevant columns.
3. Perform exploratory data analysis using visualizations such as boxplots and regression plots:
    ```python
    sns.boxplot(x='waterfront', y='price', data=df)
    sns.regplot(x='sqft_above', y='price', data=df)
    ```
4. Develop machine learning models using `LinearRegression` and `RidgeRegression` from `sklearn` to predict house prices based on features.
5. Evaluate the models using R² scores and polynomial transformations for better accuracy.

## Features

- **Data Preprocessing**:
    - The dataset contains house sale records in King County, USA, from May 2014 to May 2015.
    - Columns like `id` and `Unnamed: 0` were dropped as they don't add value to the analysis.
    - Missing values in the `bedrooms` and `bathrooms` columns were identified and replaced with the mean of those columns to ensure completeness of the dataset.

- **Exploratory Data Analysis (EDA)**:
    - **Floor Analysis**: A `value_counts()` analysis was done to display how many houses had different numbers of floors, giving insight into the distribution of house types by floor count.
    - **Waterfront & Price Outliers**: A boxplot was generated to show the relationship between waterfront views and house prices, revealing that waterfront houses generally have higher prices and more price outliers.
    - **Price vs. Square Footage**: A regression plot was created using `sqft_above` (above-ground living space) to determine its relationship with house prices, showing a positive correlation.

- **Linear Regression Models**:
    - **Simple Linear Regression**:
        - Two simple linear regression models were created:
            1. Using **longitude** as a feature to predict house prices, which yielded a low R² value (0.00047), indicating it’s not a strong predictor.
            2. Using **sqft_living** (total living area), which resulted in an R² value of 0.49, suggesting that more living space is a better predictor of price than location.
    - **Multiple Linear Regression**:
        - A more complex model was created using multiple features (e.g., **floors**, **waterfront**, **bedrooms**, etc.), which improved the R² to 0.65, indicating a better fit for predicting house prices.

- **Polynomial Regression**:
    - A pipeline was built using `PolynomialFeatures` to create a second-order polynomial regression model. The model performed better with an R² of 0.75, indicating that adding polynomial features (non-linear interactions between features) improves the prediction of house prices.

- **Model Evaluation & Refinement**:
    - **Train-Test Split**: The data was split into training (85%) and testing (15%) sets to evaluate the model’s performance on unseen data.
    - **Ridge Regression**:
        - Ridge regression (a form of regularized linear regression) was used to handle overfitting. This model performed well with the test data, yielding an R² of 0.64.
        - When combined with second-order polynomial features, the R² increased to 0.70, demonstrating an even better model for predicting house prices while controlling overfitting.


## Results

1. **Simple Linear Regression**:
   - **Model**: Used `sqft_living` as the single feature.
   - **Performance**: 
     - **R² Score**: 0.49 (indicating that about 49% of the variance in house prices is explained by square footage).
   - **Interpretation**: While `sqft_living` has a significant relationship with price, it alone isn't enough to predict prices accurately.

2. **Multiple Linear Regression**:
   - **Model**: Incorporated additional features (e.g., `bedrooms`, `bathrooms`, `floors`, `condition`, `waterfront`).
   - **Performance**:
     - **R² Score**: 0.65, showing improvement over the simple linear model.
   - **Interpretation**: Including more features provides a better prediction, though some variance is still unexplained, indicating that other factors influence house prices.

3. **Polynomial Regression (2nd Degree)**:
   - **Model**: Extended the linear model to include polynomial terms, allowing for non-linear relationships between features and prices.
   - **Performance**:
     - **R² Score**: 0.75, significantly higher than previous models.
   - **Interpretation**: Capturing non-linear relationships between features and house prices greatly improves the model's predictive power.

4. **Ridge Regression**:
   - **Model**: Applied Ridge regularization to the multiple linear regression model to reduce overfitting.
   - **Performance**:
     - **R² Score**: 0.64 (for the regular model) and **R² = 0.70** when polynomial features are used.
   - **Interpretation**: Ridge regularization helps to balance model complexity and generalization, providing a slight performance boost with polynomial features.

5. **Overall Model Comparison**:
   - **Best Model**: Polynomial Regression (2nd Degree) outperforms all other models, with an R² of 0.75.
   - **Takeaway**: The model captures more complexity in the relationships between house prices and the chosen features, showing that both linear and non-linear interactions play a role in accurate price prediction.


## Contribution
I, **[Chitransh Jaiswal](https://www.linkedin.com/in/jaiswalchitransh/)** developed this Project Individually. I was responsible for all aspects of the project, including design, development, testing, and documentation.
Contributions to improve the efficiency, readability, or functionality of the code are welcome. To contribute:
1. Fork the repository.
2. Create a new branch (`git checkout -b feature/your-feature`).
3. Make your changes.
4. Commit your changes (`git commit -am 'Add some feature'`).
5. Push to the branch (`git push origin feature/your-feature`).
6. Create a new Pull Request.

Please ensure your contributions adhere to the coding standards and follow the existing style and structure.

---

Thank you for exploring the Historical Stock and Revenue Data Analysis!
