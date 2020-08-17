# Discord Robinhood Stockbot
### Discord stock bot that utilizes an unofficial Robinhood API (robin_stocks) and discord API for market enthusiasts. 

### Discord commands:

Command prefix = '.'

#### Price checker - provide ticker names to receive the current price quickly. Condensed to allow mobile users to view it on one line. 
***********
    Ex: .p (arg1)
    EX: .p (arg1), (arg2), ... (argN)

    [during market hours]
    .p estc aapl msft spy 
    ESTC:   $92.18  +0.78% |L: 91.40   H: 93.59
    AAPL:  $458.91  -0.16% |L: 455.86  H: 464.36
    MSFT:  $209.88  +0.47% |L: 208.91  H: 211.19
    SPY:   $338.00  +0.34% |L: 336.85  H: 338.34

    [during after hours]
    .p estc aapl msft spy
    ESTC:   $91.47  +0.34% |AH: $91.47    +0.0%
    AAPL:  $459.63  -0.19% |AH: 459.29   -0.07%
    MSFT:  $210.22  +0.63% |AH: 208.82   -0.05%
    SPY:   $338.14  +0.39% |AH: 336.63   -0.07%

#### Portfolio status - check the current balance of the signed in user's portfolio. Currently set to ONLY allow the discord account associated with the ROBINHOOD_USER_ACCOUNT use this command. 
***********
    Ex: .port 

    .port 
    Current Balance: $87239.96    +2,225.16    +2.62%
    Buying power: $13,242.81
    Option positions:
### Features:

#### Background Loop - Displays SPY ticker price every 15m between market hours. Not displayed before or after, as well as not on weekends or holidays. 


### Initial build

- [x] Connect to pyrh
- [x] Create a discord bot
- [x] Have the discord bot output something onto discord.
- [x] Discord bot use pyrh to output something.
- [x] Create a discord command "priceCheck" that triggers on '.p'. Should output the ticker, current price, and percentage difference since market open. 
- [x] Create a discord command "priceCheckList" that triggers on '.pp'. Performs "priceCheck" on a list of tickers. Produces output in a single message. 
- [x] Implement eastern time for hours, minutes, day.
- [x] Create a background loop, when the bot starts up it will print out the SPY price to a channel and the console with a timestamp every 15m during market hours.
- [x] Have background loop account for holiday days (do not post any automatic stock messages on holidays)


### Next steps

- [x] Allow priceChecker to differentiate the current time to output different results depending on if market is open or not. If market is closed, it should outprint the open price, close price, percent difference, after hours price, and percent difference since market close. 
- [ ] Add an additional condition check to priceCheck/priceCheckList to validate if the ticker exists. Currently an alphabetical combination of 1-4 characters is allowed, a stock such as TVIX can cause an exception to pop. 
- [ ] Begin adding technical analysis to certain stocks (SPY, AAPL, MSFT, AMZN) and shoutout to the channel any extremities. 

