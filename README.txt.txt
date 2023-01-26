# FuelPrice-Project
Gas prices scrapping and analysis


During a conversation with a friend who lives next to the German border we talked about the price differences of fuel prices across the day. There the idea was born to make a small analysis to determine on which day of the week and what time it's best to fuel your car. 
To practice my scrapping skills instead of using an API I scrapped the data from a webpage which shows the gas prices of stations near my friend during the day.

---------Gather the data---------
To Gather the data I made use of the BeautifulSoup(bs4) and request library in Python. Also a virtual workstation from Oracle was used which runs around the clock. I made a python script which would execute the scrapping action every 5 min and would save the created table every hour to a csv file. 
Scrapped Columns:
-	Station ID – id of station on webpage
-	Station Name – Name of station (Like Shell, Aral, PM, etc)
-	Street – Street name and number of station
-	City – City name and zip code of station
-	Price – Price of selected fuel (95)
-	24/7 – Boolean value which shows if station is 24/7 or not
-	Price Time – Time viewed on website of price
-	Download Time – Time of download webpage

Following the scrapping the data was split over multiple csv files and could be merged to one big table. 

---------Data Wrangling---------
After the data was scrapped it needed to be cleaned since not all values where in the right format to start the analysis.
Cleaning steps:
	- Not available prices (‘x,xx’) need to be changed to NaN values.
	- Date/time values need to be chanced to the right datetime format.
	- The 24/7 column needs to be converted to Boolean value.
	- Indexes columns can be deleted and new index can be created.
	- Time of download_time is local time of workstation instead of the time scrapped.

---------Analysis---------
The data shows us that it is cheapest to fuel on Thursday To Saturday between 13 and 21(1pm-9pm).
Also interesting to know is that the prices an a day on average vary around 25 eurocents.
