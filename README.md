# Air pollution (PM2.5) prediction in Warsaw
PM2.5 - particulate matter with diameters 2.5 micrometers and smaller. 
Model created for fun to test possibility of creating machine learning model based on available data for Warsaw.  


## Weather data 2015-2019
Data retrieved from API https://darksky.net/dev/docs#time-machine-request  

## Pollution data for PM2.5 2015-2019
Data from archive http://powietrze.gios.gov.pl/pjp/archives  

## Available data
Data in initial model:  
* PM2.5 data from 3 stations ('pm25_nie', 'pm25_kon', 'pm25_wok'), 
* set of meteorological data ('winter_break', 'apparentTemperature', 'cloudCover', 'dewPoint', 'humidity', 'precipAccumulation', 'precipIntensity', 'precipProbability', 'precipType', 'pressure', 'temperature', 'uvIndex', 'visibility', 'windBearing', 'windGust', 'windSpeed')
* set of sezonal data ('date', 'year', 'month', 'day','hour', 'day_of_week', 'no_of_week')

Correlation matrix  
![obraz](https://user-images.githubusercontent.com/10920417/161531112-9b0567c1-756c-4a71-862e-f800dd10b281.png)

