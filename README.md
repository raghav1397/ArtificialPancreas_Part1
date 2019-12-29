# ArtificialPancreas_Part1

PART A - FEATURE SELECTION

For the given time series we have selected six features -
1. Time interval between lowest cgm glucose value and corresponding bolus input
2. CGM trend analysis
3. Polynomial fit
4. Entropy
5. Acceleration (Second derivative of the cgm glucose curve)
6. ARIMA

PART B - EXPLANATION

1. Time interval between lowest cgm glucose value and corresponding bolus input
This feature gives us a range of values between which we can expect a person to take his
lunch.

2. CGM trend monitoring
This feature gives us an insight as to how effective the entire process has been to the patient. We have utilised the CGM’s data and we try to analyse the current trend in which the values are dispersed. Observing this feature will give us an insight that the patient is doing normally and the treatment is being carried out without any hiccups. Any abnormality in the graph will immediately call for medical attention. Further applications of this feature include prediction of any potential anomalous behaviour with the current data as a training set.

3. Polynomial Fit
To capture the behavior of the time series as a whole, we need a feature which summarizes the behavior of the data i.e the curve which best fits the time series data points. The polynomial fit also allows us to interpolate data based on the given data values and establishes a linear/non-linear relationship between independent variable(time) and dependent variable (glucose values). After getting the polynomial, we extract its coefficients and use them as our features.
   
 4. Entropy
Entropy captures the complexity of the data. The sample entropy feature measures the amount of regularity and unpredictability of fluctuations over the data.

5. Acceleration (Second derivative of the cgm glucose curve)
We are taking Second Derivative to find the acceleration of the glucose rate. If the second derivative is positive at a random point then the graph is concave up. If the second derivative is positive at a crucial or critical point, then the point is said to be a local minimum. If the second derivative is negative at a random point then the graph is said to be concave down. If the second derivative is negative at a crucial or critical point, then the point is a local maximum. The second derivative will be zero at an inflection point. 

6. ARIMA
As we cannot use ARIMA model on constantly varying graph. We make the graph stationary and then we apply ARIMA model. The model helps us to predict the meal intake time. If the model has good Autocorrelation and if the predicted value of the model best fits our actual graph, we can say that we can use this model to find the intake of the meal. We have a threshold value for the change in calories. If the calculated value crosses it, then we say that a meal has been taken at that time. The accuracy and efficiency depends on the model.
 
