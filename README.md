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

<img src="https://user-images.githubusercontent.com/87891857/211190585-929bbf72-5132-4b3e-81e2-96d8d1f475f2.png" title="Optional title" width=50% height = 50%>
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
