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
```
import pandas as pd
df=pd.read_csv("/content/SAMPLEIDS.csv")
df
```
![image](https://github.com/hindhujanaki/exno1/assets/148514666/42a5863a-ee8d-45de-b4c7-92c9cb5cd486)
```
print(df.head(7))
```
![image](https://github.com/hindhujanaki/exno1/assets/148514666/031860d7-e348-42dd-802e-65dcb08db708)
```
print(df.tail(2))
```
![image](https://github.com/hindhujanaki/exno1/assets/148514666/c67715fa-1343-42da-b5a2-94eb6687e59a)
```
df.info()
```
![image](https://github.com/hindhujanaki/exno1/assets/148514666/789f3d49-9296-4bf6-9574-9137b88a3067)

```
print(df.describe())
```
![image](https://github.com/hindhujanaki/exno1/assets/148514666/8e73ba68-2b16-4a0f-8c4b-9b6f0afd7e98)
```
df.isnull().sum()
```
![image](https://github.com/hindhujanaki/exno1/assets/148514666/bdc0f746-67dd-4fb1-84e8-de6057bbfe05)
```
df.nunique()
```
![image](https://github.com/hindhujanaki/exno1/assets/148514666/932c8f7e-682a-498a-a6b2-9493b3bafb92)
```
mn=df.TOTAL.mean()
mn
```
![image](https://github.com/hindhujanaki/exno1/assets/148514666/d9d570ce-5faf-4b40-bc43-243a0b6fb7c2)

```
df.TOTAL.fillna(mn,inplace=True)
df
```
![image](https://github.com/hindhujanaki/exno1/assets/148514666/e8359f21-311c-4778-be50-8ac94b040f1c)

```
min=df.M4.min()
min
```

![image](https://github.com/hindhujanaki/exno1/assets/148514666/6c7ad4b9-3d49-44ef-95d3-ef52a6ebc4ca)
```
df.M4.fillna(min,inplace=True)
df
```
![image](https://github.com/hindhujanaki/exno1/assets/148514666/968cea78-d1af-41fb-bc83-2d5d158f6472)

![image](https://github.com/hindhujanaki/exno1/assets/148514666/96308a3e-e695-478e-9c21-46b155e5ef3e)

```
import pandas as pd
import seaborn as sns
age=[1,3,28,27,25,92,30,39,40,50,26,24,29,94]
af=pd.DataFrame(age)
af
```

![image](https://github.com/hindhujanaki/exno1/assets/148514666/39d30010-7a22-4035-b759-09afa88ee03c)
```
sns.boxplot(data=af)
```
![image](https://github.com/hindhujanaki/exno1/assets/148514666/3e4fb417-6c37-4385-92d6-d8b392954ea7)
```
sns.scatterplot(data=af)
```
![image](https://github.com/hindhujanaki/exno1/assets/148514666/03f20a5c-e209-4444-8e4c-406030319489)
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
![image](https://github.com/hindhujanaki/exno1/assets/148514666/2685680a-cca0-4263-9916-cd9a8a9cd659)

```
af=af[((af>=low)&(af<=high))]
af
```
![image](https://github.com/hindhujanaki/exno1/assets/148514666/061a0aad-0e4b-44bf-81ad-4eca31b9f621)
```
af.dropna()
```
![image](https://github.com/hindhujanaki/exno1/assets/148514666/332840f6-365a-49ff-bcea-8a3db752c5e0)
```
sns.boxplot(data=af)
```
![image](https://github.com/hindhujanaki/exno1/assets/148514666/fbd3ca73-67f9-43aa-8a7e-da605b015222)

```
sns.scatterplot(data=af)
```
![image](https://github.com/hindhujanaki/exno1/assets/148514666/efb1afe0-fba4-4fac-9737-ba64b9dcfbef)

```
data=[1,12,15,18,21,24,27,30,33,36,39,42,45,48,51,54,57,60,63,66,69,72,75,78,81,84,87,90,93,96,99,102,105]
df=pd.DataFrame(data)
df
```
![image](https://github.com/hindhujanaki/exno1/assets/148514666/9ac37805-524e-46a3-ba67-1bc775afab76)
```
import numpy as np
from scipy import stats
z=np.abs(stats.zscore(df))
z
```
![image](https://github.com/hindhujanaki/exno1/assets/148514666/8d368216-7440-4be8-879f-13d054f2fa55)

# Result
Thus the given program executed successfully.
