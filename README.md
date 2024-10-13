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
To run the analysis, follow these steps:

1. Open the `analyzer.ipynb` Jupyter Notebook in your preferred environment. You can use Jupyter Notebook or JupyterLab for this purpose.

       jupyter notebook analyzer.ipynb

2. Load the dataset:
    ```python
    file_name='https://s3-api.us-geo.objectstorage.softlayer.net/cf-courses-data/CognitiveClass/DA0101EN/coursera/project/kc_house_data_NaN.csv'
    df = pd.read_csv(file_name)
    ```
3. Preprocess the data by handling missing values and dropping irrelevant columns.
4. Perform exploratory data analysis using visualizations such as boxplots and regression plots:
    ```python
    sns.boxplot(x='waterfront', y='price', data=df)
    sns.regplot(x='sqft_above', y='price', data=df)
    ```
5. Develop machine learning models using `LinearRegression` and `RidgeRegression` from `sklearn` to predict house prices based on features.
6. Evaluate the models using R² scores and polynomial transformations for better accuracy.

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

1. **Baseline Linear Model**:
    
    - **R² Score**: 0.49 – The simple linear regression model using `sqft_living` as the only predictor achieves an R² of approximately 0.49, indicating a moderate positive correlation between house size and price.

    ![R² Score: 0.49](https://github.com/jaiswalchitransh/Data-Analysis-of-House-Sales-in-King-County-USA/blob/main/Sample%20Output/Sample%20Output%207.png)

2. **Multiple Linear Regression**:

   - **R² Score**: 0.66 – Incorporating multiple features such as the number of bedrooms, bathrooms, grade, and waterfront views increases the R² value to 0.66, demonstrating a stronger predictive performance.

   ![R² Score: 0.65)](https://github.com/jaiswalchitransh/Data-Analysis-of-House-Sales-in-King-County-USA/blob/main/Sample%20Output/Sample%20Output%208.png)

3. **Polynomial Regression (2nd Degree)**:

   - **R² Score**: 0.75 – Best performance by capturing non-linear relationships.
  
   ![R² Score: 0.75)](https://github.com/jaiswalchitransh/Data-Analysis-of-House-Sales-in-King-County-USA/blob/main/Sample%20Output/Sample%20Output%2011.png)

4. **Polynomial Ridge Regression**:

   - **R² Score**: 0.70 (with polynomial features) – A polynomial transformation combined with Ridge regularization further improves the model’s R² to 0.70, suggesting that non-linear relationships between the variables enhance the prediction of housing prices.

    ![R² Score: 0.70](https://github.com/jaiswalchitransh/Data-Analysis-of-House-Sales-in-King-County-USA/blob/main/Sample%20Output/Sample%20Output%2014.png)

5. **Summary**:

   - **Best Model**: Polynomial Regression (R² = 0.75) for capturing both linear and non-linear patterns in house prices.
  
6. **Waterfront and House Prices**:

   - From the box plot analysis, it is clear that houses with waterfront views tend to have significantly higher prices, with some extreme outliers.

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

Thank you for exploring the Data Analysis of House Sales in King County, USA!
