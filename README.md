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
- Data wrangling to clean and prepare the dataset.
- Exploratory data analysis (EDA) for understanding patterns in house prices.
- Machine learning models for predicting house prices:
    - Linear Regression
    - Ridge Regression with polynomial features.
- Cross-validation for model evaluation.

## Results
The following results were obtained from the analysis:
- Linear Regression with `sqft_living` as a feature provided an R² score of 0.49.
- Linear Regression using multiple features gave an R² score of 0.65.
- Ridge Regression with second-order polynomial features provided the best model with an R² score of 0.70.

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
