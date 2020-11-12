Datathon Challenge 

Data Parsing, Cleansing and Prediction

Overview:
Since mid-march, the National Cabinet of Australia deployed a set of key preventative measures such as social distancing, 
closing state borders, closing non-essential services and quarantine. While these measures have effectively influenced in the 
reduction of daily infection rate, but it has encouraged new challenges such as many people working from and most of the 
commercial premises were empty. A point of widespread interest is how the lockdown is affecting the energy demand. Inorder to predict 
electricity consumption there are several factors which influence such as 
    Temperature
    Public Holidays 
    Population 
    Day of the week
    
Daily electricity demand in various states of australia data can be obtained from AEMO
https://aemo.com.au/energy-systems/electricity/national-electricity-market-nem/data-nem/aggregated-data

Task 1:Auditing and cleansing the loaded data

The data i am using is hourly power consumption data from AEMO. Energy consumtion has some unique charachteristics. 
To make my task simpler and easier to visualize, I will only keep the columns SETTLEMENTDATE and Total Demand.  Now  i have 
created a time series features from SETTLEMENTDATE and then resample it. Resampling the data gives me the average Electricity consumption 
every day.


As Temperature has a major role in energy consumption, i will add the minimum and maximum temperatures adjacent to the date column. 
http://www.bom.gov.au/climate/data/stations/


As the data i am trying to analyse is from 2005 to 2020, i will add the population of the respective state in particular year.
https://www.abs.gov.au/websitedbs/D3310114.nsf/Home/census

Next when i analysed the data, i came to know that energy consumption is quite low during weekends. Which means public holidays can also 
affect in the energy consumption. So my last feature will be list of public holidays. After doing this i will check for the outliers 
and missing values. 
https://info.australia.gov.au/about-australia/special-dates-and-events/public-holidays


Task 2: Predicting Energy Demand 

I will use three models to predict the consumption of electricity. As the data after resampling has only 5000 rows, predictions made by neural network were not satisfactory. 
As the data is in the tablar, i used random forest and XGboost models to predict the demand. Finally used Tableau to build an 
application where anyone can compared daily, monthly and quarterly predicted values with actual demand.
https://public.tableau.com/profile/shahryar.abbas.mirza#!/vizhome/Book1_16050151563700/Dashboard2?publish=yes

It is encouraging to see that, so far, overall demand has not dropped as significant as in some other countries. However the impacts of the pandemic on individual sectors are dramatic, and it is important to monitor the situation.


    

