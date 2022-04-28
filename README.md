# SergiosBot: 
## containing the data used by PotBot: a CNNLSTM network to forecast bitcoin price. 

* investment_data.csv = contains the current amount of euro invested
* holding.csv = contains the current amount of euro not invested
* previous_prices.csv = contains the previous bitocin prices rescaled via MinMax scaler to the date 2021-03-04
* predicted_prices = contains the predicted hourly prices generated by the CNN-LSTM

Every hour the bot connects to Bitstamp and retrieves the current (closing) bitcoin/eur price and stores it to 
make a prediction using its ensemble CNN-LSTM. The prediction and other state variables are then fed to the bot itself which decides 
whether to withold the amount or keep the investment. 

## The Oracle

Sergiosbot's brain consists of two parts: 

* A CNN-LSTM called "Oracle". 
* A trading bot called PotBot. Potbot takes as inputs a series of parameters to decide whether to hold or sell. At this time its decision is made if the predicted price for the next hour is at least 2% different from the current. 

![My animated logo](robot-line.svg)
