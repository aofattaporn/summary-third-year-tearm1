### Mathplotlib 
###### *Line Chart*
```python 
import matplotlib.pyplot as plt
```

```python
		x = [-2, -1,  0, 1, 2]
		y = [ 3,  5, -1, 1, 2]
		z = [-4,  4,  2, 0, 3]
	
	# set plot and show graph about x and y
		plt.plot(x, y)
		plt.show() 
```


Show **grid** /  change marker type  /  and add some text
		
```python
		x = [-2, -1,  0, 1, 2]
		y = [ -3, -1, 1, 3, 0]
		z = [3, 2.5, -1, -2, 2]
		
		plt.plot(x, y)        
	
	# plot x and y using red circle markers  by *Add parameter*
		plt.plot(x, z, 'ro')  
		
	# set range of both axises
		plt.axis([-4, 4, -10, 10])
			
	# display some text on the chart
		plt.text(0, 0, r'Data', fontsize=20, fontstyle='italic')  
		
		plt.show()
```
> 	
>[!info] >
> ![[Screen Shot 2565-09-24 at 10.17.57.png | 400]]


```python
# change font size of all components in the plot and chart size to 12x8
	plt.rcParams.update({font.size:14})

# set size of image  
	plt.figure(figuresize=(5, 10))

# change label 
	plt.plot(df.average, label='average', color='red')
	plt.plot(df.actual,  label='actual',  color='green')
	plt.plot(df.forecast_noaa,  label='forecast_noaa')

	plt.title('Seattle Temperature', fontsize=20, color='darkblue')
	plt.xlabel('day', fontsize=16)
	plt.ylabel('fahrenheit',  fontsize=16)

# move the legend to upper left corner, and show grid
	plt.legend(loc = 'lower left')

# setting grid tables  
	plt.grid(True)

# shoe lagend of all with one command 
	plt.lagend(['sin(x)', 'cos(x)'], loc = "upper right")
	plt.show
```

---
###### *Pie Chart*
> เน้นการดู ความสัมพันธของข้อมูล ( relation ) โดยไม่อิงลำดับ 

```python 
# Data to plot
	names = 'Python', 'C++', 'Ruby', 'Java'
	vals  = [215, 130, 190, 210]
	colors = ['gold', 'yellowgreen', 'lightcoral', 'lightskyblue']
	shadows = [0.2, 0, 0, 0]

	plt.figure(figsize=(7,7))
	plt.pie(vals, labels=names, colors=colors)

# then set radius size=1.5,add shadow, explode some pieces out,
	plt.pie(vals, labels=names, colors=colors, 
	shadow=True, exprode=shadows, autopct='%1.1d%')

	plt.show()
```

![[Screen Shot 2565-09-24 at 22.17.09.png | 250]]

---

###### *Bar Chart*
> คล้ายๆกับ Line chart แต่นิยมในข้อมูลที่น้อยกว่า 

```python 
# creating the dataset
	data = {'C':20, 'C++':15, 'Java':30, 'Python':35}
	courses = list(data.keys())
	values = list(data.values())
	
	fig = plt.figure(figsize = (10, 5))

# creating the bar plot of the value for each course
	plt.bar(courses, values, color='green', width=0.5)

# setting a table
	plt.xlabel("Courses offered")
	plt.ylabel("No. of students enrolled")
	plt.title("Students enrolled in different courses")

# add labels on top of the bars
	for index,data in enumerate(values):
	    plt.text(x=index, y=data+0.5 , s=f"{data}")
	
	plt.show()

# horiszontal bar chart [ barh ]
	plt.barh(courses, values, color='red')
```
![[Screen Shot 2565-09-24 at 22.26.32.png | 400]]

---
0io
###### *Stack Bar Chart*
> การดูข้อมูลมากกว่า 1 อย่าง
```python 
# create data
	x = ['A', 'B', 'C', 'D']   # team
	y1 = np.array([10, 20, 10, 30])
	y2 = np.array([20, 25, 15, 25])
	y3 = np.array([12, 15, 19, 6])
 
# plot bars in stack manner
	plt.bar(x, y1, color='y')
	plt.bar(x, y2, bottom=y1, color='r')
	plt.bar(x, y3, bottom=y1+y2, color='b')

```

>![[Screen Shot 2565-09-24 at 22.32.43.png | 400]]

###### *Scatter Plot*
> ดูความสัมพันธ์ข้องตัวแปลสองตัว 

```python 
	plt.figure(figsize=(8, 6))
# plotting scartter plot 
	plt.scatter(x=df.actual, y=df.average, c='green')
	
	plt.title('Seattle Temperature')
	plt.xlabel('Actual (F)')
	plt.ylabel('Average (F)')
	plt.grid(True)
	
	plt.show()
```
###### *Box Plot*
> chart ที่ทำให้เห็นค่าทางสถิติ 
> 
```python
np.random.seed(123)      # set arbitrarily for reproducibility
d1 = np.random.normal(100, 10, 100)
d2 = np.random.normal(80, 20, 100)
d3 = np.random.normal(60, 30, 100)
d4 = np.random.normal(40, 40, 100)
 
plt.figure(figsize=(7, 5))
plt.boxplot([d1, d2, d3, d4], labels=['first', 'second', 'third', 'fourth'])
plt.show()
```
>![[Screen Shot 2565-09-24 at 22.43.23.png | 350]]

###### *Subplots Plot*
> ต้องการจะโชว์ทุก chart เพื่อนำมาเปรียบเทียบกัน 

```python 
plt.subplot(1, 2, 1)
plt.plot(x, x**2, 'o-')
plt.title('Left subplot')
plt.xlabel('X')
plt.ylabel('X^2')

plt.subplot(1, 2, 2)
plt.plot(x, 1/x, '.-')
plt.title('Right subplot')
plt.xlabel('X')
plt.ylabel('1/X')

# set the spacing between subplots
plt.subplots_adjust(left=0.05,   right=0.95, 
                    bottom=0, top=1, 
                    wspace=0.2, hspace=0.1)  # They are the fractions of the width and height of the figure.

plt.show()
```