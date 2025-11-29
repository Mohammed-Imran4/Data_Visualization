# Data_Visualization
About the basic functions of the Seaborn and differnt plots:

What is Seaborn?
Seaborn is a statistical data visualization library built on top of Matplotlib.

Why Seaborn?
Prettier visuals
Built-in themes
Works well with Pandas
Fewer lines of code
Best for statistical plots

Import:
import seaborn as sns
import matplotlib.pyplot as plt

a.Loading Sample Datasets
Seaborn provides many built-in datasets for learning.

b.List all datasets
sns.get_dataset_names()

c.Load dataset
df = sns.load_dataset("tips")
df.head()
this will show the starting 5 dataset of the "tips" dataset
