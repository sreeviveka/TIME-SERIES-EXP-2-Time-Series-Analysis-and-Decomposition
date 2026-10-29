# Ex-02: Time Series Analysis and Decomposition
## NAME : V S SREE VIVEKA
## REG NO : 2305001031
## DEPT : CSE
## Aim
To perform time series analysis and decomposition on the monthly average temperature of a city using Python.

## Objectives
- To create monthly temperature time-series data using Pandas.
- To visualize the temperature variations using Matplotlib.
- To decompose the time series into observed, trend, seasonal, and residual components using the `seasonal_decompose()` function.
- To understand the different components of additive time series decomposition.

## Program

```python
import pandas as pd
import matplotlib.pyplot as plt
from statsmodels.tsa.seasonal import seasonal_decompose

# Step 1: Create monthly temperature data
temperature = [
    25, 27, 29, 32, 34, 33,
    32, 31, 30, 29, 27, 25
]

# Step 2: Create date index
dates = pd.date_range(
    start="2025-01-01",
    periods=12,
    freq="ME"
)

# Step 3: Create time series
data = pd.Series(temperature, index=dates)

# Step 4: Display data
print("Monthly Temperature:")
print(data)

# Step 5: Plot original time series
plt.figure(figsize=(10, 5))
plt.plot(data.index, data.values, marker="o")
plt.title("Monthly Average Temperature")
plt.xlabel("Month")
plt.ylabel("Temperature (°C)")
plt.grid()
plt.show()

# Step 6: Decompose the time series
result = seasonal_decompose(
    data,
    model="additive",
    period=12
)

# Step 7: Display decomposition
result.plot()
plt.show()
```

## Output
<img width="335" height="317" alt="image" src="https://github.com/user-attachments/assets/38d6ef59-3ef7-47f7-9e8f-cac68a44457b" />
<img width="841" height="470" alt="image" src="https://github.com/user-attachments/assets/6bd3a227-129d-439a-8841-41f9521d7ec9" />
<img width="630" height="469" alt="image" src="https://github.com/user-attachments/assets/b0bfc626-2df7-40c1-80e7-5d8ba643bd21" />

## Result
The monthly temperature time series was successfully plotted and decomposed into observed, trend, seasonal, and residual components using Python.
