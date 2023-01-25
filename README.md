# Oanda-trading-bot
Here is an example of a simple trading bot that uses the Oanda API to trade the USD/EUR pair using C++.

This C++ script uses the OANDA API and the cpr library to implement a simple trading bot that trades the USD/EUR pair.
It starts by including the necessary libraries, iostream and cpr, and defining two global variables account_id and access_token which are required to access the OANDA API. These values need to be replaced with your own account id and access token that you can obtain from your OANDA account.

The main() function starts by fetching the current exchange rate for the USD/EUR pair by making a GET request to the OANDA API, using the cpr library. This request includes the account id and the access token in the header to authenticate the request. The current rate is then stored in the variable rate.

Then, the script defines the trading strategy by setting the buy and sell thresholds as 90% and 110% of the current rate, respectively.

Then, it gets the current balance of the account by making another GET request to the OANDA API, using the cpr library. This request also includes the account id and access token in the header. The balance is then stored in the variable balance.

Then, the script checks if the current rate is below the buy threshold. If it is, it calculates the number of units to buy by dividing the balance by the rate and places a buy order by making a POST request to the OANDA API, using the cpr library. The request includes the account id, access token, the number of units to buy, the side of the order(buy), the instrument (EUR_USD), and the type of order (market) in the body of the request. It then prints the message "Bought [units] units at [rate]"

Then, the script checks if the current rate is above the sell threshold. If it is, it places a sell order by making another POST request to the OANDA API, using the cpr library. The request includes the account id, access token, the number of units to sell, the side of the order(sell), the instrument (EUR_USD), and the type of order (market) in the body of the request. It then prints the message "Sold [units] units at [rate]"

Finally, the script ends with the return statement.

Please note that this is just an example, and there are many other factors to consider when building a trading bot. Also, you should always do your own research before doing any trading.
