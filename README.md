Data Cleaning and Preparation - Chipotle Dataset

Overview

This Jupyter Notebook performs a comprehensive data cleaning and consistency check on the Chipotle dataset. It addresses missing values, data type inconsistencies, duplicated entries, and other potential issues that could affect analysis accuracy. This process ensures a well-prepared dataset for further analysis or model training.

Table of Contents

Load Dataset
Handle Missing Values
Verify Data Types
Remove Duplicates
Analyze Quantity and Item Price Columns
Examine Choice Descriptions
Remove Special Characters
Validate Order ID Integrity
Standardize Item Names
Calculate Total Price
Ensure Consistent Units
Optional: Save Cleaned Data to CSV

1.Load Dataset
Purpose: Loads the dataset using pandas. If the dataset is in TSV format, adjust the sep parameter to handle tab-separated values.
Code: Loads the data from an Excel or TSV file into a DataFrame for processing.

2. Handle Missing Values
Purpose: Checks for missing values in key columns and handles them by either removing rows, filling with specific values, or using interpolation where applicable.
Code:
Checks for missing values in each column.
Provides several options for handling missing values, including filling with default values or the mean/median.

3. Verify Data Types
Purpose: Ensures each column has the correct data type (e.g., integers for Quantity, floats for Item Price).
Code:
Uses astype() to enforce the correct data types and prints the DataFrame to confirm changes.

4. Remove Duplicates
Purpose: Identifies and removes duplicated rows to avoid redundancy in the dataset.
Code:
Uses duplicated() to check for duplicate entries and drop_duplicates() to remove them.

5. Analyze Quantity and Item Price Columns
Purpose: Checks for anomalies, such as negative or zero values in Quantity and Item Price.
Code:
Filters rows with problematic values in Quantity and Item Price columns for review.

6. Examine Choice Descriptions
Purpose: Reviews the Choice Description column for consistency, especially for multiple descriptions tied to a single item.
Code:
Prints value counts of Choice Description and checks for any inconsistencies or unusual patterns.

7. Remove Special Characters
Purpose: Cleans Item Name and Choice Description by removing special characters, ensuring consistent text formatting.
Code:
Uses str.replace() to strip special characters and str.strip() and str.lower() to standardize text.

8. Validate Order ID Integrity
Purpose: Confirms the uniqueness of Order ID to ensure that each order is distinct and correctly represented.
Code:
Checks for duplicate Order ID values and validates integrity.

9. Standardize Item Names
Purpose: Ensures that Item Name entries are standardized by converting them to lowercase and removing excess whitespace.
Code:
Uses str.strip() and str.lower() for text normalization.

10. Calculate Total Price
Purpose: Adds a Total Price column by multiplying Quantity and Item Price, then checks for inconsistencies in the calculated values.
Code:
Multiplies Quantity by Item Price to create Total Price.
Checks for rows where Total Price does not match the calculation, flagging potential anomalies.

11. Ensure Consistent Units
Purpose: Validates that units in Quantity and Item Price are consistent across the dataset, identifying any values that deviate from expectations.
Code:
Checks for unusual values in Quantity (e.g., negative values) and flags outliers in Item Price using a specified range.

12. Optional: Save Cleaned Data to CSV
Purpose: Saves the cleaned DataFrame to a CSV file for use in further analysis or model training.
Code:
Uses to_csv() to export the DataFrame to CSV format, allowing for easy access to the cleaned dataset.
