##### _Seaborn_
> `import seaborn as sns`

###### *Line Plots*
```python 
# Relation between total bill and tip
sns.lineplot(x='total_bill', y='tip', data=df)

# changing the size of plot, hue, style, and markers
plt.figure(figsize=(7, 5))
sns.lineplot(x='size', y='tip', data=df, hue='sex', style='sex', markers=True)
```

###### *Bar Plots*
```python 
# plot relation between tip and day
sns.barplot(x='day', y='tip', data=df)

# plot relation between tip and day group by smoker
sns.barplot(x='day', y='tip', data=df, hue='smoker', ci=False)

# count the number of smoker and non-smoker in each day
sns.catplot(x='day', data=df, hue='size', ci=False, kind='count')

# horizontal bar with color setting
sns.barplot(x='tip', y='day', data=df, hue='size', ci=False, orient='h', color='green')
```
###### *Pie Chart*
```python
# declare data
	data = [60, 22, 40, 41, 32]
	keys = ['Finance', 'Accounting', 'Psychology', 'Marketing', 'Laws']

# define Seaborn color palette to use
	palette_color = seaborn.color_palette('Set2')  # Set2, paster

# plotting data on chart
	plt.pie(data, labels=keys, colors=palette_color,
        explode=[0, 0, 0, 0, 0.3], autopct='%.0f%%')

# displaying chart
	plt.title('Students taking elective courses')
	plt.show()
```
###### Distribution plots
```python
# histogram with seaborn's displot()
	sns.displot(df['tip'], bins=20) 

# Kernel Density Estimate plot
	sns.displot(df['tip'], kind='kde')

# Kernel Density Estimate plot, with hue=smoker grouping
	sns.displot(df, x='tip', hue='smoker', kind='kde') # , fill=True)

# kde plot with stacking smoker grouping (like area chart)
	sns.displot(df, x='tip', hue='smoker', kind='kde', multiple='stack')

# Empirical Cumulative Distribution Function (ฟังก์ชันการกระจายสะสมค่าจากการทดลอง)
	sns.displot(df['tip'], kind='ecdf')

# Empirical Cumulative Distribution Function with smoker grouping
	sns.displot(df, x='tip', kind='ecdf', hue='sex')
```
###### *Box Plot 
```python
	
	sns.boxplot(x='size', y='tip', data=df)

# grouping with sex
	sns.boxplot(x='size', y='tip', data=df, hue='sex')
```



###### *Screatter Plot 
```python

# Relationship between total bill and tip
	sns.scatterplot(x='total_bill', y='tip', data=df, color='green')

# total bill and tip with sex
	sns.scatterplot(x='total_bill', y='tip', data=df, hue='sex', 
	style='smoker')

# total bill and tip with scatter size
	plt.figure(figsize=(10,6))
	sns.scatterplot(x='total_bill', y='tip', data=df, hue='sex', style='sex', 
	                size='tip', sizes=(50, 200))
	                
```


###### *Heat map*
```python

corr = car_crashes.corr()

plt.figure(figsize=(12, 6))

sns.heatmap(corr, annot=True, linewidths=1, cmap='coolwarm')
	                
```

###### Pairplots
```python

sns.pairplot(df)

sns.pairplot(df[['total_bill', 'tip']])   # running on specific columns
	                
```
