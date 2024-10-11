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
  - Dropped irrelevant columns (`id`, `Unnamed: 0`) and handled missing values in `bedrooms` and `bathrooms` by replacing them with the mean.

- **Exploratory Data Analysis (EDA)**:
  - Analyzed distribution of floors, waterfront price outliers, and correlation between house prices and square footage using visualizations (e.g., `value_counts()`, boxplots, and regression plots).

- **Linear Regression Models**:
  - **Simple Linear Regression**: 
    - Used `sqft_living` to predict house prices, achieving an R² of 0.49.
  - **Multiple Linear Regression**: 
    - Built a model with multiple features (e.g., floors, bedrooms), improving R² to 0.65.

- **Polynomial Regression**:
  - Implemented a second-order polynomial model, yielding a better R² of 0.75.

- **Model Evaluation**:
  - Performed train-test split (85%-15%) to assess model performance.
  - **Ridge Regression**:
    - Applied regularization, achieving an R² of 0.64, and improved to 0.70 with polynomial features.


## Results

1. **Simple Linear Regression**:
   - **R² Score**: 0.49 – Limited prediction power with only `sqft_living` as a feature.

2. **Multiple Linear Regression**:
   - **R² Score**: 0.65 – Improved accuracy by incorporating more features (`bedrooms`, `bathrooms`, etc.).

3. **Polynomial Regression (2nd Degree)**:
   - **R² Score**: 0.75 – Best performance by capturing non-linear relationships.

4. **Ridge Regression**:
   - **R² Score**: 0.70 (with polynomial features) – Reduced overfitting, with slight performance improvement.

5. **Summary**:
   - **Best Model**: Polynomial Regression (R² = 0.75) for capturing both linear and non-linear patterns in house prices.


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
