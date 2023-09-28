# City-Learn-AI-Crowd

![ForeCastTrackimg](https://github.com/UKVeteran/City-Learn-AI-Crowd/assets/39216339/30d2a0d9-dc47-4c6b-934e-f4872fa28144)


The CityLearn Challenge 2023 addresses this multi-faceted nature of advanced control in buildings by blending the challenges of control algorithm design, forecast quality and grid-resilience. The CityLearn Challenge 2023 presents a control track as done in previous challenges as well as introduces an independent forecast track where, both tracks are run in parallel and utilize the same dataset.

In this forecast track, participants will design regression models to predict the 48-hour-ahead end-use load profiles for each building in a synthetic single-family neighborhood as well as the neighborhood-level 48-hour-ahead solar generation and carbon intensity profiles.

# The Dataset
Six csv files:
1) Building_1 <br>
2) Building_2<br>
3) Building_3 <br>
4) carbon_intensity <br>
5) pricing <br>
6) weather 

# Robust-Scaled Dataset
Six csv files:
1) scaled_b1 <br>
2) scaled_b2 <br>
3) scaled_b3 <br>
4) scaled_cint <br>
5) scaled_pr <br>
6) scaled_weat 


## Resultant Dataset
Concat 
1) scaled_b1 <br>
2) scaled_b2 <br>
3) scaled_b3 <br>
4) scaled_cint

# Problem Statement
In the forecast track, participants are to develop regression prediction models for forecasting building loads, grid carbon intensity and solar generation. The forecasts should be provided at each time step for the following 48 time steps. The variables to be predicted are: 

## BUILDING-LEVEL
1) Cooling Load (kWh)<br>
2) DHW Load (kWh)<br>
3) Equipment Electric Power (kWh) (a.k.a. non-shiftable load)<br>
where each variable is forecasted for each building.

## NEIGHBORHOOD-LEVEL
1) Carbon Intensity (kgCO2e/kWh)<br>
2) Solar Generation (W/kW)<br>
where each variable is forecasted for the entire neighborhood.

# The Metric
The forecast track score, ScoreForecast, is the average over all of the variables being forecast, of the normalised mean root mean square error (RMSE) of the forecasts made.

<img width="427" alt="Screenshot_2023-08-21_at_20 07 07" src="https://github.com/UKVeteran/City-Learn-AI-Crowd/assets/39216339/ce325f91-3e04-4db8-9e9a-cb8d6f0b67c9">

where:

t: Environment time step index; <br>
n: Total number of time steps, t, in 1 episode;<br>
τ: Forecasting window time step index;<br>
w: Length of forecasting window (48hrs);<br>
b: Total number of buildings;<br>
v: Forecasting variable;<br>
V: Total number of variables to forecast (3b + 2);<br>
ft,τv: Forecast of variable v for time step t+τ, made at time t.
