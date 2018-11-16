# Project-1
# Import modules
import pandas as pd

# Read colors data
colors = pd.read_csv('datasets/colors.csv')

# Print the first few rows
colors.head()
# How many distinct colors are available?
# -- YOUR CODE FOR TASK 3 --
num_colors = len(colors)
print(num_colors)

# colors_summary: Distribution of colors based on transparency
# -- YOUR CODE FOR TASK 4 --
colors_summary = colors.groupby('is_trans').count()
print(colors_summary)

%matplotlib inline
# Read sets data as `sets`
sets = pd.read_csv('datasets/sets.csv')
# Create a summary of average number of parts by year: `parts_by_year`
parts_by_year = sets.groupby('year')['num_parts'].mean()

# Plot trends in average number of parts by year
import matplotlib.pyplot as plt
plt.plot(parts_by_year)
plt.show()
