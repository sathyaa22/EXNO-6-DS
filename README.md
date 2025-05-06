# EXNO-6-DS-DATA VISUALIZATION USING SEABORN LIBRARY

## NAME: SATHYAA R
## REG NO: 212223100052

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

```
import seaborn as sns
import matplotlib.pyplot as plt
import pandas as pd
import numpy as np
```
```
x = [1, 2, 3, 4, 5]
y = [3, 6, 2, 7, 1]
```
```
sns.lineplot(x=x,y=y)
```

![image](https://github.com/user-attachments/assets/64a15fcb-e5c0-48d0-94a0-8c5f965d77f3)

```
df = sns.load_dataset("tips")
df
```

![image](https://github.com/user-attachments/assets/96e260a1-4cce-4e67-b2f9-1da301376438)

```
sns.lineplot(x="total_bill",y="tip", data=df, hue="sex", linestyle='solid', legend="auto")
```

![image](https://github.com/user-attachments/assets/391204df-c65e-47a9-8e83-dec13a3af06c)

```
x=[1, 2, 3, 4, 5]
y1=[3, 5, 2, 6, 1]
y2=[1, 6, 4, 3, 8]
y3=[5, 2, 7, 1, 4]
```
```
sns.lineplot(x=x, y=y1)
sns.lineplot(x=x, y=y2)
sns.lineplot(x=x, y=y3)
plt.title("Multi-Line Plot")
plt.xlabel('X Label')
plt.ylabel("Y Label")
```

![image](https://github.com/user-attachments/assets/4f0eeab1-3ada-4f78-8ee6-c4801b292c83)

```
tips=sns.load_dataset('tips')
avg_total_bill = tips.groupby('day')['total_bill'].mean()
avg_tip = tips.groupby('day')['tip'].mean()
plt.figure(figsize=(8, 6))
p1 = plt.bar(avg_total_bill.index, avg_total_bill, label='Total Bill')
p2 = plt.bar(avg_tip.index, avg_tip, bottom=avg_total_bill, label='Tip')
plt.xlabel('Day of the Week')
plt.ylabel('Amount')
plt.title('Average Total Bill and Tip by Day')
plt.legend()
```

![image](https://github.com/user-attachments/assets/a8d17215-749d-4d22-b0e3-9af9bf111f29)

```
avg_total_bill = tips.groupby('time')['total_bill'].mean()
avg_tip=tips.groupby('time') ['tip'].mean()
p1= plt.bar(avg_total_bill.index, avg_total_bill, label='Total Bill', width=0.4)
p2 = plt.bar(avg_tip.index,avg_tip,bottom=avg_total_bill,label='Tip', width=0.4)
```

![image](https://github.com/user-attachments/assets/f00734e4-2e01-4116-af64-7ae4375d893a)

```
years=range(2000, 2012)
apples=[0.895, 0.91, 0.919, 0.926, 0.929, 0.931, 0.934, 0.936, 0.937, 0.9375, 0.9372, 0.939]
oranges = [0.962, 0.941, 0.930, 0.923, 0.918, 0.908, 0.907, 0.904, 0.901, 0.898, 0.9, 0.896, ]
```
```
plt.bar(years, apples)
plt.bar(years, oranges, bottom=apples)
```

![image](https://github.com/user-attachments/assets/f96bfbe0-9e90-48f7-be9e-3f86e9d52a6a)

```
import seaborn as sns
dt= sns.load_dataset('tips')
sns.barplot(x='day', y='total_bill', hue='sex', data=dt, palette='Set1')
plt.xlabel('Day of the Week')
plt.ylabel("Total Bill")
plt.title('Total Bill by Day and Gender')
```

![image](https://github.com/user-attachments/assets/9fbec310-cd4a-40d7-a7ff-c6285f745f94)

```
tit=pd.read_csv("titanic_dataset.csv")
tit
```

![image](https://github.com/user-attachments/assets/e4540439-6a42-4ce1-8364-b4c38a5f5661)

```
plt.figure(figsize=(8,5))
sns.barplot(x='Embarked', y='Fare', data=tit, palette='rainbow')
plt.title("Fare of Passenger by Embarked Town")
```

![image](https://github.com/user-attachments/assets/3c238722-34f3-4854-a29f-bf88f7e01551)

```
plt.figure(figsize=(8,5))
sns.barplot(x='Embarked', y='Fare', data=tit, palette='rainbow', hue='Pclass')
plt.title("Fare of Passenger by Embarked Town, Divided by Class")
```

![image](https://github.com/user-attachments/assets/95b90c74-6f3a-48a5-b1c5-004d3b162a35)

```
tips=sns.load_dataset('tips')
sns.scatterplot(x='total_bill', y='tip', hue='sex', data=tips)
plt.xlabel('Total Bill')
plt.ylabel("Tip Amount")
plt.title('Scatter Plot of Total Bill vs. Tip Amount')
```

![image](https://github.com/user-attachments/assets/6f10b028-cd47-4405-92ac-36b0ff2835bb)

```
num_var = np.random.randn(1000)
num_var=pd.Series(num_var, name = "Numerical variable")
num_var
```

![image](https://github.com/user-attachments/assets/024b20a7-cd24-4a9b-b3c5-1f0d76799490)

```
sns.histplot(data = num_var, kde = True)
```

![image](https://github.com/user-attachments/assets/55ebf5c4-1c45-462b-b07a-80f99b1605c9)

```
df=pd.read_csv("titanic_dataset.csv")
sns.histplot(data=df,x="Pclass", hue="Survived", kde=True)
```

![image](https://github.com/user-attachments/assets/72f121cb-b073-4d53-bc22-45eb88a4129f)

```
tips=sns.load_dataset('tips')
sns.boxplot(x=tips['day'], y=tips ['total_bill'], hue=tips['sex'])
```

![image](https://github.com/user-attachments/assets/99dc53a1-0588-49a8-a7b0-f398a247513e)

```
sns.boxplot(x="day", y="total_bill", hue="smoker", data=tips, linewidth=2, width=0.6, boxprops={"facecolor": "lightblue", "edgecolor": "darkblue"},
whiskerprops={"color": "black", "linestyle": "--", "linewidth": 1.5}, capprops={"color": "black", "linestyle": "--", "linewidth": 1.5})
```

![image](https://github.com/user-attachments/assets/1b922c79-6d3b-4ea7-9843-b85730b80c3b)

```
sns.violinplot(x="day", y="total_bill", hue="smoker", data=tips, linewidth=2, width=0.6, palette="Set3", inner="quartile")
plt.xlabel("Day of the Week")
plt.ylabel("Total Bill")
plt.title("Violin Plot of Total Bill by Day and Smoker Status")
```

![image](https://github.com/user-attachments/assets/57bfd887-9382-48cc-88d2-adf66ca309a0)

```
mart=pd.read_csv("titanic_dataset.csv")
mart
```

![image](https://github.com/user-attachments/assets/9e3c7f71-6205-4561-be3b-16417454b036)

```
mart=mart[['PassengerId', 'Survived', 'Age', 'Name', 'Ticket', 'Embarked']]
mart.head(10)
```

![image](https://github.com/user-attachments/assets/3a9ccd96-3e10-4963-be35-2b1593743424)

```
sns.kdeplot(data=mart,x='PassengerId')
```

![image](https://github.com/user-attachments/assets/1fd32aae-66c4-4c24-9b60-83723236a95e)

```
sns.kdeplot(data=mart,x='Age')
```

![image](https://github.com/user-attachments/assets/3c8eb6b5-631c-487f-bf5a-919bec90b4a1)

```
sns.kdeplot(data=mart)
```

![image](https://github.com/user-attachments/assets/76bfc3b9-8cca-4b1a-9e57-2e6d443ec094)

```
sns.kdeplot(data=mart,x='PassengerId',hue='Survived',multiple='stack')
```

![image](https://github.com/user-attachments/assets/de3820bb-8682-4f26-a6a8-72022ed6bb94)

```
sns.kdeplot(data=mart,x='PassengerId',y='Survived')
```

![image](https://github.com/user-attachments/assets/a8470792-adb3-40fb-bfbc-cc3279565317)

```
data = np.random.randint(low = 1, high = 100, size = (10,10))
hm=sns.heatmap(data=data,annot=True)
```

![image](https://github.com/user-attachments/assets/a057e3d7-068e-4d8b-b516-7f3696cb3c65)

```
hm=sns.heatmap(data=data)
```

![image](https://github.com/user-attachments/assets/340169db-e695-4cc1-9e33-9bcaa7652e2f)


# Result:
Thus, all the data visualization techniques of seaborn has been implemented.
