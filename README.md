# Share-Cycle
### Preface
This is a practice of prediction of available bicycle numbers for every station at every hour.

### Import Data
There are four dataset,
- station: station location, dock numbers, city and built date.
- status: the available bicycle number of 70 stations in every hour from 2013-09-01 to 2015-08-31.
- trip: all trips during 2013-08-29 to 2014-09-01.
- weather: the forecast at 0 am of every single day during 2013-09-01 to 2015-08-31.

### EDA
- try to find the possible properties for the machine learning.
- city2 has the most trips, the most docks and the most average available bicycles.
- only 0.156% of the trips that crossed two cities. (consider 5 cities as indenpent?)
- 84.594% of the trip that were contributed by Subscribers.
- 87.123% of the days from Sep 2013 to Aug 2015 that were sunny.
- weak relationship between weather and available bike number.
- there are two peaks of trips during a single day, 6 am to 11 am and 4 pm to 7 pm. 
- there are fewer trips on weekends than on weekdays.
- possible parameters: weekdays/weekends, hours, dock number.

### Training/Evaluating Data
- dataset1: bikes_available, get_dummies of weekday
- dataset2: bikes_available, weekend or not
- dataset3: bikes_available, weekend or not, get_dummies of hour
- dataset4: bikes_available, weekend or not, 0 am ~ 5 am and get_dummies of hour

### Create model and Train
- Apply LSTM and Adam optimizer.
- Up to now the best performance lies on the fourth dataset4.
- Average of RMSE of train dataset 4 = 2.6060307003319294.
- Average of RMSE of test dataset 4 = 3.0373275033640366.
