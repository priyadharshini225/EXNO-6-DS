# EXNO-6-DS-DATA VISUALIZATION USING SEABORN LIBRARY

# Aim:
  To Perform Data Visualization using seaborn python library for the given datas.

# EXPLANATION:
Data visualization is the graphical representation of information and data. By using visual elements like charts, graphs, and maps, data visualization tools provide an accessible way to see and understand trends, outliers, and patterns in data.

# Algorithm:
STEP 1:Include the necessary Library.

STEP 2:Read the given Data.

STEP 3:Apply data visualization techniques to identify the patterns of the data.

STEP 4:Apply the various data visualization tools wherever necessary.

STEP 5:Include Necessary parameters in each functions.

# Coding and Output:
```py
import pandas as pd
import matplotlib.pyplot as plt
import numpy as np
import seaborn as sns
```

```py
df = sns.load_dataset("tips")
df
```
<img width="553" height="503" alt="image" src="https://github.com/user-attachments/assets/fecfb0e3-b02b-4ec9-8589-7e831dd011dc" />

```py
sns.lineplot(x="total_bill",y="tip",data=df,hue="sex",linestyle="solid",legend="auto")
```
<img width="707" height="559" alt="image" src="https://github.com/user-attachments/assets/d94d276f-0573-49e7-8e13-b9fea3ff1508" />

```py
avg_total_bill = df.groupby('day')['total_bill'].mean()
avg_tip = df.groupby('day')['tip'].mean()
```

```py
plt.figure(figsize=(8, 6))
p1 = plt.bar(avg_total_bill.index, avg_total_bill, label='Total Bill')
p2 = plt.bar(avg_tip.index, avg_tip, bottom=avg_total_bill,label='Tip')
plt.xlabel("Day of the Week")
plt.ylabel("Amount")
plt.title("Average Tip and Total Bill by Day")
plt.legend()
```
<img width="684" height="570" alt="image" src="https://github.com/user-attachments/assets/9afc0773-448b-4e2d-ba16-181eecd8e105" />

```py
sns.barplot(x="day",y="total_bill",data=df,hue="sex",palette='Set2')
plt.xlabel("Day of the Week")
plt.ylabel("Total Bill")
plt.title("Total Bill by Day and Sex")
```
<img width="560" height="474" alt="image" src="https://github.com/user-attachments/assets/5b9ce835-1fa4-448d-8ae0-2295e4dd4cb0" />

```py
sns.scatterplot(x='total_bill',y='tip',hue='sex',data=df)
plt.xlabel("Total Bill")
plt.ylabel("Tip Amount")
plt.title("Scatter Plot of Total Bill vs Tip")
```
<img width="566" height="475" alt="image" src="https://github.com/user-attachments/assets/fe44b759-726a-4a3a-bf9d-ea89d1648209" />

```py
np.random.seed(0)
marks = np.random.normal(loc=70,scale=10,size=100)
marks
```
<img width="566" height="361" alt="image" src="https://github.com/user-attachments/assets/4b3ef6fd-4cc4-4f3e-9664-d64ad19eb83b" />

```py
sns.histplot(data=marks, bins=10, kde=True, stat='count', cumulative=False, multiple='stack', element='bars', color='blue', shrink=0.7)
plt.xlabel("Marks")
plt.ylabel("Density")
plt.title("Histogram of Students Marks")
```
<img width="580" height="470" alt="image" src="https://github.com/user-attachments/assets/43cfb286-2cb7-4b6a-9fc5-02621841c7e5" />

```py
sns.histplot(data=df, x="total_bill", hue="sex", bins=20, kde=True, palette="Set2")
```
<img width="580" height="446" alt="image" src="https://github.com/user-attachments/assets/8e80e9e6-ae4e-4870-ad13-50d999397ae0" />

```py
sns.boxplot(data=df, x="day", y="total_bill", hue="sex")
```
<img width="572" height="447" alt="image" src="https://github.com/user-attachments/assets/bbd4ae53-9aad-4240-8a78-53988a8cce58" />

```py
sns.boxplot(data=df, x="day", y="total_bill", hue="smoker", linewidth=3, width=0.7, boxprops={'facecolor': 'pink', 'edgecolor': 'red'}, whiskerprops={"color":"blue", "linestyle": "--", "linewidth": 1.6}, capprops={"color":"green", "linestyle": "--", "linewidth": 1.6}, medianprops={"color":"black","linewidth": 1.6}
            )
```
<img width="568" height="449" alt="image" src="https://github.com/user-attachments/assets/08d417d8-3bcb-400d-9acd-0909fa3198c4" />

```py
sns.violinplot(x="day", y="total_bill", hue="sex", data=df)

plt.title("Total Bill Distribution by Day and Gender")
plt.show()
```
<img width="560" height="455" alt="image" src="https://github.com/user-attachments/assets/fc5a5fad-f75e-48a4-aea4-236cf86604ce" />

```py
sns.violinplot(x="day", y="total_bill", hue="sex", data=df, split=True)

plt.title("Split Violin Plot of Total Bill by Day and Gender")
plt.show()
```
<img width="562" height="455" alt="image" src="https://github.com/user-attachments/assets/a73a4c80-c2e1-43e7-813d-430a51d371e6" />

```py
sns.violinplot(x="day", y="tip", data=df, inner="box")

plt.title("Tip Distribution by Day")
plt.show()
```
<img width="563" height="446" alt="image" src="https://github.com/user-attachments/assets/4891f9e1-8205-46ee-be7f-5a203c030e10" />

```py
sns.kdeplot(data=df, x="total_bill", y="tip", fill=True)
plt.title("2D KDE Plot of Total Bill vs Tip")
plt.show()
```
<img width="564" height="455" alt="image" src="https://github.com/user-attachments/assets/168ab41b-46c9-45a5-a131-d0fa6144896a" />

# Result:
Thus, all the data visualization techniques of seaborn has been implemented.
