# Jupyter Setup

I recommend having a "scratch.ipynb" file for each project. Add this to your *.gitignore* file, of course.

## First Cell

Example first cell for a Jupyter Notebook:

```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
import os

sns.set_style('whitegrid')
%matplotlib inline
%config InlineBackend.figure_formats = ['svg']
```

```python
# When using pandas, this might be helpful to see more data, if you like
from IPython.display import display

with pd.option_context('display.max_rows', 300, 'display.max_columns', 100):
    display(df.iloc[:300])
```