# City-Learn-AI-Crowd
The CityLearn Challenge 2023 addresses this multi-faceted nature of advanced control in buildings by blending the challenges of control algorithm design, forecast quality and grid-resilience. The CityLearn Challenge 2023 presents a control track as done in previous challenges as well as introduces an independent forecast track where, both tracks are run in parallel and utilize the same dataset.

In this forecast track, participants will design regression models to predict the 48-hour-ahead end-use load profiles for each building in a synthetic single-family neighborhood as well as the neighborhood-level 48-hour-ahead solar generation and carbon intensity profiles.

# Problem Statement

In the forecast track, participants are to develop regression prediction models for forecasting building loads, grid carbon intensity and solar generation. The forecasts should be provided at each time step for the following 48 time steps. The variables to be predicted are: 

## BUILDING-LEVEL
Cooling Load (kWh)
DHW Load (kWh)
Equipment Electric Power (kWh) (a.k.a. non-shiftable load)
where each variable is forecasted for each building.

## NEIGHBORHOOD-LEVEL
Carbon Intensity (kgCO2e/kWh)
Solar Generation (W/kW)
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
