# Ex-01_DS_Data_Cleansing


## Aim:
To read the given data and perform data cleaning and save the cleaned data to a file. 

# Explanation:
Data cleaning is the process of preparing data for analysis by removing or modifying data that is incorrect ,incompleted , irrelevant , duplicated or improperly formatted. 
Data cleaning is not simply about erasing data ,but rather finding a way to maximize datasets accuracy without necessarily deleting the information. 

# ALGORITHM:
### STEP 1
Read the given Data
### STEP 2
Get the information about the data
### STEP 3
Remove the null values from the data
### STEP 4
Save the Clean data to the file

# CODE and OUTPUT:
Name:S.S.SRIRAM

Reg no: 212222230150
```python
import pandas as pd
df=pd.read_csv("SAMPLEDS - Sheet1 (2).csv")
df.shape
```
<img width="67" alt="image" src="https://github.com/TejaswiniGugananthan/ODD2023-Datascience-Ex01/assets/121222763/7ca532f8-7d4e-413f-91c1-c70b7fbf5154">

```python
df.dropna(how='any').shape
```
<img width="59" alt="image" src="https://github.com/TejaswiniGugananthan/ODD2023-Datascience-Ex01/assets/121222763/4dab5c44-e449-4cd5-8f5a-9660968e2ee4">

```python
df.head()
```
<img width="602" alt="image" src="https://github.com/TejaswiniGugananthan/ODD2023-Datascience-Ex01/assets/121222763/ec90de3d-9dfa-45cd-9ab1-18450cae3dc8">

```python
df.tail()
```
<img width="614" alt="image" src="https://github.com/TejaswiniGugananthan/ODD2023-Datascience-Ex01/assets/121222763/07e5ebcc-e055-4066-b8c0-7760577bd2da">

```python
x=df.dropna(how='any')
x
```
<img width="413" alt="image" src="https://github.com/TejaswiniGugananthan/ODD2023-Datascience-Ex01/assets/121222763/5e799694-5e83-4a9f-901c-1b3da38be0d9">

```python
df.dropna(how='any').shape
```
<img width="62" alt="image" src="https://github.com/TejaswiniGugananthan/ODD2023-Datascience-Ex01/assets/121222763/5eef494d-f5c8-458b-b08b-06fa12b4c02e">

```python
df.dropna(how='all').shape
```
<img width="62" alt="image" src="https://github.com/TejaswiniGugananthan/ODD2023-Datascience-Ex01/assets/121222763/c2d73c9e-daa8-4ec5-8dc9-78d53480e5de">

```python
tot=df.dropna(subset=['TOTAL'],how='any')
tot
```
<img width="408" alt="image" src="https://github.com/TejaswiniGugananthan/ODD2023-Datascience-Ex01/assets/121222763/45076178-c1c2-4b8d-bfa1-c355a1a379e7">

```python
tot=df.dropna(subset=['M1','M2','M3','M4'],how='any')
tot
```
<img width="407" alt="image" src="https://github.com/TejaswiniGugananthan/ODD2023-Datascience-Ex01/assets/121222763/a01152ac-bc34-45fe-b35c-ff6dcb26c19a">

```python
df.fillna(0)
```
<img width="410" alt="image" src="https://github.com/TejaswiniGugananthan/ODD2023-Datascience-Ex01/assets/121222763/73f902e7-f657-46c8-9538-553180afebf7">

```python
df.fillna(method='ffill')
```
<img width="307" alt="image" src="https://github.com/TejaswiniGugananthan/ODD2023-Datascience-Ex01/assets/121222763/228f99ed-5133-476b-b869-3d72c84f30b6">

```python
df.fillna(method='bfill')
```
<img width="307" alt="image" src="https://github.com/TejaswiniGugananthan/ODD2023-Datascience-Ex01/assets/121222763/50082da2-af84-440a-ad6a-488ebbaaf54c">

```python
m=df.TOTAL.mean()
m
```
<img width="52" alt="image" src="https://github.com/TejaswiniGugananthan/ODD2023-Datascience-Ex01/assets/121222763/f38f04ff-ae74-416e-9246-82c302813f3e">

```python
df.TOTAL.fillna(m,inplace=True)
df
```
<img width="314" alt="image" src="https://github.com/TejaswiniGugananthan/ODD2023-Datascience-Ex01/assets/121222763/85058462-8bfb-4aff-ae0c-a5342d63bd3e">

```python
df.duplicated()
```
<img width="43" alt="image" src="https://github.com/TejaswiniGugananthan/ODD2023-Datascience-Ex01/assets/121222763/94970260-d50d-46d6-81a8-0481764d7421">

```python
df.drop_duplicates(inplace=True)
df
```
<img width="314" alt="image" src="https://github.com/TejaswiniGugananthan/ODD2023-Datascience-Ex01/assets/121222763/0907b382-f99d-4a97-af8f-5cd3023c7291">

```python
df['cd']=pd.to_datetime(df['DOB'])
df
```
<img width="348" alt="image" src="https://github.com/TejaswiniGugananthan/ODD2023-Datascience-Ex01/assets/121222763/8200da4a-e93a-4b93-b086-d573beae466b">

```python
for x in df.index:
  if df.loc[x,"AVG"]>100:
    df.drop(x,inplace=True)
df
```
<img width="343" alt="image" src="https://github.com/TejaswiniGugananthan/ODD2023-Datascience-Ex01/assets/121222763/439617cd-5804-49c5-aad4-17ced8e6333e">

```python
import seaborn as sns
sns.heatmap(df.isnull(),yticklabels=False,annot=True)
```
<img width="196" alt="image" src="https://github.com/TejaswiniGugananthan/ODD2023-Datascience-Ex01/assets/121222763/dae5ea73-2958-4e12-9e61-1ad193e52fb7">

# Result:
Thus,the given data is read,cleansed and the cleaned data is saved into the file.

