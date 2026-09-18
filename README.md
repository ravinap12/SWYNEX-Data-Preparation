# Housing Price Data Preparation

## Dataset
- **Source:** Kaggle (Housing Price Dataset)
- **Link:** https://www.kaggle.com/datasets/yasserh/housing-prices-dataset
- **Size:** 545 rows, 13 columns

## Objective
Prepare a public dataset for data-science work by cleaning missing values,handling data types, and documenting assumptions made during the process.

## Steps Taken

1. **Loaded the dataset** using pandas and inspected it with `df.info()` and `df.head()`.

2. **Checked data types** — found 6 numeric columns (Price, Area, Bedrooms,Bathrooms, Stories, Parking) and 7 categorical/text columns (Mainroad,Guestroom, Basement,Hotwaterheating, Airconditioning, Prefarea, 
   Furnishingstatus). All data types were already correct.

3. **Checked missing values** using `df.isnull().sum()` — no missing values were found in any column.

4. **Checked duplicate rows** using `df.duplicated().sum()` — no duplicate rows were found.

5. **Analyzed statistics** using `df.describe()` — found that Price and Area have high maximum values compared to their mean, indicating the presence of outliers (a few large/expensive properties).

6. **Converted categorical columns** (Mainroad, Guestroom, Basement, Hotwaterheating, Airconditioning, Prefarea, Furnishingstatus) to the `category` data type for better memory efficiency and clarity.

7. **Verified categorical values** using `.unique()` on each categorical column — confirmed all values were clean and consistent (e.g., only 'yes'/'no', no typos or inconsistent casing).

8. **Standardized text formatting** — capitalized the first letter of values in categorical columns (e.g., 'yes' → 'Yes') for consistency.

9. **Saved the cleaned dataset** as `cleaned_housing_data.csv`.

## Assumptions

- Since no missing values were present, no imputation (mean/median filling) was required. If missing values had been present, columns with skewed distribution (like    Price and Area) would have been filled using median, while more symmetric columns would have used mean.
- Outliers in Price and Area were **not removed**, as they were considered genuine data points representing large or expensive properties, rather than data entry errors.
- Categorical columns were assumed to have only the intended set of categories (yes/no, or furnished/semi-furnished/unfurnished) based on the `.unique()` check.

## Files in this Repository

- `Housing_Data_DS.ipynb` — Jupyter notebook with all cleaning steps and code
- `housing.csv` — Original dataset downloaded from Kaggle
- `cleaned_housing_data.csv` — Final cleaned dataset
- `README.md` — This file