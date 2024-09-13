# Isolation-forests-outlier-detection-test-on-monthly-IF-aggregated-data
Overview
This script performs outlier detection on investment funds data aggregated by various attributes such as instrument, country group, maturity, sector, etc. 

Description
The script follows these key steps:

Read Data: Loads the dataset from an Excel file.
Data Preparation:
Converts the DATA_TYPE column to a string. This is optional.
Creates a concatenated key column from several attributes.
Adds an iteration column to number the groups. This is optional.
Outlier Detection:
Applies Isolation Forest to detect outliers in the OBS_VALUE column for each group defined by the key.
Scores each observation and indicates whether it is an outlier based on a predefined threshold. Currently set as -0.7 but may be adjusted to any figure between -1 and 0. 
Handles cases where a group is too small to fit the model by assigning None and incomplete.
Output:
The final DataFrame is written to a new Excel file with additional columns: score, iteration, and outlier_indication.
Dependencies
pandas
openpyxl
scikit-learn
Usage
Install the necessary packages:
bash
Copy code
pip install pandas openpyxl scikit-learn
Update the file paths in the script as needed.
Run the script to process the data and generate the output Excel file.
Notes
Ensure that the input Excel file and output paths are correctly specified.
The script assumes that the dataset is structured with specific columns. Adjust the column names and logic as needed for different datasets.
