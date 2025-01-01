# Basic Analytics

## Overview
This project is designed to analyze and process data sourced from a shared Google Spreadsheet. The dataset provides social media engagement metrics and other related information, which is used for filtering, transforming, and analyzing patterns in engagement across various platforms.

## Dataset
The dataset used in this project is hosted on Google Sheets and can be accessed through the following link:

[Google Sheets Dataset](https://docs.google.com/spreadsheets/d/1YhsgsN_WvYwDnhxpIcKqM-NXOfWrITm6Fc9h0agDKAI/edit?usp=sharing)

### Key Information:
- **Format**: Google Sheets (.xlsx or .csv can be downloaded as needed)
- **Data Fields**:
  - `Platform`: Name of the social media platform (e.g., Facebook, Instagram, Twitter, LinkedIn).
  - `Reach`: Total number of users reached.
  - `Likes`: Number of likes.
  - `Shares`: Number of shares.
  - `Comments`: Number of comments.
  - Other relevant engagement metrics.

## Features
1. **Data Ingestion**:
   - The Google Sheets link can be downloaded as a `.csv` or `.xlsx` file.
   - Pandas is used to read the dataset and load it into a DataFrame for further processing.

2. **Data Preprocessing**:
   - Columns such as `Platform`, `Reach`, `Likes`, `Shares`, and `Comments` are cleaned and validated.
   - Rows where engagement (`Likes + Shares + Comments`) exceeds `Reach` are filtered out.

3. **Data Analysis**:
   - Randomized columns such as `Home Reach`,`Hashtag_Reach` and `Explore Reach` are calculated based on the provided logic.
   - Filtered data is saved to a `.csv` file for further use.

## Prerequisites
### Libraries
Ensure the following Python libraries are installed:
```bash
pip install pandas numpy seaborn
```

### Tools
- Access to Google Sheets (for viewing or updating the dataset).
- Python environment for running the scripts.

## Usage Instructions

1. **Download the Dataset**:
   - Open the [Google Sheets Dataset](https://docs.google.com/spreadsheets/d/1YhsgsN_WvYwDnhxpIcKqM-NXOfWrITm6Fc9h0agDKAI/edit?usp=sharing).
   - Download the dataset as `.xlsx` or `.csv`.

2. **Load the Dataset**:
   - Place the file in the working directory.
   - Use the following script to load it:
     ```python
     import pandas as pd

     # Load the dataset
     df = pd.read_excel('dataset.xlsx')
     # or
     df = pd.read_csv('dataset.csv')
     ```

3. **Run Analysis**:
   - Apply transformations and analyze the data. Example:
     ```python
     # Filter rows where engagement exceeds reach
     df_filtered = df[df['Reach'] > (df['Likes'] + df['Shares'] + df['Comments'])]

     # Save to a new file
     df_filtered.to_csv('filtered_data.csv', index=False)
     ```

4. **Randomized Columns**:
   - Example to create `Home Reach`:
     ```python
     import numpy as np

     df['Home_Reach'] = df.apply(lambda row: np.random.randint(row['Reach'] // 2, row['Reach']), axis=1)
     ```

