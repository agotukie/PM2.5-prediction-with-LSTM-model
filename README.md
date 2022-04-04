# Air pollution (PM2.5) prediction in Warsaw
PM2.5 - particulate matter with diameters 2.5 micrometers and smaller. 
Model created for fun to test possibility of creating machine learning model based on available data for Warsaw.  


## Weather data 2016-2020
Data retrieved from API https://darksky.net/dev/docs#time-machine-request  

## Pollution data for PM2.5 2016-2020
Data from archive http://powietrze.gios.gov.pl/pjp/archives  

## Available data
Data in initial model:  
* PM2.5 data from 1 station ('pm25_wok'), 
* set of meteorological data ('cloudCover', 'humidity', 'precipitation','pressure', 'temperature', 'visibility', 'windBearing', 'windSpeed',)
* set of sezonal data ('month',  'hour', 'day_of_week')

Correlation matrix  
![obraz](https://user-images.githubusercontent.com/10920417/161531112-9b0567c1-756c-4a71-862e-f800dd10b281.png)

## Tested models

Machine learning model:  
* LightGBM

Neural network models - layers:
* LSTM
* Conv+MaxPool+LSTM+Dropout
* LSTM+LSTM (autoencoder)


## Comparision of different single models  
The best result gave simple basic LSTM  
|dataset | metric |	ML model (lightGBM)	| basic LSTM	| Conv+MaxPool+LSTM+Dropout |	LSTM+LSTM   | 
|:---: | :---: | :---: | :---: | :---: | :---: | 
|validation	 | RMSE	 | 8.330	 | 7.709	 | 7.771	 | 8.211 | 
|validation	 | R2	 | 45.8%	 | 53.6%	 | 52.8%	 | 47.4% | 
|test	 | RMSE	 | 8.272	 | **6.694**	 | 7.261	 | 7.180 | 
|test	 | R2	 | 28.5%	 | **53.1%**	 | 44.8%	 | 46.0% | 

## Comparision of LSTM models combined with ML model (LightGBM)   
The best result gave simple basic LSTM combined with ML model. Results where better than single LSTM  
|dataset |	metric |	basic LSTM & LightGBM |	Conv+MaxPool+LSTM+Dropout  & LightGBM |	LSTM+LSTM  & LightGBM|
|:---: | :---: | :---: | :---: | :---: |
|validation |	RMSE |	7.135 |	7.185 |	7.346 |
|validation |	R2 |	60.2% |	59.7% |	57.9% |
|test |	RMSE |	**6.449** |	6.772 |	6.489 |
|test |	R2 |	**56.4%** |	52.0% |	55.9% |
