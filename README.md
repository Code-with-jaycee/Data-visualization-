# Data-visualization-
Practicing data visualization with python
# Python Data visualization.

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
<h4><b>Example:</b> A simple pie chart</h4>

```
Languages = 'Python', 'C/C++', 'PHP', 'C#', 'Java', 'Other languages'
popularity = [29, 5.9, 6.2, 7.3,  19.1, 23.5]
colors = ['#1f77b4', '#ff7f0e', '#2ca02c', '#d62728' ,  '#9467bd', '#8c564b']
explode= [0.1, 0, 0, 0, 0, 0]
# wp=  {'linewidth': 0.5, 'edgecolor': 'green'}

# fig = plt.figure(figsize = (16, 7), dpi=600)
fig, ax = plt.subplots(figsize= (8, 7), dpi=600)
ax.pie(popularity,
        labels=Languages, 
        colors=colors, 
        shadow=True, 
        explode=explode, 
        autopct= "%1.1f%%")
ax.legend(languages,
        title = "Programming languages",
        loc = "upper left",
        bbox_to_anchor =(1, 0, 0.5, 1)
    )
ax.set_title("Popular programming language")
```

<h2>Output</h2>
<img src="https://user-images.githubusercontent.com/87891857/211190585-929bbf72-5132-4b3e-81e2-96d8d1f475f2.png" title="Optional title" width=50% height = 50%>
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
# 4. Adding a graph inside a graph
# 5. Graph parameters - title, label, legend
# 6. Line graphs - line types, color and transparency
# 7. Canvas grid and axis range
# 8. 2D plots - scatter, step, bar, fill_between
# 9. Radar chart, Histogram, Contour image
# 10 3D surface image
# 11 Practive example (pie chart)
