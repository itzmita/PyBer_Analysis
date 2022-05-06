# PyBer_Analysis

# Analyzing data for PyBer

## Overview:

Purpose of this analysis is to visually analyze the performance of a ridesharing company PyBer. The data points provided in this Challenge was ride data for 2019 in 2 spreadsheets . One had information about the cities , the type of cities (Urban, Suburban, Rural) and the number of drivers each of the cities have. The second spreadsheet had for each city how many rides were made, the ride ID and the date-timestamp of when a particular ride happened. The goal is to create a multi-line graph which will show total weekly fares for each type of city.


## Results

For the analysis we create a merged DataFrame using both the spreadsheet data. The common data point between the 2 csv files was "city" which was used to merge the data. We also used groupby by the "type" so we can see data by the city types. 

Below is the snapshot of the merged DataFrame.

![image](https://user-images.githubusercontent.com/3753839/167056300-932db4b1-cad4-49a6-a22e-1a787139e2e4.png)


From the above data we can clearly see that there are way more riders in the Urban cities than Suburban and Rural cities. 
The total number of Drivers are also more in the Urban cities than Rural cities. Hence the Urban cities are shown to generate more Revenue than the Suburban and Rural cities. 
However we see that the Average fare per ride for Urban cities is very less compared to the Suburban and Rural cities. Also the same with the Average Fare per Driver which is very less in Urban cities. 

Next we used reset_index function to reset the index which is done for pivot function to work.
In the pivot function we had "date" as the index and columns as "type" and values as "fare". 
This basically created a DataFrame which has date as the index and the different types of cities came up as columns with the total fare for that date. Below is the screen shot for the DataFrame.

![image](https://user-images.githubusercontent.com/3753839/167056319-4258dd74-e34d-45bf-8c13-c8c0b3382fd8.png)


We further analyzed only a particular timeframe from Jan to April 2019 data for our line graph.
We filtered this duration using the "loc" function on the index. 
Next we used the "resample" function with a parameter 'W' to get the sum of fares per week.
The below data shows weekly basis what are the Fares across different types of cities.

![image](https://user-images.githubusercontent.com/3753839/167056363-10c942de-1d2b-4da5-bcab-09a8854d72ff.png)




The below snapshot shows the line graph that was plotted using the above DataFrame.
As you see below we didn't have to mention x axis or y axis as it is a DataFrame and the index is considered by Default to be the x axis. 

The line graph as shown below which is named as 'Total Fare by City Type" also supports the above metrices in the PyBer Summary DataFrame. The yellow line below shows the Urban Fares which started around $1600 beginning in Jan and was in its peak during last week of Feb at $2466 , second week of March at $2470 and somewhat same in April. Similar trends are seen for Suburban and Rural cities as well which start off with way less Fare. But the peak was seen around last week of Feb and again in 1st week of April.

![image](https://user-images.githubusercontent.com/3753839/167056431-374cd4fa-4a7a-4865-bcd6-5dc273806f5c.png)



## Summary:


The Rural cities have way less driver count, but compared to the rides happening, it is still more. PyBer might need to see why the count is so less. Is it because people have their own transportation and don’t want to pay for rideshare? Also we should see why the averages fares are more per ride and per driver, is it because the distance travelled is more? If we can investigate and find out reasons behind the data points, we can figure out whether more advertizing is needed to let more people be aware of this app.

The Suburban cities are doing okay given that the driver counts are less than the riders. PyBer may need to advertise more in Suburban locations to get more drivers. May be some incentives can be provided to the drivers if they sign up.

There are more drivers in the Urban areas than riders. That's why the averages fares show very less compared to the other cities. We need to see why so many drivers are not getting rides. Could it be possible that riders in Urban cities have more alternative transportations available which are more efficient? Could traffic be the problem which is more in Urban cities due to compact nature of buildings and businesses? We would need more data points like total population, distance travelled, mileage etc. Like what duration a rider takes to reach destination etc. This will give us a better idea to see what can be done in Urban cities to urge more riders to use PyBer rideshare. Schemes like first ride free or less fare on certain occasions may attract more riders.
