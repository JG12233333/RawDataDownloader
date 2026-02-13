# OVERVIEW

The RawDataDownloader is a Python tool for downloading historical price data from Yahoo Finance and preparing it for spreadsheet-based analysis.
All core functionality lives in DataDownloader.py, which is the file you will run and modify

# REQUIREMENTS

Python 3.10.11

Libraries:
yfinance
pandas
numpy

These libraries are important for the functionality of the program, they are located in the requirements.txt file of the project directory, do not forget to install them before running the DataDownloader.py file!

# INSTRUCTIONS

1. Replace the default asset in the DataDownloader.py file with your desired asset you wish to analyze
   Default: ticker = "TSLA"
   If you wanna analyze apple
   ticker = "AAPL"
   If you wanna analyze Bitcoin
   ticker = "BTC-USD"
   This will most certaintly work for any asset as long as it is a valid listed asset on yahoo finance.

2. Set the time interval, and analysis length.
   Find the line interval = "1W" (default) and replace it with the interval you want to analyze
   "1m" = 1 minute bars
   "5m" = 5 minute bars
   "15m" = 15 minute bars
   "1H" = 1 hour bars
   "1D" = daily bars
   "1W" = weekly bars
   "1MO" = monthly bars

   The program should download raw data at this exact frequency with OHLC/Timestamps, and other values you desire (make sure you specify what other "values" you want included in the raw data, for instance, RSI values, MA values... etc).

3. Set the Date Range
   The date range must be updated in the files, and the way that the date ranges work is
   start_date = "YYYY-MM-DD"
   end_date = "YYYY-MM-DD"

   Intraday Data Limits
   1m = 7D of max history
   2m = 60D of max history
   5m = 60D of max history
   15m = 60D of max history
   30m = 60D of max history
   1H = 2 years max history
   90M = 2 years of max history
   1D - 3M = Decades of price data (varies per asset)

The intraday data limits exist (1m - 1h) due to requirement of massive storage, so Yahoo finance only keeps recent history. Daily, weekly, and monthly data go back decades, it just depends on the exact asset. 


# IMPORTANT NOTES

You need to install all the libraries in requirements.txt before running this script.
DataDownloader.py relies heavily on yfinance, pandas, and numpy and if you don't install these, DataDownloader.py will not work. 
After setting your asset, interval, and date range, you need to run DataDownloader.py to generate your raw data, once the raw data is generated, the output of DataDownloader.py will result in a CSV file in the project directory. 
