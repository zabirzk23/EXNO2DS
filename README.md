# EXNO2DS
# AIM:
      To perform Exploratory Data Analysis on the given data set.
      
# EXPLANATION:
  The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.
  
# ALGORITHM:
STEP 1: Import the required packages to perform Data Cleansing,Removing Outliers and Exploratory Data Analysis.

STEP 2: Replace the null value using any one of the method from mode,median and mean based on the dataset available.

STEP 3: Use boxplot method to analyze the outliers of the given dataset.

STEP 4: Remove the outliers using Inter Quantile Range method.

STEP 5: Use Countplot method to analyze in a graphical method for categorical data.

STEP 6: Use displot method to represent the univariate distribution of data.

STEP 7: Use cross tabulation method to quantitatively analyze the relationship between multiple variables.

STEP 8: Use heatmap method of representation to show relationships between two variables, one plotted on each axis.

## CODING AND OUTPUT

```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt

import seaborn as sns
df=pd.read_csv("titanic_dataset.csv")
d
```

<img width="1430" height="495" alt="image" src="https://github.com/user-attachments/assets/9080b30f-78ca-4ac9-b58c-06a8227defc9" />

```
df.info()
```
<img width="416" height="430" alt="image" src="https://github.com/user-attachments/assets/e12272d3-ed80-46e1-9f9b-3f504f4f16da" />

```
df.dtypes
```

<img width="216" height="565" alt="image" src="https://github.com/user-attachments/assets/ae6929a5-afa8-48ee-9035-110f1364078d" />

```
df.describe
```
<img width="868" height="372" alt="image" src="https://github.com/user-attachments/assets/7059c8b0-7932-4479-8556-6070699abde1" />

```
df.value_counts()
```
<img width="1508" height="612" alt="image" src="https://github.com/user-attachments/assets/50f0a8cc-f743-4d37-90d3-30f5580a2362" />

```
df['Age'].value_counts()
```
<img width="189" height="588" alt="image" src="https://github.com/user-attachments/assets/62ac1108-89a0-4314-8ccb-dd62b01b8b7d" />

```
df.shape
```
<img width="556" height="41" alt="image" src="https://github.com/user-attachments/assets/f30c4bc9-71cb-4574-8cfc-cf5933baa7ed" />

```
df.set_index("PassengerId",inplace=True)
df.describe()
```

<img width="736" height="368" alt="image" src="https://github.com/user-attachments/assets/72db707e-36b7-4b94-aa3e-2b589af825d7" />

```
df.nunique()
```

<img width="181" height="527" alt="image" src="https://github.com/user-attachments/assets/7cb12321-ab10-4d6a-a587-7f93d435b79d" />

```
sns.countplot(data=df,x="Survived")
```

<img width="729" height="579" alt="image" src="https://github.com/user-attachments/assets/aff8eb6a-bef7-432b-bdc5-72bfe8c3ddd9" />

```
df.Pclass.unique()
```

<img width="780" height="40" alt="image" src="https://github.com/user-attachments/assets/ea5d5c90-20e0-410e-b120-832395fb16e6" />

```
df.rename(columns={'Sex' :'Gender'},inplace=True)
df
```

<img width="1394" height="560" alt="image" src="https://github.com/user-attachments/assets/6819ef6e-b8d4-4f01-839e-685f70ad4c13" />

```
sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=.7)
```

<img width="889" height="637" alt="image" src="https://github.com/user-attachments/assets/c622589d-089c-4f30-b1fd-fb61e8828afe" />

```
df.boxplot(column="Age",by="Survived")
```

<img width="693" height="604" alt="image" src="https://github.com/user-attachments/assets/736e4964-9bb8-492f-b7f4-d7880743980b" />

```
sns.scatterplot(x=df["Age"],y=df["Fare"])
```

<img width="724" height="564" alt="image" src="https://github.com/user-attachments/assets/4cc9bbef-6441-4c97-8ce3-4f92864398a7" />

```
fig,ax1=plt.subplots(figsize=(8,5))
plt=sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=df)
```
<img width="851" height="555" alt="image" src="https://github.com/user-attachments/assets/252d684d-2a63-41f2-96f7-88244fa9c613" />

```
plt=sns.boxplot(x='Pclass',y='Age',hue='Gender',data=df)
```

<img width="699" height="536" alt="image" src="https://github.com/user-attachments/assets/28454052-1e14-491e-be61-8ac28b9efabc" />

```
sns.catplot(data=df,col="Survived", x="Gender", hue="Pclass", kind="count")
```

<img width="1310" height="593" alt="image" src="https://github.com/user-attachments/assets/2a0c8753-fc86-43a1-a1e3-188a6379b829" />

```
corr=df.select_dtypes(include=np.number).corr()
sns.heatmap(corr,annot=True)
```

<img width="669" height="553" alt="image" src="https://github.com/user-attachments/assets/d7c9d318-826e-4ec0-a76f-5ac1bfd2140f" />


# RESULT

Thus exploratory data analysis on the given data set has been executed successfully
