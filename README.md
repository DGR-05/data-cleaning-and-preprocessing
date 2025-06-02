# data-cleaning-and-preprocessing
# TASK 1
Data cleaning and preprocessing (Netflix and tv showes)
# Objective

The goal of this project is to clean the Netflix Movies and TV Shows dataset so it’s ready for analysis. This includes:

Fixing or filling missing values

Removing duplicate rows

Making text values consistent (like country names)

Converting dates to the same format

Renaming columns to be clean and easy to use

Making sure each column has the correct data type

# dataset summary
rows-8807

total columns-12

# sample data set

![2025-06-02 (2)](https://github.com/user-attachments/assets/ee0ce550-c6c6-4c72-8911-83121391c134)

# sample code

![Screenshot 2025-06-02 215741](https://github.com/user-attachments/assets/23a0fe0e-0ad2-4921-a129-ed86edbe6536)

# sample output
![Screenshot 2025-06-02 215928](https://github.com/user-attachments/assets/9be5cae8-019f-4774-9e3a-dea651f0e5b0)

# data cleaning and preprocessing code

import pandas as pd
df = pd.read_csv("/content/netflix_titles.csv")

print("initial data:\n",df.head())

print("\n missing values:\n",df.isnull().sum())

print("\n remove duplicate:\n",df.drop_duplicates())

df['country'] = df['country'].str.strip().str.title()

df['type'] = df['type'].str.lower()  

df['date_added'] = pd.to_datetime(df['date_added'], errors='coerce')

df['date_added'] = df['date_added'].dt.strftime('%d-%m-%Y')

df.columns = df.columns.str.strip().str.lower().str.replace(' ', '_')

print(df.dtypes)

df['release_year'] = df['release_year'].astype('int')

df['date_added'] = pd.to_datetime(df['date_added'], errors='coerce')

 # output
![Screenshot 2025-06-02 220635](https://github.com/user-attachments/assets/ba8ba639-0cec-405f-9150-b36b2d0c7949)
![Screenshot 2025-06-02 220710](https://github.com/user-attachments/assets/3aefcef8-c606-44a2-ae9c-e9149bc0e26e)
![Screenshot 2025-06-02 220733](https://github.com/user-attachments/assets/2dc44a91-4dc1-4026-9b4c-b634f59e5598)
![Screenshot 2025-06-02 220733](https://github.com/user-attachments/assets/5e95ace0-002e-4ac8-9f3b-923395392b94)
![Screenshot 2025-06-02 220755](https://github.com/user-attachments/assets/2de7ef81-f2b7-4543-ab1c-90cfadded993)









 
