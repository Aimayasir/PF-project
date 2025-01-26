# PF-project
import pandas as pd
# Data load
df= pd.read_csv("C:\\Users\\hassnain computer\\folder\\data .project.csv")
df.shape
# Data cleaning
df.info()
#df = pd.DataFrame(df)
column = list(df.columns)
column
check empty N\A values
df.isna().sum()
 Cleaning an empty data set
df.dropna()
df.dropna(inplace=True)
# Replace empty values
df.fillna(33)
# Replace a specefic columns

df['Country'].fillna(999)
df['Global Rank'].mean() # take out average
df['Global Rank'].mode()# most common
df['Global Rank'].median()# middle value
# Data duplications
df.duplicated()
#pd.set_option("display.max_rows",None)
#pd.set_option("display.max_columns",None)
#df.duplicated()
df.drop_duplicates()
df.describe()
df.describe(include="all").iloc[[0,10,]]# fetch data from index or position
df.describe(include="all").loc[["min","max"]]#fetch data from values of list
# Adding a new column in data frame
df['col']=5
df
# Remove a column
df.drop(columns=['col'],inplace=True)
df
# Adding a row
a=pd.DataFrame({' University':100,
                'Country':'Pakistan',
                  'city':'Lahore'},
                  index=[0])
a
df=pd.concat([a,df])
df
# Remove a row
df.drop(0,inplace=True)
df
# Slicing in code
df[3:6]
df[3:5:2]
df[['Country']][45:56]
# Flow charts
df['Country'].value_counts().plot(kind="bar")
df['Country'].value_counts().plot(kind="barh")
df['Country'].value_counts().plot(kind="box")
df['Country'].value_counts().plot(kind="density")
df['Country'].value_counts().plot(kind="pie")
df['Country'].value_counts().plot(kind="line")
df['Country'].value_counts().plot(kind="kde")
df['Country'].value_counts().plot(kind="hist")
# Data aggregation

df.aggregate(['sum', 'min'])
 sum values()
df['Global Rank'].sum()

##  std() – Standard Deviation

df['Global Rank'].std()
## var() – Variance Calculation
Computes the variance of a numerical column.
df['Global Rank'].var()
## data preprocessing
df.isnull().sum() 
## rename() – Rename columns
Renames column names for better understanding.
df.rename(columns={'University': 'Uni'}, inplace=True)

#  Data Saving
df = pd.read_csv("data .project.csv")
df
df.to_excel("newdata.xlsx", sheet_name="newsheet")
