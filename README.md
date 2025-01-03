# EX-04 IMPLEMENTATION OF ADVANCED VISUALIZATIONS AND GEOSPATIAL DATA
**DATE :**
### Aim:
To Implement Advanced Visualizations and Geospatial Data using python.
### Algorithm:
Step 1: Include the necessary libraries<br>
Step 2: Add the necessary values to the initialized variables.<br>
Step 3: Install the advanced python necessary libraries such as pygal,plotnine,altair etc.<br>
Step 4: Use the necessary arguments for the functions used from advanced library.<br>
Step 5: Import Geopandas and folium.<br>
Step 6: Use folium map function to display the map location.<br>

### Program:

**Developed By: SANDHIYA R - 212222230129**
```Python
import numpy as np
import matplotlib.pyplot as plt
X=np.array([1,2,3,4,5,6,7,8,9,10])
Y=np.sin(X)
Z=np.cos(X)
plt.figure(figsize=(8,3))
plt.xlabel("Natural Numbers")
plt.ylabel("SIN and COS values")
plt.plot(X,Y,'yellow',marker='*',markersize=20,
    markeredgecolor='red',markerfacecolor='blue')
plt.plot(X,Z,'g',linewidth=5,linestyle='--')
plt.title("SIN and COS values")
plt.legend(["SIN","COS"])
plt.show()
```
![image](https://github.com/user-attachments/assets/8cedbb49-d0d1-4349-86bb-8d037663f9e2)

```Python
import pygal
from pygal.style import Style
custom=Style(background='transparent',
            plot_background='transparent',
            foreground='red',transition='400ms',
            foreground_strong='blue',
            foreground_subtle='yellow',
            opacity='.6',opacity_hover='.9',
            colors=('#E80080','#404040'))
chart=pygal.Line(style=custom,show_legend=True,
             x_title='Months',y_title='Values')
chart.title='Monthly Trends'
chart.add('Series 1',[1,4,5,9,8])
chart.add('Series 2',[2,3,7,6,10])
chart.render_to_file('output.svg')
```
![image](https://github.com/user-attachments/assets/2522fe91-9bc1-46d7-9fdc-1de4e73b20c0)

```Python
from bokeh.models import HoverTool 
from bokeh.plotting import figure, show 
from bokeh.io import output_notebook 
output_notebook() 
L=[1,2,3,4,5,6,7,8,9]
X=np.sin(L)
Y=np.cos(L)
p=figure(title="Scatter Plot with Hover Tool",
     x_axis_label='X-Axis',y_axis_label='Y-Axis') 
p.scatter(x=X,y=Y,size=10,color="blue",alpha=1.5) 
hover=HoverTool() 
hover.tooltips=[("X", "@x"), ("Y", "@y")] 
p.add_tools (hover) 
show(p)
```
![image](https://github.com/user-attachments/assets/5a053a74-5841-4786-ab0b-254247a3bc99)
```Pythonimport altair as alt 
import pandas as pd  
score_data = pd.DataFrame({ 'Name': ['A', 'B', 'C', 'D', 'E'], 
                           'Score': [65, 50, 99, 75, 33] }) 
alt.Chart(score_data).mark_bar().encode(x='Name',y='Score' )
```
![image](https://github.com/user-attachments/assets/e2382475-8905-480d-bbf1-fe82cabff1bc)
```Python
import altair as alt 
from vega_datasets import data
iris = data.iris() 
alt.Chart(iris).mark_point().encode(x='sepalLength',y='petalLength',shape='species')
```
![image](https://github.com/user-attachments/assets/19b3a959-caed-4c7c-b563-9693297afab9)

```Python
import altair as alt  
import pandas as pd 
data=pd.DataFrame([['A', 10, 20],['B', 5, 29],['A', 15, 29],['B', 15, 20]],
                  columns=['Team', 'Round 1', 'Round 2'])
print(data) 
chart=alt.Chart(data).mark_bar().encode(alt.Column('Round 2'),
 alt.X('Team'),alt.Y('Round 1',axis=alt.Axis(grid=False)),alt.Color('Team')) 
chart.display()
```
![image](https://github.com/user-attachments/assets/78832d94-a756-4739-8dbb-a0301054850c)
```Python
import geopandas as gpd 
import folium
import pandas as pd 
m=folium.Map(location=[10.9, 77.519],zoom_start=7,title="TAMILNADU") 
m.save('my_map.html')
m
```
![image](https://github.com/user-attachments/assets/09ec7f26-a2bb-4798-b9b1-baba78b8db93)

### Result:
Thus, theimplementation of Advanced Visualizations and Geospatial Data using python is successfully achieved.

