# Pandas_Pivot_Table_Example
This Python script demonstrates how to use a pivot table to calculate the count of occurrences for each team in each year from a given dataset. The dataset contains information about various teams, their ranks, years, and points.

## Sample Code

```python
import numpy as np
import pandas as pd

ipl_data = {
    'Team': ['Riders', 'Riders', 'Devils', 'Devils', 'Kings',
    'kings', 'Kings', 'Kings', 'Riders', 'Royals', 'Royals', 'Riders'],
    'Rank': [1, 2, 2, 3, 3, 4, 1, 1, 2, 4, 1, 2],
    'Year': [2014, 2015, 2014, 2015, 2014, 2015, 2016, 2017, 2016, 2014, 2015, 2017],
    'Points': [876, 789, 863, 673, 741, 812, 756, 788, 694, 701, 804, 690]
}
df = pd.DataFrame(ipl_data)

# Pandas_Pivot_Table_Example
pivot_table = df.pivot_table(df, index = 'Team', columns = 'Year', aggfunc = 'size', fill_value = 0)
print(pivot_table)
