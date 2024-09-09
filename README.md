### DEVELOPED BY: S JAIGANESH
### REGISTER NO: 212222240037
### DATE:

# Ex.No: 03   COMPUTE THE AUTO FUNCTION(ACF)

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

# Load the provided dataset
file_path = '/mnt/data/MLTempDataset.csv'
data = pd.read_csv(file_path)

# Extract the 'DAYTON_MW' column (data for analysis)
data_values = data['DAYTON_MW'].values

# Calculate mean and variance
mean_data = np.mean(data_values)
var_data = np.var(data_values)

# Normalize the data (subtract mean and divide by standard deviation)
normalized_data = (data_values - mean_data) / np.sqrt(var_data)

# Compute the ACF for the first 35 lags
lags = range(35)
acf_values = [np.corrcoef(normalized_data[:-lag], normalized_data[lag:])[0, 1] if lag != 0 else 1 for lag in lags]

# Plot the ACF results
plt.figure(figsize=(10, 6))
plt.stem(lags, acf_values, use_line_collection=True)
plt.title('Autocorrelation Function (ACF) for DAYTON_MW')
plt.xlabel('Lag')
plt.ylabel('ACF')
plt.grid(True)
plt.show()

```
<br>
<br>
<br>
<br>

### OUTPUT:
![image](https://github.com/user-attachments/assets/d9e50bcd-98e4-482c-95a8-45e7dbb3326d)



### RESULT:
 Thus, the python code for implementing the auto correlation function is executed successfully.  
