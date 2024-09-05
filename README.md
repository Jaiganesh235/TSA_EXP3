# Ex.No: 03   COMPUTE THE AUTO FUNCTION(ACF)
Date: 

### AIM:
To Compute the Auto Correlation Function (ACF) of the data for the first 35 lags to determine the model
type to fit the data.
### ALGORITHM:
1. Import the necessary packages
2. Find the mean, variance and then implement normalization for the data.
3. Implement the correlation using necessary logic and obtain the results
4. Store the results in an array
5. Represent the result in graphical representation as given below.
### PROGRAM:

```python
import matplotlib.pyplot as plt
import numpy as np
import pandas as pd

# Load the coffee sales data
file_path = '/mnt/data/coffee_Sales.csv'  # Replace with your file path
coffee_sales_data = pd.read_csv(file_path)

# Extract the 'money' column (sales data)
sales_data = coffee_sales_data['money'].values

# Calculate mean and variance
mean_sales = np.mean(sales_data)
var_sales = np.var(sales_data)

# Normalize the data (subtract mean and divide by standard deviation)
normalized_sales = (sales_data - mean_sales) / np.sqrt(var_sales)

# Compute the ACF for the first 35 lags
lags = range(35)
acf_values = [np.corrcoef(normalized_sales[:-lag], normalized_sales[lag:])[0, 1] if lag != 0 else 1 for lag in lags]

# Plot the ACF results
plt.figure(figsize=(10, 6))
plt.stem(lags, acf_values, use_line_collection=True)
plt.title('Autocorrelation Function (ACF) for Coffee Sales')
plt.xlabel('Lag')
plt.ylabel('ACF')
plt.grid(True)
plt.show()
```

### OUTPUT:

### RESULT:
 Thus, the python code for implementing the auto correlation function is executed successfully.  
