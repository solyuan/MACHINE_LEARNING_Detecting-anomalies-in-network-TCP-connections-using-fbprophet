Author: StatsEye - Klaudia Łubian

Date: October 2019

# Forecasting and detecting anomalies in network TCP connections using fbprophet

This repository includes Python code used for analysis of real, large data of network TCP connections coming from a large company which is used to detect anomalies in the signals' level by the means of time series forecasting.

It makes use of the *fbprophet* library. Fbprophet implements a Generalized Additive Model, and - in a nutshell - models a time-series as the sum of different components (non-linear trend, periodic components and holidays or special events) and allows to incorporate extra-regressors (categorical or continuous). The reference is [Taylor and Letham, 2017](https://peerj.com/preprints/3190.pdf), see also this [manual](https://facebook.github.io/prophet/docs/quick_start.html#python-api) from Facebook research team.

The anomalies are supposed to be detected immediately, hence I have tried to model minutely data. Fbprophet was originally built for analysis of daily data, hence as per October 2019, there is not much on the Internet about the application of Prophet to minutely data. Found this comment from Facebook's employee (https://github.com/facebook/prophet/issues/226): 
"@iamshreeram we did some experiments with sub-daily (second) data, but paused those experiments awhile ago. If I see any significant results or findings I will report them here."
This analysis proved that fbprohpet can be succesfully used to fit a model to minutely data.  

*Source code* folder includes Python code files used for: 
* loading multiple datasets containing information about connections detected over a few weeks time, and creating a summary file with counts of connections per minute. The data loaded is large, hence it was processed chunk by chunk,  
* exploring the time series, its decomposition, building and tunning forecasting model; including seasonal, holiday effects and regressors, 
* creating a framework to detect anomalies using best forecasting model. 

