# Scatter Plot Visualization

## Features
- Scatter plot with:
  - **Customizable point sizes**.
  - **Color-coded points** using the `viridis` colormap.
  - **Categories** randomly assigned to data points.
- Axes labels, a plot title, and a color bar for better visualization.

## Requirements
- Python 3.x
- Libraries:
  - `numpy`
  - `pandas`
  - `matplotlib`
  - `seaborn`

## Installation
Install the required libraries using `pip`:

```bash
pip install numpy pandas matplotlib seaborn
```

## Code Overview

```python
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

x = [3.74, 9.50, 7.319, 5.98, 1.56, 1.55, 1.58, 8.66, 6.01, 7.08]
y = [16.23, 33.52, 26.95, 22.95, 9.68, 9.67, 6.74, 30.98, 23.035, 26.24]

size = len(x)

data = pd.DataFrame({
    'X': x,
    'Y': y,
    'Category': np.random.choice(['A', 'B', 'C'], size=size)
})

sizes = np.random.rand(size) * 100
colors = np.random.rand(size)

plt.figure(figsize=(8, 6))
plt.scatter(data['X'], data['Y'], s=sizes, c=colors, alpha=0.7, cmap='viridis')
plt.title("Scatter Plot with Color and Size")
plt.xlabel("X Values")
plt.ylabel("Y Values")
plt.colorbar(label="Color Scale")
plt.show()
```

