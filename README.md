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

df=pd.read_csv("SAMPLEIDS.csv")

df
<img width="1079" height="868" alt="image" src="https://github.com/user-attachments/assets/47bf7158-e9eb-4ce8-b3ab-ba8a34d862cb" />

# df.head()
<img width="1043" height="254" alt="image" src="https://github.com/user-attachments/assets/1a93d13c-1254-43fb-b1c4-3ebf681842ee" />

# df.tail()
<img width="1062" height="296" alt="image" src="https://github.com/user-attachments/assets/41b9b5f9-ead7-4287-8595-aed886ddcf8d" />

# df.isnull()
<img width="861" height="880" alt="image" src="https://github.com/user-attachments/assets/373973df-89ca-4c69-9096-ce17537e92ff" />

# df.isnull().sum()
<img width="235" height="552" alt="image" src="https://github.com/user-attachments/assets/3ebd1933-78f8-418f-b9dd-e5fffb349941" />

# df.notnull().sum()
<img width="223" height="551" alt="image" src="https://github.com/user-attachments/assets/443b374e-f44a-4cd9-9be7-00c1542e81d3" />

# df.isnull().any()
<img width="401" height="558" alt="image" src="https://github.com/user-attachments/assets/2e8ce49f-aed1-4d47-85d4-0a7ff19ba83e" />

# df.dropna()
<img width="1057" height="552" alt="image" src="https://github.com/user-attachments/assets/b9ca70cf-0849-4ab1-a3a8-915ec04274ed" />

# df.dropna(axis=0)
<img width="1068" height="559" alt="image" src="https://github.com/user-attachments/assets/15e3afde-9e33-4af1-9e36-e01ff722e4a1" />

# df.dropna(axis=1)
<img width="321" height="871" alt="image" src="https://github.com/user-attachments/assets/7ec9faad-98d7-4c52-a73f-3a366032f23a" />

# df.fillna(0)
<img width="1038" height="882" alt="image" src="https://github.com/user-attachments/assets/7fb609ed-2d39-47fc-8588-37cd94f1932a" />

#df.fillna({'GENDER':'MALE','NAME':'SRI','ADDRESS':'POONAMALEE','M1':'97','M2':'99','M3':'89'})
<img width="1051" height="867" alt="Screenshot 2025-08-26 214750" src="https://github.com/user-attachments/assets/1ffcea76-e9b3-48ef-a498-bc2186fc8528" />

#ir=pd.read_csv('/content/iris.csv')

ir

<img width="744" height="521" alt="image" src="https://github.com/user-attachments/assets/d9c56f30-39ae-47c9-858b-755a718d3c39" />

# ir.describe()
<img width="628" height="372" alt="image" src="https://github.com/user-attachments/assets/2b1fb4a5-c036-46a4-b62c-892061079c2a" />

import seaborn as sns

sns.boxplot(x='sepal_width',data=ir)

<img width="749" height="578" alt="image" src="https://github.com/user-attachments/assets/3e286c38-006a-4b06-a0b9-6b7cac815b83" />

q1=ir.sepal_width.quantile(0.25)

q3=ir.sepal_width.quantile(0.75)

iq=q3-q1

print(iq)

<img width="62" height="27" alt="image" src="https://github.com/user-attachments/assets/d410ba80-da82-46f1-bcbd-84bcf3a8f285" />

rid=ir[((ir.sepal_width<(q1-1.5*iq))|(ir.sepal_width>(q3+1.5*iq)))]

rid['sepal_width']

<img width="263" height="256" alt="image" src="https://github.com/user-attachments/assets/411b8b75-0d2f-471a-bb0a-abba817d3125" />

derid=ir[~((ir.sepal_width<(q1-1.5*iq))|(ir.sepal_width>(q3+1.5*iq)))]

derid['sepal_width']

<img width="197" height="544" alt="image" src="https://github.com/user-attachments/assets/c496f4ab-ca30-4941-a6b9-4634b68c4681" />

derid=ir[~((ir.sepal_width<(q1-1.5*iq))|(ir.sepal_width>(q3+1.5*iq)))]

derid

<img width="701" height="531" alt="image" src="https://github.com/user-attachments/assets/7d5193e4-99c4-498a-a544-d003033e27a0" />

sns.boxplot(x='sepal_width',data=derid)

<img width="766" height="580" alt="image" src="https://github.com/user-attachments/assets/6212e60c-ada1-4494-9845-fbfeb59e7452" />

import matplotlib.pyplot as plt

import pandas as pd

import numpy as np

import scipy.stats as stats

dataset=pd.read_csv('/content/iris.csv')

dataset

<img width="698" height="513" alt="image" src="https://github.com/user-attachments/assets/b4b80587-2cf1-4228-b2a8-fa4c7c33a85e" />

z=np.abs(stats.zscore(dataset['sepal_width']))

z

<img width="752" height="659" alt="image" src="https://github.com/user-attachments/assets/d32fa85f-4110-4dbe-9cc4-62326e312eb1" />

dataset1=dataset[(z<3)]

dataset1

<img width="659" height="538" alt="image" src="https://github.com/user-attachments/assets/bcefcc93-2700-463c-b1f5-8ab3d3eb86a0" />

# Result
The given data and perform data cleaning and save the cleaned data to a file.
