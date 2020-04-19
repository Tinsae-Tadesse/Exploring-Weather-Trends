# Objective
Objective of this project is to compare local temperature data (for Asmara city in Eritrea) with the global temperature trend.

# Methodology
## Getting the Data
*	To search the nearest capital city from the country where I live in, I used the SQL query:    
```SELECT * FROM city_list ORDER BY city_list.country;```
*	To get the temperature data for Asmara city, I used the query:    
```SELECT * FROM city_data WHERE city_data.city = 'Asmara' AND city_data.country = 'Eritrea';```
*	Furthermore; the same query was used to extract temperature data for Nairobi and Khartoum. These are used for comparison purpose.
*	To get the global temperature data, I used the query:    
```SELECT * FROM global_data;```
*	All the return data were saved as a CSV file.
## Exploring the Data
*	_Excel_ was used to analyze and visualize the data.
*	The global temperature data starts at the year of 1750. Nairobi’s and Khartoum’s data start at the year of 1850 and 1859 respectively. However; Asmara’s (is the local) data starts at the year of 1864. Furthermore; there are lots of missing values in the data during 1864-1874. Hence; data starting from the year of 1875 was considered for all countries including the global temperature. Any _missing values after 1875 are replaced by the previous five years’ average temperature_. 
*	The _moving average temperature was calculated using the previous five years of data_.
*	Since type of the data is time series and numerical, it can be best visualized using _line chart_. However; to visualize the relationship between variables _scatterplot_ was used.

# Result and Discussion
The local and global temperature trend is depicted in the following figure.
![](images/Explore_Weather_Trends.jpg)    
**Figure 1**: Five year moving average of local and global temperature.    
*	As Figure 1 shows, _Asmara’s average temperature is hotter than the global average_. As shown in Figure 2, the difference between Asmara’s average temperature and the global average temperature is _consistently around 15<sup>o</sup>C_. The average temperature difference was 15.37<sup>o</sup>C.    
![](images/Explore_Weather_Trends_2.jpg)    
**Figure 2**: Five year moving average of temperature difference between local and global.
*	_Both the global and local average temperatures are slowly rising_. However; the range in average temperature of Asmara is higher than the range of global average, as R<sub>Global</sub>=2.06<sup>o</sup>C and R<sub>Asmara</sub>=2.9<sup>o</sup>C. Hence; _the maximum local temperature change is higher than the global_ by 0.84<sup>o</sup>C.
*	The range of local and global temperature during 1976-2015(past 39 years) is higher than the range in 1875-1975(past 100 years). R<sub>(1875-1975)</sub><sup>Global</sup>=1.18<sup>o</sup>C and R<sub>(1875-1975)</sub><sup>Asmara</sup>=1.57<sup>o</sup>C, however; R<sub>(1976-2015)</sub><sup>Global</sup>=1.48<sup>o</sup>C and R<sub>(1976-2015)</sub><sup>Asmara</sup>=2.21<sup>o</sup>C. Hence; the _maximum temperature change in the past 39 years was higher than the past 100 years_.
