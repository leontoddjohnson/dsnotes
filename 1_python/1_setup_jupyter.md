# Jupyter Setup

I recommend having a "scratch.ipynb" file for each project. Add this to your *.gitignore* file, of course.

## JupyterLab Extensions

Most JupyterLab Extensions can be installed using the [JupyterLab Extension Manager](https://jupyterlab.readthedocs.io/en/latest/user/extensions.html#managing-extensions-using-the-extension-manager), but some of them require a `conda` or `pip` installation. Also, many will require you to [install Node](https://nodejs.org/en/download), so I recommend doing that first.

One particularly nice extension is the [Variable Inspector](https://github.com/lckr/jupyterlab-variableInspector). Though unfortunately, for this one, I've found that it only works when it is installed using pip: `pip install lckr-jupyterlab-variableinspector`.

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