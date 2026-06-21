# superstore-sales-dataset-cleaning

## The Question
Raw retail transaction data is rarely analysis-ready. This project takes the raw Superstore Sales dataset and prepares it for downstream analysis (dashboards, reporting, modeling) by fixing missing values, correcting data types, and standardizing formats.

## The Data
- **Source:** Superstore Sales Dataset (US retail orders — customer, product, and shipping details)
- **Size:** ~10K rows, 18 columns
- **Key fields:** Order Date, Ship Date, Customer, Segment, Region, Category, Sub-Category, Sales, Postal Code

## The Process
1. **Loaded the raw CSV** into a pandas DataFrame
2. **Handled missing values** — identified a missing postal code for a Burlington, Vermont record and filled it using the correct ZIP (5401) based on city/state
3. **Converted date columns** (`Order Date`, `Ship Date`) from string to proper `datetime` objects, handling the day/month/year format
4. **Standardized postal codes** — cast to integer, then zero-padded string format (5 digits) to preserve leading zeros
5. **Cleaned text fields** — stripped leading/trailing whitespace from every string column to prevent silent matching errors later (e.g. `"New York "` vs `"New York"`)
6. **Normalized column names** — converted to lowercase with underscores (`Order Date` → `order_date`) for easier, consistent coding downstream
7. **Verified the result** — confirmed zero remaining missing values and correct dtypes across all columns

## Key Insight
The dataset went from having inconsistent formatting and one missing geographic value to a fully clean, type-correct, analysis-ready table — with standardized text fields and machine-readable column names throughout.

## Tools
`Python` `Pandas` `Jupyter Notebook`
