#  Public Transport Service-wise Forecasting Report

## 1. Overview
This report presents the forecasting of public transport ridership for each service type for the next seven days.  
The dataset contains daily passenger journeys from **2019 to 2024**, spanning multiple services such as **Local Route, Light Rail, Peak Service, Rapid Route, School, and Other**.  
The goal of this analysis was to design a simple yet interpretable predictive model that captures **weekday and weekend travel behavior**.

---

## 2. Algorithm Chosen
To account for weekly behavioral differences, **two separate Linear Regression models** were trained for each transport service —  
one using **weekday data (Monday to Friday)** and the other using **weekend data (Saturday and Sunday)**.  
This method allows the model to capture realistic travel variations between workdays and weekends without introducing the complexity of seasonal time-series models.

---

## 3. Model Parameters
Below are the key parameters used in the forecasting process:

- **Algorithm:** Linear Regression (scikit-learn)  
- **Input Feature:** Day Index (numerical representation of each date)  
- **Target Variables:** Ridership counts for each service type  
- **Separate Models:** One model for weekdays and another for weekends per service  
- **Forecast Horizon:** 7 days beyond the last recorded date  

---

## 4. Forecast Behavior and Insights
The forecasts for each service type indicate **stable weekday ridership** and **significant drops during weekends**.  
Among all services, **Rapid Route** continues to be the most used, while **Peak Service** records the lowest ridership.  

- Predicted weekday ridership values: *~13,000 – 16,000* (main services)  
- Predicted weekend ridership values: *~3,000 – 7,000*  

These trends align with historical data patterns where weekday demand exceeds weekend demand.

---

## 5. Limitations and Future Scope
While separate Linear Regression models for weekdays and weekends effectively capture general patterns,  
they are limited in modeling **complex nonlinearities and seasonal cycles**.  

For long-term or more dynamic forecasting, advanced models such as **SARIMA, Prophet, or LSTM** could be explored to incorporate:  
- Multi-seasonal patterns  
- External factors such as weather, holidays, or fare changes  

---
