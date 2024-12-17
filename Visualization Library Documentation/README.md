# Visualization Library Documentation

This guide provides an overview of two popular Python visualization libraries, Matplotlib and Pandas. It explores the variety of graphs they can generate and includes practical examples with code snippets. The document also compares the strengths and weaknesses of these libraries to help users choose the right tool for their needs.

## Table of content
1. [Visualization Library](#visualization-library-documentation)
2. [Matplotlib](#matplotlib)
    1. [Introduction](#matplotlib)
    2. [Type's of Graph](#types-of-graph-offered-by-matplotlib)
3. [Pandas](#pandas)
    1. [Introduction](#pandas)
    2. [Type's of Graph](#types-of-graph-offered-by-pandas)
4. [Comparison](#comparison)

---------------------------

# 📊Matplotlib

Matplotlib is a Python library that allows users to create data visualizations, including static, animated, and interactive plot.

Matplotlib was created by John D. Hunter. It's open source and can be used freely. 

Matplotlib Library are available as wheel packages for macOS, Windows and Linux for python, we can install it using ```pip```<br>

```sh
pip install matplotlib
``` 
### pyplot


The library’s primary plotting tool is the ```pyplot``` module, It is a collection of functions that make matplotlib work like MATLAB.

Way to use MatPlotlib's pyplot module in Python 
```py
import matplotlib.pyplot as plt
```
### figure

The figure is the top-level container of all the axes and properties of a plot, or we can say that it is a canvas that holds the drawings (graphs or plots) on it. 

The ```pyplot``` module has a **figure()** function in it. We can create a new figure by using this function.

## Type's of Graph offered by Matplotlib

### 1. Line Graph
__Description__: A basic plot that connects data points with a line. <br>
**Use Case**: Visualizing trends over time.

__Code Snippet:__
```py
# line plot

# X axis parameter:
xaxis = np.array([2, 5, 8,])
# Y axis parameter:
yaxis = np.array([4, 6, 7])
plt.plot(xaxis, yaxis)
plt.xlabel('year after 201x')
plt.ylabel('sales in Cr.')
plt.show()
```
__Output:__

![line plot](Assets/Img/line%20chart.png)

### 2. Bar Chart
__Description__: Represents data using rectangular bars. <br>
**Use Case**: Comparing discrete categories.

__Code Snippet:__
```py
# bar chart

Shop = ['A', 'B', 'C', 'D']
values = [4, 7, 1, 8]

plt.bar(Shop, values, color='blue')
plt.title('Bar Chart')
plt.xlabel('Shop')
plt.ylabel('Sales in lakhs')
plt.show()
```
__Output:__

![bar chart](Assets/Img/bar%20chart.png)


### 3. Scatter Plot
__Description__: Displays data points as dots. <br>
**Use Case**: Identifying relationships or clusters in data.

__Code Snippet:__
```py
# scatter plot

x = [1, 2, 3, 4, 5]
y = [5, 3, 8, 1, 7]

plt.scatter(x, y, color='red')
plt.title('Scatter Plot')
plt.xlabel('X-axis')
plt.ylabel('Y-axis')
plt.show()
```
__Output:__

![scatter plot](Assets/Img/scatter%20plot.png)

### 4. Area Chart
__Description__: Displays quantitative data graphically by plotting data points and shading the area below the line. <br>
**Use Case**: Visualizing cumulative trends.

__Code Snippet:__
```py
# area Chart

x = [1, 2, 3, 4, 5]
y = [2, 3, 5, 7, 11]

plt.fill_between(x, y, color="skyblue", alpha=0.4)
plt.plot(x, y, color="Slateblue", alpha=0.7, linewidth=2)
plt.title('Area Plot')
plt.xlabel('X-axis')
plt.ylabel('Y-axis')
plt.show()
```

__Output:__

![area chart](Assets/Img/area%20chart.png)

### 5. Histogram
__Description__: Shows the distribution of a dataset. <br>
**Use Case**: Analyzing frequency distributions.

__Code Snippet:__
```py
# histogram 

data = [1, 2, 2, 3, 3, 3, 4, 4, 5]

plt.hist(data, bins=5, color='green', edgecolor='black')
plt.title('Histogram')
plt.xlabel('Value')
plt.ylabel('Frequency')
plt.show()
```

__Output:__

![histogram](Assets/Img/histogram.png)

### 6. Box Plot
__Description__: Displays the distribution of data based on a five-number summary. <br>
**Use Case**: Identifying outliers and understanding data spread.

__Code Snippet:__
```py
# box plot

data = [7, 8, 5, 6, 9, 10, 5, 6, 7]

plt.boxplot(data)
plt.title('Box Plot')
plt.ylabel('Values')
plt.show()
```
__Output:__

![box plot](Assets/Img/box%20plot.png)

### 7. Pie Chart
__Description__: Displays data as proportions of a whole. <br>
**Use Case**: Showing percentage contributions.

__Code Snippet:__

```py
# pie chart

labels = ['team A', 'team B', 'team C', 'team D']
values = [15, 30, 45, 10]

plt.pie(values, labels=labels, autopct='%1.0f%%', startangle=90)
plt.title('Team Performance Pie Chart')
plt.show()
```

__Output:__

![pie chart](Assets/Img/pie%20chart.png)

## 3D plots
### 1. 3D Bar Graph
__Description__: Displays data as 3D bars in a three-dimensional space. <br>
**Use Case**: Comparing categorical data in three dimensions.

__Code Snippet:__
```py
# 3d bar chart

fig = plt.figure()
ax = fig.add_subplot(111, projection='3d')
x = [1, 2, 3, 4, 5]
y = [2, 3, 4, 5, 6]
z = np.zeros(len(x))
dx = dy = 0.5
dz = [5, 10, 15, 20, 25]

ax.bar3d(x, y, z, dx, dy, dz, color='cyan', alpha=0.7)
ax.set_title('3D Bar Chart')
plt.show()
```

__Output:__

![3d bar chart](Assets/Img/3d%20bar%20chart.png)

### 2. 3D Scatter Graph 
__Description__: Displays data points in a three-dimensional space.<br>
**Use Case**: Visualizing spatial relationships in datasets.

__Code Snippet:__
```py
# 3D scatter plot 

fig = plt.figure()
ax = fig.add_subplot(111, projection='3d')

x = [1, 2, 3, 4, 5, 4, 6, 3, 7, 3, 5, 2, 9]
y = [5, 3, 8, 1, 7, 3, 6, 7, 4, 3, 6, 2, 6]
z = [2, 4, 6, 8, 10, 2, 6, 8, 3, 6, 2, 6, 8]

ax.scatter(x, y, z, color='red')
ax.set_title('3D Scatter Plot')
plt.show()
```

__Output:__

![3d scatter plot](Assets/Img/3d%20scatter%20plot.png)

### 3. Surface Graph
__Description__: Represents a 3D surface defined by a grid of data points. <br>
**Use Case**: Visualizing functions of two variables.

__Code Snippet:__
```py
# Surface plot

fig = plt.figure()
ax = fig.add_subplot(111, projection='3d')

x = np.linspace(-5, 5, 50)
y = np.linspace(-5, 5, 50)
x, y = np.meshgrid(x, y)
z = np.sin(np.sqrt(x**2 + y**2))

ax.plot_surface(x, y, z, cmap='viridis', edgecolor='none')
ax.set_title('Surface Plot')
plt.show()
```

__Output:__

![surface plot](Assets/Img/surface%20plot.png)

# 🐼Pandas

Pandas is primarily a data analysis library that includes built-in plotting functions for quick and easy visualizations. It utilizes Matplotlib under the hood.

Pandas library features simple syntax for quick plots directly from DataFrames and Series.

Ideal for exploratory data analysis (EDA).

Integrates seamlessly with Pandas data structures.

This library is best for data exploration, quick data analysis visualizations, and lightweight plotting without much customization.

Pandas library can be install in python using ```pip```
```sh
pip install pandas
```

## Type's of Graph offered by Pandas

### 1. Line Plot

**Description:**  Quickly generate a line plot directly from a Pandas DataFrame or Series.

**Use Case:** Plotting trends and time series data.

__Code Snippet:__
```py
import pandas as pd
import matplotlib.pyplot as plt

# Data
data = {'X': [1, 2, 3, 4, 5], 'Y': [2, 4, 6, 8, 10]}
df = pd.DataFrame(data)

# Create line plot
df.plot(x='X', y='Y', kind='line', title="Pandas Line Plot")

# here as pandas utilizes Matplotlib under the hood.
# plt.show() ensures that the graph is rendered perfectly.

plt.show()
```
__Output:__
![pd line plot](Assets/Img/pd%20line%20plot.png)

### 2. Bar Chart

**Description:** Create a bar chart from categorical data.

**Use Case:** Comparing values across categories.

__Code Snippet:__
```py
import pandas as pd
import matplotlib.pyplot as plt

# Data
data = {'Categories': ['A', 'B', 'C', 'D'], 'Values': [5, 7, 3, 8]}
df = pd.DataFrame(data)

# Create bar chart
df.plot(x='Categories', y='Values', kind='bar', title="Pandas Bar Chart")
plt.show()
```

__Output:__
![pd bar chart](Assets/Img/pd%20bar%20chart.png)

### 3. Histogram

**Description:** Generate histograms to visualize distributions.

**Use Case:** Exploring data distributions.

__Code Snippet:__
```py
import pandas as pd
import numpy as np

# Data
data = {'Values': np.random.randn(1000)}
df = pd.DataFrame(data)

# Create histogram
df['Values'].plot(kind='hist', bins=30, title="Pandas Histogram")
plt.show()
```
__Output:__
![pd line plot](Assets/Img/pd%20histogram.png)

## Comparison

### Matplotlib

MatPlotlib is Highly customizable which can use to create complex and detailed visualizations. 

It supports wide variety of graph with maximum customization options.

It is Flexible with multiple backends and extensions.

There are also some cons with matplotlib, as the learning curve of this library is much steeper for beginners. This library requires more line of code for simple plots. limited interactivity in default setup.

### Pandas

Whereas, pandas library is much simple and easy to learn and plot. it can do plotting directly from DataFrames and Series.

It is quick, which makes it an excellent choice for data exploration.

It uses Matplotlib under the hood, which allowing further customization to basic plots.

But not much customization options as comparied to matplotlib. It is less efficient for large and complex visualization. It has Fewer graph types available compared to Matplotlib.

## Conclusion

Matplotlib is ideal for creating detailed and highly customizable visualizations, suitable for presentations and reports.

Pandas is perfect for quick, simple visualizations during data exploration.

Both libraries complement each other, and Pandas can leverage Matplotlib's capabilities for further customization.

