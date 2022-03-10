# data-science-clustering-countries
## Objective:

To categorize countries using socioeconomic and health factors that determine a country's development overall.

## About Organization:

HELP International is an international humanitarian NGO committed to fighting poverty and providing basic facilities and assistance for people in underdeveloped countries during disasters and natural disasters.

## Problems:

HELP International has raised approximately $10 million. Currently, NGO CEOs need to decide how to use this money strategically and effectively. So, the CEO has to make a decision to choose the country that needs it the most help. Therefore, your task is to categorize countries using several socio-economic factors and health that determines the development of the country as a whole. Then you guys need to suggest which country only what the CEO needs to focus on the most.

## What you need:

If you use Google Colaboration :
- You should Mount Drive to connect the Google Colaboration into your Google Drive
- Place the csv file into a folder
- And type the folder path in your code :
df = pd.read_csv('/content/drive/MyDrive/..../Data_Negara_HELP.csv') 

If you use Jupyter Notebook in Visual Studio Code :
- Make sure that you have been install this several library :
  numpy
  pandas
  seaborn
  matplotlib.pyplot
- If you haven't installed it yet, please install first
- After finished installing, place the csv folder in the same folder with the code file (.ipynb) and open it in Visual Studio Code
- Then place the file name of the csv file into the code :
df = pd.read_csv('Data_Negara_HELP.csv') 

## Step :

1. Data Cleaning : Cleaning the dataset/dataframe untill the data is ready to use
2. Use Multivariate Analysis : To take what factors will be used to make decisions
  - The largest value is taken (other than the value 1)
  - There are 2 largest values, namely 0.9 for GDP per capita and Income and 0.85 for Total Fertility and Child Mortality. These four parameters will be used to which countries     are eligible for assistance.
  - GDP per capita and income will be used as Socio-Economic Factors, while the Total Fertility and Child Mortality will be used as a Factor Health
  
3. Do Outliers Treatment : Unnecessary outliers are dropped to prevent overlapping data so the data is more accurate

![outliers](https://user-images.githubusercontent.com/56376510/157673903-1dda23ea-a8a5-4847-b97e-a2a00e8f4374.JPG)

5. Do Scaling Data : Use Elbow Method to get the optimal number of clusters

![elbow](https://user-images.githubusercontent.com/56376510/157673659-9ec7f58d-9061-4d09-810c-c5e05130ad87.JPG)

6. Creating k means clustering and visualizing clusters formed :
  - Economic-Social Factor
  
![kmeans 1](https://user-images.githubusercontent.com/56376510/157674195-9d3267fd-9c29-47e2-bd0f-d92a37854853.JPG)

  - Health Factor

![kmeans 2](https://user-images.githubusercontent.com/56376510/157674396-be136764-22cf-4483-8fe5-e2dc3ba46981.JPG)

7. Make decisions (prediction) :
   Countries that need to be focused on:
   From the results that have been shown previously, there are 3 countries that need to be focused on in the following order:
   
   - Congo, Dem. Rep.
   This country has a low GDP per capita and low income and high child mortality and fertility rates. Because this country is included in 2 factors with 4 parameters in it, so      this country is the main focus for assistance.
   
   - Burundi
   This country has a GDP per capita and low income and high fertility rate. Because this country is included in 2 factors with 3 parameters in it, so this country is one of the    focuses for assistance.
   
   - Guinea
   The country has a low GDP per capita and low income and high child mortality. Because this country is included in 2 factors with 3 parameters in it, so this country is also      one of the focuses for assistance.

