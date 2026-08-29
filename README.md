# Forex Trading Bot

## About The Program
**This program is a forex trading bot that works on the popular trading platform, MetaTrader 5. It was created 
using Python to connect to the MetaTrader5 terminal and run on a personal PC. It presents one of my first attempts 
at using Python for algorithmic trading and trading bot design and implementation. It is meant to showcase a sample of 
my work in algorithmic trading and trading bot development, but I wouldn't advise using it for personal trading.**
<br>
<br>
**This bot employs a variation of a SuperTrend strategy, translated from Pinescript to Python, using 18 periods and a 
multiplicative factor of 5, which analyzes market prices for a given forex pair and specifies the buy and sell conditions 
accordingly. To be more specific, the SuperTrend indicator identifies market trends, detecting the market's up-trend 
and down-trend which are depicted as a green or red line, according to which a decision can be made about buying or selling. 
These lines are not plotted by the bot here, however they are indicated by two key variables: maximum and minimum (and average, 
corresponding to the midway point). For the current strategy, the buy condition is defined as, buy if the low price of the next to 
last candle is lower than the indicator's down-trend line; whereas the sell condition is defined as, sell if the high price of 
the next to last candle is higher than the indicator's up-trend. The bot provides ongoing monitoring of market trends on each 
candle update for a given forex pair based on a prespecified timeframe and executes a buy/sell order if a buy/sell condition is met.**
<br>
<br>
**The program is split into 4 Python files, the main program script, 'Forex Trading Bot.py', and three additional scripts, each 
containing custom functions that are specialized for a particular type of task: 'DataProcessing.py', which contains the bot's 
indicator function for processing, analyzing, and identifying market trends; 'OrderProcessing.py', which is particularly 
specialized for processing market orders, covering custom functions for calculating the lot size for a given trade, stop 
loss and take profit values, and functions for executing buy and sell orders; and, 'TimeProcessing.py', which is specialized 
for time-related processes, such as monitoring market opening and closing times, monitoring and signalling the start of a new 
candle update for a given pair to begin analyzing its candles, and specifying the timeframes for trading.**
<br>
<br>
**This bot is designed to trade on multiple forex pairs simultaneously with different trading time frames, currently containing 26 pairs 
in total, each has its own trading timeframe. They are presented as a tuple of lists, each list containing the pair's name on MetaTrader,
the timeframe for trading on it, and a boolean value indicating the presence or absence of a new candle update for that given pair based on 
that particular timeframe. As such, each forex pair is processed and analyzed separately based on its own unique, prespecified trading 
timeframe. You can add or remove a pair from the tuple, or change the timeframe for any given pair. With a little tinkering, this bot can 
also trade on stocks and crypto, depending on the type of broker.**
<br>
<br>
**Finally, this bot is highly dynamic and responsive with multiple nested loops to control for: market open/close time, internet connection 
problems, order execution problems, high increases or decreases in the account balance, among others, and adjusts its behaviour accordingly. In 
this way it can confront and meet many different challenges automatically without intervention from the user.** 

<br>

**Overall, the bot performs the following tasks:**
 - **Checks if the forex market is open** <br>
 - **Connects to metatrader5 terminal and logs in to personal account** <br> 
 - **Checks if the internet is connected** <br>
 - **Iterates over forex pairs and collects candlesticks with open, high, low, and close prices for a given pair** <br>
 - **Applies the strategy or indicator to analyze the pair's candlesticks and identify its market trends** <br>
 - **Specifies the buy and sell conditions based on the indicator's analysis** <br>
 - **Executes a buy or sell order if the conditions are met** <br><br>
*It's also provided with a function that checks whether the data of a given pair was analyzed and prevents processing the same candlestick twice for a given timeframe*



