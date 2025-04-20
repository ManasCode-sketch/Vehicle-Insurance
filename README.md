# Vehicle Insurance Customer Response Analysis

## Project Overview

This project aims to explore and analyze a dataset containing information about potential vehicle insurance customers. The primary goal is to understand the factors influencing a customer's decision to purchase vehicle insurance (the 'Response' variable) and prepare the data for potential predictive modeling.

The analysis involves:
*   Initial data inspection and cleaning.
*   Descriptive statistical analysis.
*   Exploring correlations between numerical features.
*   Visualizing key distributions and relationships between relevant variables.

## Dataset

The analysis is performed on the `Vehicle_Insurance.csv` dataset. This dataset contains various attributes about individuals, such as gender, age, driving license status, region code, whether they were previously insured, vehicle information (age, damage status), annual premium, policy sales channel, customer vintage, and their response (whether they purchased the insurance or not).

*   **Source:** (Specify the source if it's from Kaggle, a specific competition, etc. If it's a private dataset, you might just say "Local CSV file" or similar.)
*   **Number of Entries:** 381,109
*   **Number of Features:** 11 (after removing 'id')

## Analysis Steps and Process

The analysis was conducted in a Jupyter Notebook (`insurance_analysis.ipynb` - adjust the filename if needed) and involved the following key steps:

1.  **Loading and Initial Inspection:**
    *   The dataset was loaded using pandas.
    *   The `.info()` method was used to check data types, non-null counts, and memory usage.
    *   The 'id' column was dropped as it is not relevant for the analysis.

2.  **Data Cleaning and Preprocessing:**
    *   Binary columns ('Response', 'Previously_Insured') represented as 0/1 were converted to more descriptive string values ('Yes'/'No' for Response, 'True'/'False' or 'Yes'/'No' for Previously_Insured) for better interpretability in visualizations and analysis.

3.  **Descriptive Statistics:**
    *   Descriptive statistics (`.describe()`) were generated for the numerical columns ('Age', 'Driving_License', 'Region_Code', 'Annual_Premium', 'Policy_Sales_Channel', 'Vintage').
    *   Insights regarding central tendency, dispersion, and range were extracted (e.g., average age, premium range, vintage distribution).
    *   Outliers in 'Annual_Premium' were specifically checked by filtering for values exceeding a certain threshold.

4.  **Correlation Analysis:**
    *   A correlation matrix was computed for the numerical features.
    *   A heatmap visualization was created using seaborn to show the strength and direction of linear relationships between these features.

5.  **Graphical Data Exploration (EDA):**
    *   Various plots were generated using matplotlib and seaborn to visualize distributions and relationships:
        *   **Response Distribution by Gender:** A bar plot showing the counts of 'Yes' and 'No' responses segmented by gender.
        *   **Annual Premium Distribution by Age:** A line plot illustrating how the average annual premium changes with age.
        *   **Distribution of Previously Insured Customers:** A pie chart showing the percentage breakdown of customers who were previously insured vs. those who were not.
        *   **Count of Vehicle Damage by Vehicle Age:** A bar plot comparing the counts of damaged ('Yes') and undamaged ('No') vehicles across different vehicle age categories.

## Key Findings

The initial analysis revealed several important insights:

*   **No Missing Data:** The dataset is complete, simplifying the data preparation process.
*   **Significant Class Imbalance:** The 'Response' variable is highly imbalanced, with a vast majority of customers (approx. 87.7%) not responding positively. This is a critical factor for model development.
*   **Previously Insured Status:** Customers who were previously insured are significantly less likely to respond to the current offer. This feature appears to have the strongest relationship with the target variable among the features explored.
*   **Age and Sales Channel:** There is a notable negative correlation between 'Age' and 'Policy_Sales_Channel', suggesting a relationship between customer age and the sales channel through which they were acquired.
*   **Weak Linear Correlations:** Most other numerical features show relatively weak linear correlations with the target variable and each other, although this doesn't preclude non-linear relationships.
*   **Premium Distribution:** Annual premiums have a wide range, indicating potential outliers or segments with very high premium vehicles.

## Technologies and Libraries Used

*   Python
*   Jupyter Notebook
*   pandas
*   numpy
*   matplotlib
*   seaborn

## How to Run

1.  Clone this repository:
    ```bash
    git clone <repository_url>
    ```
2.  Navigate to the project directory.
3.  Ensure you have the required libraries installed. You can install them using pip:
    ```bash
    pip install pandas numpy matplotlib seaborn
    ```
4.  Place the `Vehicle_Insurance.csv` file in the location expected by the notebook (e.g., in a `content` subdirectory or the same directory as the notebook).
5.  Open the Jupyter Notebook (`insurance_analysis.ipynb`) in a Jupyter environment (like JupyterLab or Google Colab) and run the cells.

## Future Work

*   Perform more in-depth univariate and bivariate analysis, especially for categorical features ('Gender', 'Region_Code', 'Vehicle_Age', 'Vehicle_Damage', 'Policy_Sales_Channel').
*   Address the class imbalance issue (e.g., using techniques like oversampling, undersampling, or choosing appropriate evaluation metrics).
*   Develop predictive models (e.g., Logistic Regression, Random Forest, Gradient Boosting) to predict customer response.
*   Evaluate model performance considering the class imbalance.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details. (Remember to add a LICENSE file to your repository).

---
