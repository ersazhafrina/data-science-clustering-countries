# data-science-clustering-countries
This final project was carried out to meet the requirements for graduating from the Bootcamp for Data Science that was followed who held by Sanbercode.
This final project is in the form of data clustering using Kmeans to determine which country will be selected based on certain criteria.

## Objective:

To categorize countries using socioeconomic and health factors that determine a country's development overall.

## About Organization:

HELP International is an international humanitarian NGO committed to fighting poverty and providing basic facilities and assistance for people in underdeveloped countries during disasters and natural disasters.

## Problems:

HELP International has raised approximately $10 million. Currently, NGO CEOs need to decide how to use this money strategically and effectively. So, the CEO has to make a decision to choose the country that needs it the most help. Therefore, your task is to categorize countries using several socio-economic factors and health that determines the development of the country as a whole. Then you guys need to suggest which country only what the CEO needs to focus on the most.

## Feature column explanation:

- Country : Country name
- Child_death: Death of children under 5 years old per 1000 births
- Exports: Exports of goods and services per capita
- Health: Total health expenditure per capita
- Imports: Imports of goods and services per capita
- Income: Net income per person
- Inflation: A measure of the annual growth rate of Total GDP
- Life_expectancy: The average number of years a newborn child would live if the current death pattern remained the same
- Number_fertility: The number of children that will be born to each woman if the current fertility rate remains the same
- GDPper capita: GDP per capita. Calculated as Total GDP divided by the total population.

## What you need:
Because this file is .ipynb you need to install :
- Google Colaboration/Jupyter Notebook

### If you use Google Colaboration :
- You should Mount Drive to connect the Google Colaboration into your Google Drive
- Place the csv file into a folder
- And type the folder path in your code :
df = pd.read_csv('/content/drive/MyDrive/..../Data_Negara_HELP.csv') 

### If you use Jupyter Notebook in Visual Studio Code :
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

### 1. Data Cleaning : Cleaning the dataset/dataframe untill the data is ready to use
### 2. Use Multivariate Analysis : To take what factors will be used to make decisions
  Multivariate analysis is used to analyze more than 2 variables at the same time, the resulting trends can be multidimensional in nature, this analysis will help us understand which data has complex trends in attribute combinations.
  - The largest value is taken (other than the value 1)
  - There are 2 largest values, namely 0.9 for GDP per capita and Income and 0.85 for Total Fertility and Child Mortality. These four parameters will be used to which countries are eligible for assistance.
  - GDP per capita and income will be used as Social-Economic Factors, while the Total Fertility and Child Mortality will be used as a Factor Health
  
### 3. Do Outliers Treatment : Unnecessary outliers are dropped to prevent overlapping data so the data is more accurate

![outliers](https://user-images.githubusercontent.com/56376510/157673903-1dda23ea-a8a5-4847-b97e-a2a00e8f4374.JPG)

### 4. K-means Clustering
Clustering is the process of grouping similar/similar values (data points) into the same group.
There are many algorithms that can be used to perform clustering. One of them is by means of K-means Clustering.
Because the kmeans algorithm calculates the distance from each data to each centroid and assigns it to the centroid with a certain distance, because the algorithm really wants to optimize (in this case the minimum distance to each centroid) it is easy to calculate the distance and then we average it, with sklearn the total distance is called inertia ( The smaller the inertia, the better the kmeans). Minimize inertia (distance between within 1 cluster).
But if we increase the number of clusters, the inertia value will decrease. Then where is the limit of inertia? The limit is where the inertia value = 0. Because each data point has its own cluster. The smaller the inertia, the better the cluster fit. Then How to find a suitable fit cluster? To find this, we can use the elbow method. Where this method compares the number of clusters with their inertia.

![elbow](https://user-images.githubusercontent.com/56376510/157673659-9ec7f58d-9061-4d09-810c-c5e05130ad87.JPG)

After making the elbow method and determining how many clusters to use, here are the results of the k-means clustering that has been executed :

  - Economic-Social Factor
  
![kmeans 1](https://user-images.githubusercontent.com/56376510/157674195-9d3267fd-9c29-47e2-bd0f-d92a37854853.JPG)

  - Health Factor

![kmeans 2](https://user-images.githubusercontent.com/56376510/157674396-be136764-22cf-4483-8fe5-e2dc3ba46981.JPG)

### 6. Make decisions (prediction) :
   Countries that need to be focused on:
   From the results that have been shown previously, there are 3 countries that need to be focused on in the following order:
   
   - Congo, Dem. Rep.
   This country has a low GDP per capita and low income and high child mortality and fertility rates. Because this country is included in 2 factors with 4 parameters in it, so this country is the main focus for assistance.
   
   - Burundi
   This country has a GDP per capita and low income and high fertility rate. Because this country is included in 2 factors with 3 parameters in it, so this country is one of the focuses for assistance.
   
   - Guinea
   The country has a low GDP per capita and low income and high child mortality. Because this country is included in 2 factors with 3 parameters in it, so this country is also one of the focuses for assistance.

Article Link : https://medium.com/@ersazhafrina/data-science-clustering-countries-with-k-means-clustering-616c16b57fd7
