# Ex.No: 01A PLOT A TIME SERIES DATA
###  Date: 19/8/26

# AIM:
To Develop a python program to Plot a time series data (population/ market price of a commodity
/temperature.
# ALGORITHM:
1. Import the required packages like pandas and matplot
2. Read the dataset using the pandas
3. Calculate the mean for the respective column.
4. Plot the data according to need and can be altered monthly, or yearly.
5. Display the graph.
# PROGRAM:
```
import matplotlib.pyplot as plt
import pandas as pd

# Load dataset
df = pd.read_csv(r"/content/Month_Value_1.csv")

# Display first 5 rows
print(df.head())

# Convert Period column to datetime, specifying format for DD.MM.YYYY
df['Period'] = pd.to_datetime(df['Period'], format='%d.%m.%Y')

# Check data types
print(df.dtypes)

# Set Period as index
df.set_index('Period', inplace=True)

# Resample and interpolate using 'Revenue' column
df_resampled = df['Revenue'].resample('D').interpolate()

# Plot
df_resampled.plot(
    kind='line',
    label='Revenue',
    color='black'
)

plt.title('Time Series Plot of Revenue Each Day')
plt.xlabel('Day')
plt.ylabel('Revenue')
plt.legend()
plt.grid(True)
plt.show()
```










# OUTPUT:



<img width="804" height="877" alt="image" src="https://github.com/user-attachments/assets/61d0062c-d7f9-433a-87e9-c09a849c44af" />



# RESULT:
Thus we have created the python code for plotting the time series of given data.
