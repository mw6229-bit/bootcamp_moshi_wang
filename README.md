# Bootcamp Repository

## Folder Structure
- **homework/** → All homework contributions will be submitted here.
- **project/** → All project contributions will be submitted here.
- **class_materials/** → Local storage for class materials. Never pushed to GitHub.

## Homework Folder Rules
- Each homework will be in its own subfolder (`homework0`, `homework1`, etc.)
- Include all required files for grading.

## Class Materials Rules
- Each stage's handouts go in their own subfolder, named exactly as the course folder, e.g. `class_materials/stage01_problem-framing-and-scoping/`.
- Run lecture notebooks in place from that folder.
- Copy a homework starter into `homework/homeworkN/` before working on it.

## Project Folder Rules
- Keep project files organized and clearly named.
- The project folder structure is set up in Stage 02.


# VIX Spikes and Its Downside Risk on S&P 500 
**Stage:** Problem Framing & Scoping (Stage 01)

## Problem Statement
Will spikes in VIX elevate the downside risk of S&P500 in the next trading day? 
VIX represents the option market's expectation of future market volatility, and usually increases when market stress increases. When VIX elevates, there is a possibility that the equity market will decline, therefore, we are trying to find if the relationship between VIX spikes and S&P500 is strong enough to predict the outcome.

## Stakeholder & User
Investors, traders, and portfolio managers will be the main stakeholders and users.

## Useful Answer & Decision
The answer should be predictive, and should use next day's S&P500 return as the metric. A useful answer would indicate the downside risk of the equity market on the next trading day. If the downside risk of the S&P 500 increases after VIX spikes, investors may use this information to decide whether they should lower their equity exposure and strengthen risk management. The final analysis will include the results and visualizations comparing market performance after VIX spikes with normal trading days.

## Assumptions & Constraints
- We assume that historical S&P500 and VIX are accurate and complete.
- We assume that historical data are sufficient enough to decide whether VIX spikes provide predictive information
- We need to define a threshold for identify VIX spikes

- Factors affecting S&P 500 are more than just VIX, therefore the outcome of the next trading day cannot simply be attributed to VIX effects
- The relationship between VIX and the S&P 500 may change under different market conditions

## Known Unknowns / Risks
- We do not know what threshold should be used to define a VIX spike. We can test different thresholds and compare the results
- We do not know whether the downside risk of the S&P 500 is actually higher after VIX spikes. We will compare the next-day returns after VIX spikes with normal trading days
- The relationship between VIX spikes and S&P 500 returns may change over time. We can compare the results from different time periods

## Lifecycle Mapping
- Define the research problem → Problem Framing & Scoping (Stage 01) → Project scoping paragraph
- Identify the stakeholders → Problem Framing & Scoping (Stage 01) → Stakeholder context
- Define the project scope → Problem Framing & Scoping (Stage 01) → Analysis plan

## Repo Plan
- data/ → Store VIX and S&P500 data
- src/ → Store Python scripts and functions used in the analysis
- notebooks/ → Store Jupyter notebooks for data analysis and visualization
- docs/ → Store project documentation and stakeholder materials
- The repository will be updated after each stage of the project

## Data Storage
The project use `data/raw/` to store raw data and `data/processed/` to store processed data. Raw data is saved as CSV because it is easy to read and work with it. Processed data is saved as Parquet because it kept data types and would be more efficient for storing data.

The data paths are set in the `.env` file using:
- `DATA_DIR_RAW=data/raw`
- `DATA_DIR_PROCESSED=data/processed`

The code uses these environment variables to find where the data should be saved or loaded. The `write_df()` and `read_df()` functions check the file type and use the correct method for CSV or Parquet files.

## Data Cleaning Strategy
For Stage 06, the raw dataset is cleaned before further analysis. The cleaning process include dealing the missing values, removing rows with missing data when necessary, and normalizing numerical values.

Missing numerical values will be filled with the median because the median is less affected by extreme values. Rows with missing values can also be dropped depending on the amount of missing data. Numerical columns are normalized using min-max scaling so the values are between 0 and 1.

Cleaning functions are stored in `src/cleaning.py` so they can be reused. The cleaned dataset is saved in `data/processed/` while the original raw data remains unchanged.

## Assumptions and Reflection
The provided dataset did not contain any missing values, so the missing value function did not change the original data. I still tested the functions separately with a missing value to make sure they worked correctly.

I used median filling for numerical missing values because the median is less affected by extreme values. Rows with too much missing data can be dropped, although dropping rows may reduce the amount of available data.

I used Min-Max normalization for the `value` column. This changed the original values from a range of 10 to 30 into a range of 0 to 1. The relative differences between the values are preserved, but the original scale is no longer directly visible.

The `date` column was converted to datetime so it can be treated as a date instead of text. The original raw dataset was kept unchanged and the cleaned version was saved separately in `data/processed/`.