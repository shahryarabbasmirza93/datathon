

Data Parsing, Cleansing and Prediction.

Overview:
Since mid-March, the National Cabinet of Australia deployed a set of key preventative measures such as social distancing, closing state borders, closing non-essential services and quarantine. While these measures have effectively influenced in the reduction of daily infection rate, but it has encouraged new challenges such as many people working from and most of the commercial premises were empty. A point of widespread interest is how the lockdown is affecting the energy demand. In order to predict electricity consumption there are several factors which influence such as 
    Temperature
    Public Holidays 
    Population 
    Day of the week
    
Daily electricity demand in various states of Australia data can be obtained from AEMO
https://aemo.com.au/energy-systems/electricity/national-electricity-market-nem/data-nem/aggregated-data

Task 1: Auditing and cleansing the loaded data

The data I am using is hourly power consumption data from AEMO. Energy consumption has some unique characteristics. 
To make my task simpler and easier to visualize, I will only keep the columns SETTLEMENTDATE and Total Demand of a specific state(i.e NSW or VIC or QLD or SA). In the end i will combine the excell files . If you want to run the python code, just open in the colab and run four .ipynb files which is specific to each state. And in the end i have saved the predicted values along with the other features to analyse it.

To get started with, I have created a time series features from SETTLEMENTDATE and then resample it. Resampling the data gives me the average Electricity consumption 
of each day.


As Temperature has a major role in energy consumption, i will add the minimum and maximum temperatures adjacent to the date column. I will 
use excell as its quite easy to include the different columns and filled the empty values with preceding values.
http://www.bom.gov.au/climate/data/stations/


As the data i am trying to analyse is from 2005 to 2020, i will add the population of the respective state in particular year. Because its 
Obvious that the of the electricity demand increases if the population of a state increase.
https://www.abs.gov.au/websitedbs/D3310114.nsf/Home/census

Next when i analysed the data, i came to know that energy consumption is quite low during weekends. Which means public holidays can also 
affect in the energy consumption. So, my last feature will be list of public holidays. Once i had a list of holidays, i have used excell where i created a column that has '0' or '1' , where '0' specifically means that day is not holiday and '1' for public holidays. 
https://info.australia.gov.au/about-australia/special-dates-and-events/public-holidays

After doing this i will check for the outliers and missing values. 


Task 2: Predicting Energy Demand 

I will use three models to predict the consumption of electricity. As the data after resampling has only 5000 rows, predictions made by neural network were not satisfactory. 
As the data is in the table format, it’s better to use random forest and XGBoost models to get more precise results. Finally used Tableau to build an application where anyone can compare daily, monthly and quarterly predicted values with actual demand.
https://public.tableau.com/profile/shahryar.abbas.mirza#!/vizhome/Book1_16050151563700/Dashboard2?publish=yes


