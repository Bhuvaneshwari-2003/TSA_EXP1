#Name: bhuvaneshwari S

#Register Number: 212221240010

# Ex.No: 01A PLOT A TIME SERIES DATA
###  Date: 

# AIM:
To Develop a python program to Plot a time series data (population/ market price of a commodity
/temperature.
# ALGORITHM:
1. Read the CSV file into a DataFrame with the "DATE" column as the index.
2. Display the first few rows of the DataFrame.
3. Extract data for January 2017.
4. Extract data from May 2017 to June 2017.
5. Compute the mean population for the year 2017.
6. Resample data annually and compute the mean for each year.
7. Plot the annual mean population with labeled axes.
8. Extract data for January 2017.
9. Compute the mean closing price for January 2017.
10. Extract data from May 2017 to August 2017.
11. Resample the closing prices by month and plot the monthly mean.
12. Resample the closing prices by year and plot the yearly mean.
13. Compute the mean temperature for the year 2017.
14. Extract data from May 2015 to August 2015 (note the year discrepancy).
15. Resample mean temperatures by month and plot the monthly mean.
16. Resample mean temperatures by year and plot the yearly mean.
# PROGRAM:
# Population Time Series Data :
```
#dataset: https://fred.stlouisfed.org/series/POPTHM
import matplotlib.pyplot as plt
import pandas as pd
df=pd.read_csv("POPTHM.csv",parse_dates=["DATE"],index_col="DATE")
df.head()
df["2017-01"]
df["2017"].mean()
df["2017-05":"2017-06"]
df.resample('Y').mean()
mean=df.resample('Y').mean().plot(kind='line')
plt.xlabel("Year")
plt.ylabel("Population(in Thousands)")
plt.show()
```
# Market Price of a Commodity Time Series Data :
```
import matplotlib.pyplot as plt
import pandas as pd
df=pd.read_csv("trainset.csv",parse_dates=["Date"],index_col="Date")
df.head()
df["2017-01"]
df["2017-01"].Close.mean()
df["2017-05-01":"2017-08-31"]
df.Close.resample('M').mean()
df.Close.plot(kind='line')
plt.xlabel("Date")
plt.ylabel("Price")
plt.show()
mean=df.Close.resample('M').mean().plot(kind='line')
plt.xlabel("Month")
plt.ylabel("Price")
plt.show()
mean=df.Close.resample('Y').mean().plot(kind='line')
plt.xlabel("Year")
plt.ylabel("Price")
plt.show()
```
# Temperature Time Series Data :
```
import matplotlib.pyplot as plt
import pandas as pd
df=pd.read_csv("ClimateTrain.csv",parse_dates=["date"],index_col="date")
df.head()
df["2017-01"]
df["2017"].mean()
df["2017-05-01":"2015-08-31"]
df['meantemp'].resample('M').mean()
mean=df["meantemp"].resample('M').mean().plot(kind='line')
plt.xlabel("Month")
plt.ylabel("Temperature")
plt.show()
mean=df["meantemp"].resample('Y').mean().plot(kind='line')
plt.xlabel("Year")
plt.ylabel("Temperature")
plt.show()
```

# OUTPUT:
# Population Time Series Data :
![image](https://github.com/user-attachments/assets/71b95f21-fd91-4eef-853f-8a049c56c8ac)

# Market Price of a Commodity Time Series Data :
![image](https://github.com/user-attachments/assets/00f3f5a5-cbae-444e-b36f-a7927726c34c)

![image](https://github.com/user-attachments/assets/5a42b56f-70bb-44d9-86af-9ab25903c68e)

![image](https://github.com/user-attachments/assets/c838ee06-71fb-4f87-b122-7abb479a11a5)


# Temperature Time Series Data :
![image](https://github.com/user-attachments/assets/59900472-0d77-4147-968c-9d91674c3b23)

![image](https://github.com/user-attachments/assets/756ae986-81b0-4c5d-bc00-d29b9067d9d0)


# RESULT:
Thus the successfully implemented the plot a time series data in python.
