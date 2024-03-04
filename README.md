# Exno:1
Data Cleaning Process

# AIM
To read the given data and perform data cleaning and save the cleaned data to a file.

# Explanation
Data cleaning is the process of preparing data for analysis by removing or modifying data that is incorrect ,incompleted , irrelevant , duplicated or improperly formatted. Data cleaning is not simply about erasing data ,but rather finding a way to maximize datasets accuracy without necessarily deleting the information.

# Algorithm
STEP 1: Read the given Data

STEP 2: Get the information about the data

STEP 3: Remove the null values from the data

STEP 4: Save the Clean data to the file

STEP 5: Remove outliers using IQR

STEP 6: Use zscore of to remove outliers

# Coding and Output

import pandas as pd
df=pd.read_csv("/content/SAMPLEIDS.csv")
df

![307849926-cc27d6cf-05b5-4b55-9c0a-2c03001688f9](https://github.com/Prakashmathi2004/exno1/assets/118350045/df22c8dc-336b-4daf-a191-2d126138df7c)


print(df.head(7))

![2](https://github.com/Prakashmathi2004/exno1/assets/118350045/ef50472b-8bdd-4d1b-a076-9e8065f13621)


print(df.tail(2))

![o4](https://github.com/chgeethika/ex-no1/assets/142209368/99c1ad9e-d98c-44a3-96a5-61a8622d6178)

df.info()

![3](https://github.com/Prakashmathi2004/exno1/assets/118350045/80f63398-6ed2-4e1d-8e29-cec2cab464ca)

```
print(df.describe())
```

![4](https://github.com/Prakashmathi2004/exno1/assets/118350045/12e4523b-4886-4856-80f9-d1ed1d1da176)

```
df.isnull().sum()
```

![5](https://github.com/Prakashmathi2004/exno1/assets/118350045/476614ef-43bf-43c8-a0e8-26a5e72b7305)

```
df.nunique()
```

![7](https://github.com/Prakashmathi2004/exno1/assets/118350045/6fe20dc2-23b3-45cc-b8f7-b30b02f74af2)

```
mn=df.TOTAL.mean()
mn
```

![8](https://github.com/Prakashmathi2004/exno1/assets/118350045/fbf24d9d-9648-4267-b28c-d5cfa3fea9c7)


```
df.TOTAL.fillna(mn,inplace=True)
df
```

![9](https://github.com/Prakashmathi2004/exno1/assets/118350045/fa8cb419-762a-4eda-b10a-aa52fe0d2108)

```
min=df.M4.min()
min
```

![10](https://github.com/Prakashmathi2004/exno1/assets/118350045/f1e24de5-10a5-48f5-8944-6d0f98a4b551)

```
df.M4.fillna(min,inplace=True)
df
```

![11](https://github.com/Prakashmathi2004/exno1/assets/118350045/9a95c8e3-6031-4a15-a51b-6f75e88a3833)


![12](https://github.com/Prakashmathi2004/exno1/assets/118350045/102ba8f6-22ef-4261-ab29-f7630d799268)
```
import pandas as pd            
import seaborn as sns      
age=[1,3,28,27,25,92,30,39,40,50,26,24,29,94]
af=pd.DataFrame(age)
af
```

![13](https://github.com/Prakashmathi2004/exno1/assets/118350045/4e8ed674-4aff-4af0-96e4-7efe0bbebcbd)


sns.boxplot(data=af)

![14](https://github.com/Prakashmathi2004/exno1/assets/118350045/e2657120-59f0-41bb-ba3b-ab74edf220e9)


```
sns.scatterplot(data=af)
```

![15](https://github.com/Prakashmathi2004/exno1/assets/118350045/4ea36b3d-033c-436b-bce8-48d2b9c5ea6b)

```
q1=af.quantile(0.25)
q2=af.quantile(0.50)
q3=af.quantile(0.75)
iqr=q3-q1
iqr
low=q1-1.5*iqr
low
high=q3+1.5*iqr
high
```
![16](https://github.com/Prakashmathi2004/exno1/assets/118350045/d27da8cc-c75b-4062-be1e-d3c1c665f2aa)


af=af[((af>=low)&(af<=high))]
af

![17](https://github.com/Prakashmathi2004/exno1/assets/118350045/6da3bbf6-6284-4dce-a43f-2549d291ca41)

af.dropna()

![18](https://github.com/Prakashmathi2004/exno1/assets/118350045/3c8ef0c0-770b-4c44-99c9-811bafd3bc7f)

sns.boxplot(data=af)

![o18](https://github.com/chgeethika/ex-no1/assets/142209368/7b62062c-59cc-4789-bbcf-5e4fd63c0b53)


sns.scatterplot(data=af)

![o19](https://github.com/chgeethika/ex-no1/assets/142209368/d294460b-cd0a-4f8e-8ea7-495169adb75c)

data=[1,12,15,18,21,24,27,30,33,36,39,42,45,48,51,54,57,60,63,66,69,72,75,78,81,84,87,90,93,96,99,102,105]
df=pd.DataFrame(data)
df

![o20](https://github.com/chgeethika/ex-no1/assets/142209368/bff14676-97ae-4ebd-9897-89d9e8a3bc87)

import numpy as np
from scipy import stats
z=np.abs(stats.zscore(df))
z

![o22](https://github.com/chgeethika/ex-no1/assets/142209368/9a5242a4-f1c6-4ffa-96b1-fa68c0aa81ab)

# Result
Thus the given program executed successfully.
