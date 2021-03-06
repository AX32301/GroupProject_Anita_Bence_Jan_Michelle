# Monte Carlo Simulation of Stock Prices

###### Authors:
Anita Xhemaili 17-610-296 <br/>
Bence Szij 21-603-394 <br/>
Jan Lörtscher 19-615-905 <br/>
Michelle Nestola 19-614-650 <br/>

The programme can be found in ***Code*** and must be executed on the user's own device. <br/>

## Code Description:
This program simulates future stock prices for a user-defined ticker.<br/>
A chart of the simulated paths & an Excel file containing the data will be saved on the user's device.<br/>
Before running the Code please make sure the following packages are installed: yfinance, pandas, datetime, numpy, matplotlib.pyplot, math <br/>
<br/>
The programme is illustrated on the Tesla example with the following input parameters: ticker TSLA, start date 2020-01-01, forecast horizon 180 days, number of simulations 100
<br/>
#### Part 1 - Requesting and checking input data:
Gathering user inputs: 
The user has to specify the ticker, the starting date for the estimation of mean historical returns & volatility, the forecast horizon(T) and the number of simulations (simruns). <br/>
The user inputs get checked for correct format. In case of an error, the input request is repeated.<br/>
Apart from all other input variables, the ticker variable is checked by the yfinance formula. In case of an invalid ticker, an error will be displayed.<br/>
At the end of Part 1 some core variables are calculated. For example, historical data for the specified ticker is gathered from Yahoo Finance, or daily stock returns are calculated. <br/>
#### Part 2 - Monte Carlo Simulation of stock price paths:
In the simulation, the outer loop(x) initiates the different simulations and the inner loop(y) calculates the daily future values. <br/>
The stock prices are modelled according to the Geometric Brownian Motion (GBM): <br/> ![GeometricBrownianMotion Formula](/GBM.PNG)
<br/>
#### Part 3 - Saving the simulation chart locally:
The figure containing the stock price simulations is displayed and saved locally as a plot.<br/>
This is an example of such a figure for the Tesla simulation: <br/>
![SimulationChart Tesla](/SimulationChart.png)
<br/>
#### Part 4 - Saving the simulated stock prices locally in an Excel file:
The expected value of the stock at day T as the mean of all simulated final values is calculated. <br/>
Furthermore, a dates-column is added to the output table. <br/>
Lastly, the output table is saved locally as an Excel file, such that the simulated stock prices can be used for further analyses. <br/>
This is an example of such an output table for the Tesla simulation: <br/>
![SimulationTable Tesla](/SimulationTable.jpeg)
<br/>
## Sources:
Geometric Brownian Motion (lecture notes of the course 'Derivatives' at University of St. Gallen):<br/>
Ammann, M. (2022). *4. Black-Scholes* [PDF slides]. University of St. Gallen, Derivatives. Canvas: https://learning.unisg.ch

Some theoretical background:<br/>
Guan, B. T. (2021, September 19). *Simulating Random Walk of Stock Prices with Monte Carlo Simulation in Python*. Medium. https://medium.com/the-handbook-of-coding-in-finance/simulating-random-walk-of-stock-prices-with-monte-carlo-simulation-in-python-6e233d841e <br/>
Harper, D. R. (2022, January 21). *How to Use Monte Carlo Simulation With GBM*. Investopedia. https://www.investopedia.com/articles/07/montecarlo.asp
