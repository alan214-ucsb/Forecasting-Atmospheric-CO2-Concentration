# Forecasting-Atmospheric-CO2-Concentration

## Abstract

As a greenhouse gas, carbon dioxide (CO2) is one of the driving forces behind global warming. Since the beginning of the industrial revolution, atmospheric CO2 levels have risen more than 40% and give no indication of slowing down. This project utilizes seasonal autoregressive integrated moving average (SARIMA) models to accurately forecast atmospheric carbon dioxide concentrations 10 months into the future. It is our hope that these forecasts may be useful for anticipating other meteorological phenomena, such as catastrophic weather events and global temperature rises.

## Introduction

Global warming is perhaps the greatest problem facing future generations. One of the largest contributing factors to global warming is atmospheric carbon dioxide. Since the effects of global warming are widespread and catastrophic, it is important to accurately predict how atmospheric CO2 levels will change into the future. The goal of this paper is to forecast monthly atmospheric carbon dioxide concentration by utilizing the Box-Jenkins methodology to fit an appropriate SARIMA model. Our efforts were successful, and our results indicate that atmospheric CO2 concentrations can be accurately forecasted 10 months into the future.

### About the Data

The models in this project were trained from monthly mean atmospheric carbon dioxide concentrations measured in parts per million. The data were collected at the Mauna Loa Observatory in Hawaii, beginning in March 1958. These data are publicly available and freely distributed by the National Oceanic & Atmospheric Administration in accordance with their Global Greenhouse Gas Reference Network. The data table used in the project is available at the NOAA website.

### Software Used in Analysis

All statistical analysis performed in this project was done with the RStudio integrated development environment. In addition to base R, the following software libraries were used: MASS, stats, tseries, and forecast. Please note that `forecast::Arima()` was used instead of `stats::arima()`. According to the creator of the forecast package, Rob J Hyndman, `Arima()` provides a more robust framework to forecast differenced data than that provided by `stats::arima()`.

## Results

Using SARIMA models, we conclude that atmospheric CO2 concentrations can be accurately forecasted.

## Summary of Analysis

We begin the project by loading our data in R. We first remove the last 10 observations for comparison against our forecasts. Next, we begin conducting exploratory analysis of the data and discover that it requires a transformation to stabilize variance and differencing to remove trend and seasonality. We perform this transformation and differencing, yielding a stationary time series. Next, we examine the autocorrelations (ACF) and partial autocorrelations (PACF) of the stationary series to identify appropriate models. After constructing two potential models, we conduct model diagnostic checking to make sure each meets the assumptions of SARIMA. Finally, we choose a 'best' model and use it to forecast ten future observations. These forecasts are compared against the 10 observations we reserved in the beginning in order to evaluate model performance.
