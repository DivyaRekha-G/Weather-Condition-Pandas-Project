# Weather-Condition-Pandas-Project

 Project Overview

This project analyzes weather conditions using Python and Pandas. The dataset contains meteorological data, including temperature, humidity, wind speed, and visibility, recorded at different timestamps. The goal is to extract insights such as average weather conditions, patterns, and correlations between different parameters.

Dataset Description

The dataset consists of the following columns:

Column Name

Description

Date/Time

Timestamp of the recorded weather condition

Temp_C

Temperature in Celsius

Dew Point Temp_C

Dew point temperature in Celsius

Rel Hum_%

Relative humidity in percentage

Wind Speed_km/h

Wind speed in kilometers per hour

Visibility_km

Visibility in kilometers

Press_kPa

Atmospheric pressure in kilopascals

Weather Condition

General description of the weather (e.g., Fog, Rain, Clear)

🛠️ Technologies Used

Python 🐍

Pandas 📊

Jupyter Notebook / Google Colab 📒

📌 Key Explorations & Analysis

Summary statistics: Mean, median, max, min for each weather condition.

Data Grouping: data.groupby('Weather Condition').mean() to get average numerical values for each weather type.

Filtering data:

Find all instances when Weather is clear or Visibility is above 40.

Find all instances when Wind Speed is above 24 and Visibility is 25.

Find all instances when Snow was recorded.

Aggregation & Statistics:

Compute the Minimum & Maximum value of each column against each 'Weather Condition'.

Compute the Mean value of each column against each 'Weather Condition'.

Compute the Standard Deviation of Pressure.

Renaming Columns:

Rename the column name 'Weather' to 'Weather Condition'.

import pandas as pd

# Load the dataset
data = pd.read_csv("weather_data.csv")

# Display first few rows
data.head()

# Group by weather condition and compute mean values
data.groupby('Weather Condition').mean(numeric_only=True)

# Find instances where Weather is clear or Visibility is above 40
data[(data['Weather Condition'] == 'Clear') | (data['Visibility_km'] > 40)]

# Find instances when Wind Speed is above 24 and Visibility is 25
data[(data['Wind Speed_km/h'] > 24) & (data['Visibility_km'] == 25)]

# Find instances when Snow was recorded
data[data['Weather Condition'].str.contains('Snow', case=False, na=False)]

# Compute Standard Deviation of Pressure
data['Press_kPa'].std()

# Rename column 'Weather' to 'Weather Condition'
data.rename(columns={'Weather': 'Weather Condition'}, inplace=True)
📊 Results & Insights

Weather conditions impact temperature: Certain conditions like fog and rain show lower temperatures on average.

Wind speed affects visibility: Higher wind speeds correlate with better visibility.

Humidity and temperature relationship: Higher humidity is associated with lower temperatures.

🚀 How to Run This Project

Install dependencies: pip install pandas

Run the Jupyter Notebook or Python script.

Load the dataset using Pandas.

Execute the provided code snippets to analyze weather conditions.
