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

<h2><strong>Bar Chart</strong></h2>
<b>When to use Bar Charts</b>

Bar graphs are useful for comparing data across categories or viewing trends over time. However, bar graphs excel at measuring change over time when the changes are significant.

# Example
<img src="https://user-images.githubusercontent.com/87891857/211253830-e8277ed8-59bb-4e1c-aff4-d38bddcb9ae5.png" alt="Bar chart" title="Optional title" width=50% height=50%>
<h4>Scatter plot</h4>

<b>When to use Scatter plot</b><br>
You can use a scatter plot to see how two variables are related to one another. Two variables that work well together can be plotted on a scatter diagram to examine their relationship and determine if it is positive or negative.

# Example
<img src="https://user-images.githubusercontent.com/87891857/211311370-30176bd4-b7e1-4ea2-9917-a3e6ea43a034.png" alt="Scatter plot" title="Optional title" width=50% height=50%>
<h2><strong>pie Chart</strong></h2>


<p>The size of the items (or "wedges") in one data series in a pie chart is proportional to the total number of those elements. Information in a pie chart is represented graphically as a fraction of the entire. The pie() method of the Matplotlib API produces a pie chart from an array of data.</p><br>


# Example
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

<b>When to use histogram</b>

One common type of graph is the histogram. It's a handy tool for summarizing interval-scaled data, whether those measurements are continuous or discontinuous. It's a useful way to show the key characteristics of the data's distribution.

# Example
<img src="https://user-images.githubusercontent.com/87891857/211313451-ba688e5e-0d93-459f-81c3-621de32bfb9e.png" alt="Histogram" title="Optional title" width=50% height=50%>
<h4>Line Chart</h4>
<b>When to use line graph</b><br>
Line graphs are useful for monitoring trends over both finite and infinite time frames. Line graphs are preferable to bar graphs when the differences are minimal. Changes over time for multiple groups can be compared using line graphs.

# Example
<img src="https://user-images.githubusercontent.com/87891857/211315647-c50b6472-0be4-40d1-91a1-435147bc541d.png" alt="Line chart" title="Optional title" width=50% height=50%>
<h4>Area Graph</h4><br>
<b>When to use Area graph</b><br>
Similarities between line graphs and area graphs are considerable. One or more groups' changes over time can be monitored with their help. When you need to monitor the evolution of a single category that consists of multiple subcategories, an area graph is the way to go (for example public and private groups).

# Example
<img src="https://user-images.githubusercontent.com/87891857/211316830-8aeccfe0-4374-4cee-87c1-6f958e187791.png" alt="Area graph" title="optional title" width=50% height=50%>

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

```
i = data["goal preventions team1"]
j = data["goal preventions team2"]

ax.legend(["Label1", "label2"])
fig, axes = plt.subplots(dpi= 600)
axes.set_xlabel('goal preventions team1') # x axis label
axes.set_ylabel('goal preventions team2') # y axis label
axes.set_title("Fifa World Cup") # Adding title


axes.plot(i, j, color='green', lw=0.25 ,marker="o", markerfacecolor='red')
axes.legend([ "team1 vs team2 goal preventions"])
```

# Output
<img src="https://user-images.githubusercontent.com/87891857/211242225-b4b7c2e2-fad8-45b8-9914-3350998eb9f7.png" alt="Graph parameters" title="Any title" width=50% height =50%>

# 6. Line graphs - line types, color and transparency

```
fig, axes = plt.subplots(dpi= 600)


axes.plot(x, y, 
        color='green', 
        alpha=.7, 
        lw=0.5,  # line width
        marker="o", 
        markerfacecolor="red")
```
# Output

<img src="https://user-images.githubusercontent.com/87891857/211243864-31190109-c220-4b23-b126-34fdaedc3e9a.png" alt="Line graph" title="Optional title" width= 50% height=50%>

# 7. Canvas grid and axis range

```
k  = np.linspace(1, 25, 25)
n = np.linspace(1, 20, 25)

fig, axes = plt.subplots(1, 2, dpi=400)

axes[0].plot(k, k**2, n, n**3, lw=2)
axes[0].grid(True)

axes[1].plot(k, k**2, n, n**3, lw=2)
axes[1].grid(True)
axes[1].set_ylim([0, 8000])
axes[1].set_xlim([5, 10])
```

# Output
<img src="https://user-images.githubusercontent.com/87891857/211248437-9869fca7-4c49-4f3b-b029-bef5bebb41ea.png" alt="Canvas grid" title="Optional title" width=50% height=50%>

# 8. 2D plots - scatter, step, bar, fill_between

```
k  = np.linspace(1, 25, 25)
fig , axes = plt.subplots(1, 4, figsize=(16, 5), dpi=600)
axes[0].set_title("scatter")
axes[0].scatter(k, k**2, color='red')
axes[1].set_title("step plot")
axes[1].step(k, k**3)

axes[2].set_title("bar plot")
axes[2].bar(k, k**4, width=0.8)

axes[3].set_title("fill_between")
axes[3].fill_between(k, k**4, color='green', alpha=0.5)
```

# Output

<img src="https://user-images.githubusercontent.com/87891857/211249408-4e1aa135-079a-4fde-a04c-3cf258f4f32d.png" alt="2D plot" title="Optional title" >

# 9. Radar chart, Histogram, Contour image

```
fig = plt.figure(figsize=(6, 6), dpi=400)
axes = fig.add_axes([0.0, 0.0, 6, 1], polar=True)

x = np.linspace(0, 2 * np.pi, 100)


axes.plot(x, x, color='red', lw=3)
```
# Output
<img src="https://user-images.githubusercontent.com/87891857/211250863-22487732-7d38-45b2-a74d-8f1c899d057e.png" alt="Rada chart" title="Optional Title" width=50% height=50%>

# 10 3D surface image

```
delta = 0.025
x = np.arange(-3.0, 3.0, delta)
y = np.arange(-2.0, 2.0, delta)

X, Y = np.meshgrid(x, y)
Z1 = np.exp(-X**2 - Y**2)
Z2 = np.exp(-(X-1)**2 - (Y - 1)** 2)
Z = (Z1 - Z2)* 2

fig = plt.figure(figsize=(14, 6), dpi=400)
# specify the 3D graphics to draw, with projection='3d'
ax = fig.add_subplot(1, 2, 1, projection='3d')
ax.plot_surface(X, Y, Z, rstride=7, cstride=4, linewidth=0, color="red")
```

# Output

<img src="https://user-images.githubusercontent.com/87891857/211252226-6af0fd44-dfbe-449b-a19b-2676bbec8d7e.png" alt="3D graph" title="Optional title" width=50% height=50%>

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