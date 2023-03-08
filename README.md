# Commodity Portfolio Seasonal Analysis

The code is designed to analyze the seasonal patterns of historical data of a particular financial asset, such as a commodity, and determine the optimal times to buy and sell the asset based on long-term trends in the market.

The first step in the code is to calculate the 15-year and 5-year seasonal averages of the asset's price movements. These averages are calculated based on the asset's historical performance over the specified time periods, taking into account any seasonal trends or fluctuations that may occur.

Next, the code identifies the longest streaks of price movements in the same direction, whether up or down, that occur within the 15-year and 5-year timeframes. This information is used to determine the optimal times to buy and sell the asset based on the strength and duration of these streaks.

The program creates a `nextTrade` dataframe that houses the best trades to make given the seasonal tendencies over the past 15 and 5 years. It is set to look for streaks that produce a profit at least 70% of the time with a sharpe ratio of at least 0.7.

By using these long-term trends and streaks to inform buying and selling decisions, the code aims to maximize profits and minimize losses for investors who are looking to make informed decisions based on historical data and market trends.

# Installation
- Clone the repo to your computer
- Install the necessary requirements (and possibly create a virtual environment depending on your software package) by doing:
  - `pip install -r requirements.txt`

# Usage
- Modify the `folder_path` on line 195 of the last notebook entry from `folder_path = "E:/path/of/your/choice/" + ...` to the file folder where you have downloaded the repo
- Run Commodity_Portfolio_Seasonal_Analysis.ipynb in a Python IDE
- It will create a folder for the seasonal period you wish to analyze and inside you will find:
  - The `nextTrade_"start"_"end".csv`, a log of trades that would have been used in the end year.
  - The `seasonality_"start"_"end".csv`, a log of all the seasonal trends of each commodity in the portfolio.
  - A `"ticker"_seasonality.html`, which should be opened in a browser, for each commodity that shows the 15 and 5 year averages, their 20 day moving averages and the end year price change history to make analyzing the PnL visually simple.

# Extending this
If you would like to extend this work, here are a few places to start:
- Determine a better entry system than longest positive/negative streaks
  - Examples: Trend Following, Mean Reversion, Spread History, etc.
- Explore using Machine Learning by providing the 15 and 5 year averages as features to the model
- Add different assets to the portfolio to find ones that are more consistent
- Add a way to backtest the nextTrade results at the portfolio level to see how this sytem would have done over time
- Create a heatmap of monthly returns each year to compare to the average to better asses outlier years that may be influencing the model too heavily
