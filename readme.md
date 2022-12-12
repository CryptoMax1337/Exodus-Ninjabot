

 fast cryptocurrency trading bot framework implemented in Go. Ninjabot permits users to create and test custom strategies for spot markets. 
| DISCLAIMER                                                                                                                                                                                                           |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| This software is for educational purposes only. Do not risk money which you are afraid to lose.  USE THE SOFTWARE AT YOUR OWN RISK. THE AUTHORS AND ALL AFFILIATES ASSUME NO RESPONSIBILITY FOR YOUR TRADING RESULTS |

## Examples of Usage

Check [examples](examples) directory:

- Paper Wallet (Live Simulation)
- Backtesting (Simulation with historical data)
- Real Account 


**Example of usage**
```bash
# Download candles of BTCUSDT to btc.csv file (Last 30 days, timeframe 1D)
ninjabot download --pair BTCUSDT --timeframe 1d --days 30 --output ./btc.csv
```

### Backtesting Example

- Backtesting a custom strategy from [examples](examples) directory:
```
go run examples/backtesting/main.go
```

Output:

```
INFO[2022-10-16 16:34] [SETUP] Using paper wallet                   
INFO[2022-10-16 16:34] [SETUP] Initial Portfolio = 10000.000000 USDT 
+---------+--------+-----+------+--------+--------+-----+----------+-----------+
|  PAIR   | TRADES | WIN | LOSS | % WIN  | PAYOFF | SQN |  PROFIT  |  VOLUME   |
+---------+--------+-----+------+--------+--------+-----+----------+-----------+
| BTCUSDT |     14 |   6 |    8 | 42.9 % |  5.929 | 1.5 | 13511.66 | 448030.04 |
| ETHUSDT |      9 |   6 |    3 | 66.7 % |  3.407 | 1.3 | 21748.41 | 407769.64 |
+---------+--------+-----+------+--------+--------+-----+----------+-----------+
|   TOTAL |     23 |  12 |   11 | 52.2 % |  4.942 | 1.4 | 35260.07 | 855799.68 |
+---------+--------+-----+------+--------+--------+-----+----------+-----------+

-- FINAL WALLET --
0.0000 BTC = 0.0000 USDT
0.0000 ETH = 0.0000 USDT
45260.0734 USDT

----- RETURNS -----
START PORTFOLIO     = 10000.00 USDT
FINAL PORTFOLIO     = 45260.07 USDT
GROSS PROFIT        =  35260.073380 USDT (352.60%)
MARKET CHANGE (B&H) =  407.09%

------ RISK -------
MAX DRAWDOWN = -11.76 %

------ VOLUME -----
ETHUSDT         = 407769.64 USDT
BTCUSDT         = 448030.04 USDT
TOTAL           = 855799.68 USDT
COSTS (0.001*V) = 855.80 USDT (ESTIMATION) 
-------------------
Chart available at http://localhost:8080

### Features:

- [x] Live Trading
  - [x] Custom Strategy
  - [x] Order Limit, Market, Stop Limit, OCO

- [x] Backtesting
  - [x] Paper Wallet (Live Trading with fake wallet)
  - [x] Load Feed from CSV
  - [x] Order Limit, Market, Stop Limit, OCO

- [x] Bot Utilities
  - [x] CLI to download historical data
  - [x] Plot (Candles + Sell / Buy orders, Indicators)
  - [x] Telegram Controller (Status, Buy, Sell, and Notification)
  - [x] Heikin Ashi candle type support
  - [x] Trailing stop tool
  - [x] In app order scheduler




