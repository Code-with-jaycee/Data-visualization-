# Data-visualization-
Practicing data visualization with python
# Python Data visualization.
<h2>imports</h2>

```
from matplotlib import pylab
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
from mpl_toolkits.mplot3d.axes3d import Axes3D
from numpy.random import randint
```

# 1. What is matplotlib?
- this is an open source drawing library which supports rich drawing types
- It is used to draw 2D and 3D graphics
- You can understand your data easily by visualizing it with the help of matlotlib.
- You can generate plots, histograms, bar charts and many other charts with just a few lines of code.

# 2. Types of plots

<h4>Bar Chart</h4>
<h4>Scatter plot</h4>
<h2><strong>pie Chart</strong></h2>
<p>The size of the items (or "wedges") in one data series in a pie chart is proportional to the total number of those elements. Information in a pie chart is represented graphically as a fraction of the entire. The pie() method of the Matplotlib API produces a pie chart from an array of data.</p><br>



<img src="https://user-images.githubusercontent.com/87891857/211193300-a4d06cf7-191e-4efe-b63a-e8848bc0ecdc.png" title="Optional title" width=50% height = 50%>
<h5>When to use pie chart</h5>
<p>
To illustrate two main uses, consider the following:

- If it's more critical that your audience get the big picture of your data than the finer details of how the individual slices compare in size, then by all means use pie charts.

- To emphasize the size or smallness of a certain portion of the whole.


</p>

<h4><b>When is it acceptable to refuse pie?</b></h4>

1. <b>Comparing category sizes:</b> Pie charts fail rapidly if we want our audience to grasp our data beyond huge, little, or the same.
2. <b>Data comparison across pies</b> is challenging because the pie slices you want to compare are visually distinct and situated in various locations.
3. <b>Displaying data that doesn't add up to 100%:</b> if the slices don't add up to 100%, the data is incorrect. The pie must, by definition, represent a meaningful totality.

<h4><b>The technique of creating a beautiful pie chart</b></h4>

1. <b>Avoid things like 3D and explosions.</b>These additions aren't necessary and can skew the results.
2. <b>Don't use very many slices.</b>There isn't a hard and fast rule here, so think carefully about the needs of your dataset as well as audience.
3. <b>Organize your data in a useful way.</b>This takes into account the natural construct that we have of reading in a clockwise direction.
4. <b>Remove the legend and provide direct labels for the information.</b>A direct labeling system eliminates the need to constantly refer back and forth between the legend as well as the information being shown. As provided  there is enough room for the labels to be legible, you should always try to label your segments directly with the value.
<h4>Histogram</h4>
<h4>Line Chart</h4>
<h4>Area Graph</h4><br>

# 3. Plotting graphs and subgraphs

* Markers (points) can be drawn in a diagram with the aid of the plot() function. The plot() function automatically constructs a line connecting two points.

<h3>Plotting graph</h3>

```
# read a dataframe. Data available in the folder
data = pd.read_csv("Fifa_world_cup.csv")
data.head()

# dpi produce high quality images
fig = plt.figure(dpi=600)
x = data["total attempts team1"]
y = data["goal preventions team2"]


pylab.plot(x, y,color='red', lw=0.5, marker='o') 

```
# Output

<img src="https://user-images.githubusercontent.com/87891857/211196697-6e5547a3-f3e1-416c-ae8c-bde73c52dd1d.png" title="Optional title" width=50% height = 50%>

<h3>Drawing subgraphs</h3>

- A subgraph is a graph where all of the edges and vertices belong to a smaller graph.
```
# The contents of the brackets represent (rows, columns, indexes)

m = data["conceded team1"]
n = data["goal inside the penalty area team2"]
fig = plt.figure(dpi=600)
pylab.subplot(1, 2, 1)  # (1st row, 2nd column, index 1 )
pylab.plot(x, y,color='red', lw=0.25 ,marker="o", markerfacecolor='red' )

pylab.subplot(2, 2, 2)  # (2nd row , 2nd column, index 2)
pylab.plot(m, n, color='green', lw=0.25 ,marker="o", markerfacecolor='green')
```

# Output

<img src="https://user-images.githubusercontent.com/87891857/211197293-009c7f7b-0327-42ac-a108-6608227cb7d4.png" alt="subgraphs" title="Any title" width=50% height=50%>

# 4. Adding a graph inside a graph

```
fig = plt.figure(dpi=600)
axes1 = fig.add_axes([0.1, 0.1, 0.8, 0.8]) # left , right, width, height
axes2 = fig.add_axes([0.2, 0.5, 0.2, 0.3])

axes1.plot(x, y,color='red', lw=0.25 ,marker="o", markerfacecolor='red')

axes2.plot(m, n, color='green', lw=0.25 ,marker="o", markerfacecolor='green')
```
# Output
<img src="https://user-images.githubusercontent.com/87891857/211240499-98bddf1c-8e6a-45e4-8120-2294ea55fe96.png" alt="graph inside a graph" title="Any title" width=50% height = 50%>
# 5. Graph parameters - title, label, legend
# 6. Line graphs - line types, color and transparency
# 7. Canvas grid and axis range
# 8. 2D plots - scatter, step, bar, fill_between
# 9. Radar chart, Histogram, Contour image
# 10 3D surface image
# 11 Practive example (pie chart)

<h4><b>Example:</b> A simple pie chart</h4>

```
Languages = 'Python', 'C/C++', 'PHP', 'C#', 'Java', 'Other languages'
popularity = [29, 5.9, 6.2, 7.3,  19.1, 23.5]
colors = ['#1f77b4', '#ff7f0e', '#2ca02c', '#d62728' ,  '#9467bd', '#8c564b']
explode= [0.1, 0, 0, 0, 0, 0]
# wp=  {'linewidth': 0.5, 'edgecolor': 'green'}

fig, ax = plt.subplots(figsize= (8, 7), dpi=600)
ax.pie(popularity, labels=Languages,colors=colors,explode=explode, autopct= "%1.1f%%")

ax.set_title("Popular programming language")
```
# Output
<img src="https://user-images.githubusercontent.com/87891857/211193300-a4d06cf7-191e-4efe-b63a-e8848bc0ecdc.png" title="Optional title" width=50% height = 50%>