# Diwali Sales Data Analysis (Exploratory Data Analysis)

## Project overview
This project explores a Diwali sales dataset using Python. The notebook performs data inspection, basic data cleaning, descriptive statistics, grouped analysis, and visualizations to examine customer and sales patterns across demographic, geographic, occupation, and product dimensions.

## Dataset
- Input file: `Diwali Sales Data.csv`
- Original shape: 11,251 rows × 15 columns
- Columns removed: `Status` and `unnamed1` (both are completely empty)
- Missing values found in `Amount`: 12
- Rows remaining after dropping missing values: 11,239
- Final shape: 11,239 rows × 13 columns

## Tools and libraries
- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Jupyter Notebook

## Exploratory data analysis performed

### 1. Data loading and inspection
- Imported NumPy, Pandas, Matplotlib, and Seaborn.
- Loaded the CSV using Pandas with `unicode_escape` encoding.
- Checked the dataset dimensions with `shape`.
- Previewed records using `head()`.
- Inspected column names, non-null counts, and data types using `info()`.
- Used `describe()` to review descriptive statistics for numeric columns.

### 2. Data cleaning and preparation
- Removed the fully empty columns `Status` and `unnamed1`.
- Checked missing values with `isnull().sum()`.
- Found 12 missing values in `Amount` and removed those rows using `dropna()`.
- Converted `Amount` from floating-point to integer.
- Displayed the column names after cleaning.
- The notebook calls `rename()` for `Marital_Status`, but does not assign the result back to the DataFrame; therefore, the original column name remains unchanged in subsequent analysis.

### 3. Descriptive statistics
Used `describe()` on the cleaned dataset and specifically on `Age`, `Orders`, and `Amount` to inspect count, mean, standard deviation, minimum, quartiles, and maximum.

### 4. Gender analysis
- Created a count plot to compare the number of records for each gender.
- Grouped data by `Gender` and summed `Amount`.
- Visualized total amount by gender using a bar plot.

### 5. Age-group analysis
- Created a count plot of `Age Group`, split by `Gender`.
- Grouped data by `Age Group` and summed `Amount`.
- Visualized total amount by age group.

### 6. State analysis
- Grouped by `State` and summed `Orders`; selected the top 10 states.
- Grouped by `State` and summed `Amount`; selected the top 10 states.
- Created bar plots for both comparisons.

### 7. Marital-status analysis
- Created a count plot for the `Marital_Status` codes.
- Grouped by `Marital_Status` and `Gender`, summed `Amount`, and visualized the results with a gender hue.
- The notebook does not define what codes `0` and `1` mean, so they should be treated as codes rather than named marital categories.

### 8. Occupation analysis
- Created a count plot to compare records across occupations.
- Grouped by `Occupation` and summed `Amount`.
- Visualized total amount by occupation.

### 9. Product-category analysis
- Created a count plot to compare records across product categories.
- Grouped by `Product_Category` and summed `Amount`.
- Selected and visualized the top 10 categories by total amount.

### 10. Product-ID analysis
- Grouped by `Product_ID` and summed `Orders`.
- Selected the 10 product IDs with the highest summed order values.
- Visualized the top products using a Seaborn bar plot and a Pandas bar chart.

## Findings from the cleaned dataset

All values below are recalculated from the uploaded CSV after applying the cleaning steps in the notebook.

| Metric | Result |
|---|---:|
| Rows after cleaning | 11,239 |
| Unique `User_ID` values | 3,752 |
| Sum of `Orders` | 27,981 |
| Sum of `Amount` | ₹106,249,129 |

### Main observations
- **Gender:** Female records have a higher summed `Amount` (₹74,335,853) than male records (₹31,913,276).
- **Age group:** `26-35` has the highest summed `Amount` (₹42,613,442).
- **States:** Uttar Pradesh has the highest summed `Amount` (₹19,374,968) and the highest summed `Orders` (4,807). Maharashtra and Karnataka follow by amount.
- **Zone:** Central has the highest summed `Amount` (₹41,600,872).
- **Occupation:** IT Sector has the highest summed `Amount` (₹14,755,079), followed by Healthcare and Aviation.
- **Product category:** Food has the highest summed `Amount` (₹33,933,883). Clothing & Apparel has the highest summed `Orders` among categories (6,634).
- **Product ID:** `P00265242` has the highest summed `Orders` (127).

## Limitations of the notebook
- The analysis is descriptive and based on the columns available in this dataset.
- The notebook does not analyze sales by date or time.
- The notebook does not calculate profit, cost, profit margin, or return on investment.
- The notebook does not perform customer retention, cohort, or repeat-purchase analysis.
- `Orders` is summed as provided in the dataset; the sum should not automatically be interpreted as a count of distinct transactions.
- `Marital_Status` codes are not defined in the notebook.
- The notebook does not use SQL or Power BI.

## How to run
1. Place `Diwali_Sales_Analysis.ipynb` and `Diwali Sales Data.csv` in the same folder.
2. Install the required libraries:
   ```bash
   pip install numpy pandas matplotlib seaborn jupyter
   ```
3. Start Jupyter Notebook:
   ```bash
   jupyter notebook
   ```
4. Open `Diwali_Sales_Analysis.ipynb` and run the cells from top to bottom.

## Files
- `Diwali_Sales_Analysis.ipynb` — Jupyter Notebook containing the EDA.
- `Diwali Sales Data.csv` — source dataset.
- `README.md` — project documentation.
