# RawDataDownloader
Program that pulls raw asset price data from Yahoo Finance, applies common indicators, and exports a clean dataset to Excel for analysis, research, and strategy development.

# Note
Python 3.10.11

# Libraries
yfinance
pandas
numoy

#functionality
This tool (the RawDataDownloader) is designed to download price history for a financial asset from Yahoo Finance and prepare that data for analysis in a spreadsheet.

1. The DataDownloader.py file is the main script you will run, and edit.
2. Specify the asset you want to perform an analysis on
     -> In the code, find the line that sets "ticker" (e.g., "TSLA").
     -> Replace the default ticker with the exact symbol of the asset you are trying to analyze (e.g., "AAPL" for Apple, "ETH-USD" for Ethereum).
3. Choose the time interval (bar size), and the appropriate date range. 
     -> If you have a specific time range in which you want to analyze your desired asset with (minute, hour, daily, weekly, monthly, yearly) then you will need       to specify that where it says interval="1W" (Change the default time range with your desired time range, and follow the same format that was previously      listed, if you need more context:
     "1H" -> Hourly data
     "1D" -> Daily data
     "1W" -> Weekly data
      What will happen is after you clarify the the time interval, the program will go ahead and download raw data with a timestamp at that exact frequency.

     # IMPORTANT
     When you are clarifying the time range for the specific frequency you desire, please remember to change the start_date, and the end_date

     #Reference
     | Interval                              | How far back you *can* realistically retrieve data |
| ------------------------------------- | -------------------------------------------------- |
| **1-minute (`1m`)**                   | ~7 days max history                                |
| **2-minute (`2m`)**                   | ~60 days max history                               |
| **5-minute (`5m`)**                   | ~60 days max history                               |
| **15-minute (`15m`)**                 | ~60 days max history                               |
| **30-minute (`30m`)**                 | ~60 days max history                               |
| **60-minute / 1 hour (`60m` / `1h`)** | ~2 years (≈ 730 days)                              |
| **90-minute (`90m`)**                 | ~2 years (similar to 1h, since it’s hourly-level)  |
**| Interval              | How far back history is available |
| --------------------- | --------------------------------- |
| **Daily (`1d`)**      | Many years of history             |
| **5-day (`5d`)**      | Many years of history             |
| **Weekly (`1wk`)**    | Many years of history             |
| **Monthly (`1mo`)**   | Many years of history             |
| **Quarterly (`3mo`)** | Many years of history             |

# Important Details

The limitation only applies to intraday intervals (like 1m, 5m, 15m, etc.) because minute‑level and short time bars require a huge amount of storage and Yahoo only keeps recent history for those.
For daily and longer intervals, Yahoo’s historical data goes back to the early trading history of an asset and for many companies this is several decades.

4. Make sure you install the requirement.txt, this contains the necessary libraries you'll need for this program
   -> If you decide not to install the libraries, this program will not work at all because the main function of DataDownloader.py relies on the libraries such as yfinance, pandas, and numpys to work.



