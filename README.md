# Ex.No: 05  IMPLEMENTATION OF TIME SERIES ANALYSIS AND DECOMPOSITION

## NAME : YUGABHARATHI T
## REG.NO : 212224040375
### Date: 13/05/2026


### AIM:
To Illustrates how to perform time series analysis and decomposition on the monthly average temperature of a city/country and for airline passengers.

### ALGORITHM:
1. Import the required packages like pandas and numpy
2. Read the data using the pandas
3. Perform the decomposition process for the required data.
4. Plot the data according to need, either seasonal_decomposition or trend plot.
5. Display the overall results.

### PROGRAM:
```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
from statsmodels.tsa.seasonal import seasonal_decompose

data = pd.read_csv('monthly-car-sales.csv',
                   parse_dates=['Month'],
                   index_col='Month')

print(data.head())

print(data.columns)

decomposition = seasonal_decompose(data['Sales'],
                                   model='additive',
                                   period=12)

plt.figure(figsize=(10, 12))

# Original Data
plt.subplot(411)
plt.plot(data['Sales'], label='Monthly Car Sales')
plt.legend(loc='upper left')
plt.title('Monthly Car Sales')

# Trend Plot
plt.subplot(412)
plt.plot(decomposition.trend,
         label='Trend',
         color='orange')
plt.legend(loc='upper left')
plt.title('Trend Plot')

# Seasonal Plot
plt.subplot(413)
plt.plot(decomposition.seasonal,
         label='Seasonality',
         color='green')
plt.legend(loc='upper left')
plt.title('Seasonality Plot')

# Residual Plot
plt.subplot(414)
plt.plot(decomposition.resid,
         label='Residual',
         color='red')
plt.legend(loc='upper left')
plt.title('Residual Plot')

plt.tight_layout()
plt.show()
```



### OUTPUT:
<img width="1297" height="572" alt="image" src="https://github.com/user-attachments/assets/ec1d4be8-6a87-418a-a12f-36f55a42d648" />

<img width="1257" height="731" alt="image" src="https://github.com/user-attachments/assets/cde39e97-10ef-475b-8f27-635016547e77" />

<img width="1240" height="378" alt="image" src="https://github.com/user-attachments/assets/0a9370c4-9851-4a28-921c-e2504056b670" />


### RESULT:
Thus we have created the python code for the time series analysis and decomposition.
