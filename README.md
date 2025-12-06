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

Why built-in datasets?
You can practice without collecting data
Clean and ready for plotting
Standard datasets used in ML + visualizations

1. Differnt Seaborn Plots are: 
🔹 A. Relational Plots

These show relationships between variables:

a. Scatter Plot
sns.scatterplot(data=df, x="total_bill", y="tip")
plt.show()

b.Line Plot
sns.lineplot(data=df, x="total_bill", y="tip")
plt.show()

c.relplot (Facet version)
sns.relplot(data=df, x="total_bill", y="tip", kind="scatter")
plt.show()

2.Categorical Plots:
Used for category-wise comparison.
* Barplot
sns.barplot(data=df, x="day", y="total_bill")
plt.show()

* Countplot
sns.countplot(data=df, x="day")
plt.show()

* Boxplot
sns.boxplot(data=df, x="day", y="total_bill")
plt.show()

* Violinplot
sns.violinplot(data=df, x="day", y="total_bill")
plt.show()

* Stripplot
sns.stripplot(data=df, x="day", y="total_bill")
plt.show()

* Swarmplot
sns.swarmplot(data=df, x="day", y="total_bill")
plt.show()

* Pointplot
sns.pointplot(data=df, x="day", y="total_bill")
plt.show()

* catplot (Wrapper)
sns.catplot(data=df, x="day", y="total_bill", kind="bar")
plt.show()

3. Distribution Plots:
* Histogram
sns.histplot(df["total_bill"], kde=True)
plt.show()

* KDE Plot
sns.kdeplot(df["total_bill"])
plt.show()

* ECDF Plot
sns.ecdfplot(df["total_bill"])
plt.show()

* Displot (Wrapper)
sns.displot(df["total_bill"], kde=True)

* Jointplot
sns.jointplot(data=df, x="total_bill", y="tip", kind="scatter")

* Pairplot
sns.pairplot(df[["total_bill","tip","size"]])

4. Regression Plots:
1. regplot
sns.regplot(data=df, x="total_bill", y="tip")
plt.show()

lmplot (Facet version)
sns.lmplot(data=df, x="total_bill", y="tip", col="sex")
plt.show()

*. Regression line explanation
A line shows the average trend
Useful for predicting relationships

*. CI (Confidence Interval)
Shaded band around regression line → shows uncertainty.

**. Matrix Plots **
. Heatmap
sns.heatmap(df.corr(), annot=True)
plt.show()

. Cluster Map
sns.clustermap(df.corr(), annot=True)
plt.show()

4. Styling in Seaborn
. Set Theme
sns.set_theme(style="darkgrid")

. Color Palettes
sns.color_palette("pastel")
sns.set_palette("husl")

. Figure Size
plt.figure(figsize=(8,5))

. Context Styles
sns.set_context("paper")
sns.set_context("talk")

5. Facet Grid / Multi-Plotting:
Used for plotting by category (rows/cols).

* FacetGrid Example
sns.FacetGrid(df, col="sex").map(sns.histplot, "total_bill")

* catplot
sns.catplot(data=df, x="day", y="total_bill", kind="box", col="sex")

* relplot
sns.relplot(data=df, x="total_bill", y="tip", col="sex")

* displot
sns.displot(df, x="total_bill", col="day")

## Combining Seaborn + Matplotlib ##
Seaborn returns a Matplotlib Axes object:
Example:
ax = sns.barplot(data=df, x="day", y="tip")
ax.set_title("Tips per Day")
ax.set_xlabel("Day")
ax.set_ylabel("Tip Amount")

You can use:
ax.set_title()
ax.set_xlabel()
ax.set_ylabel()
This allows mixing Matplotlib with Seaborn.
