📊 Crypto Analyzer Dashboard (R Shiny)
An interactive R Shiny dashboard for cryptocurrency analysis, featuring:

⚡ Near real-time price tracking

📈 Statistical forecasting

🧠 Comprehensive backtesting engine with multiple strategies

This tool integrates essential crypto analytics into a single, browser-accessible app—ideal for traders, analysts, and researchers.

🔍 Features
✅ Live Price Tracking:

Fetches data from Binance API every 30 seconds.

Displays updated prices via text and line charts.

✅ Multi-Crypto Support:

Supports popular assets including Bitcoin, Ethereum, Solana, and more.

✅ Backtesting Engine:

Daily timeframe backtests for:

Moving Average Crossover

RSI Threshold

MACD Crossover

Bollinger Bands (Breakout & Mean Reversion)

ATR Breakout

Features:

Parameter optimization

Volume confirmation filter

Configurable slippage & commission

✅ Forecasting:

Uses auto.arima from the forecast package

Fits best ARIMA model for historical data and projects future prices

✅ Advanced Visualization:

Candlestick charts with Plotly

Buy/Sell/Exit markers on strategy output

Overlay of indicators like MA and BBands

📸 Screenshots

<img width="1900" height="881" alt="{5FEE943B-17AA-4A1E-85D3-13B7CC8EAA00}" src="https://github.com/user-attachments/assets/649f3ba3-6abe-4552-8d06-d35d47354513" />


<img width="1897" height="1023" alt="{199E22AE-0FC2-4911-8ED2-4B941AAB3595}" src="https://github.com/user-attachments/assets/d835558f-4cee-4dd1-9372-44295e331bb0" />

<img width="1896" height="945" alt="{6B022E07-0FD8-4DEB-A1B1-0D18F3D5805C}" src="https://github.com/user-attachments/assets/24d5a2ab-b988-494d-8bbe-1fa048b89c3c" />

<img width="1907" height="935" alt="{806A806E-CDA1-4901-808C-5925EBC6F762}" src="https://github.com/user-attachments/assets/91ee9b28-ba8f-4cb6-b673-05af77a471e6" />

<img width="1877" height="952" alt="image" src="https://github.com/user-attachments/assets/4a9b9163-9eea-48d5-b8f7-259cd97d9a6d" />

<img width="1876" height="910" alt="image" src="https://github.com/user-attachments/assets/fce5a1bf-dd14-4226-a62a-565e5ec9afa6" />

<img width="1417" height="496" alt="{85ECE6D9-9F3C-4954-A309-2F54EF805331}" src="https://github.com/user-attachments/assets/95da1bef-6321-4ff2-ba91-1f439f8fe499" />



🧱 Tech Stack
Language: R

Core Libraries:

UI & Server: shiny, shinycssloaders

Charts: plotly, ggplot2

Time Series & Indicators: quantmod, TTR, forecast, xts

Data Handling: dplyr, lubridate, PerformanceAnalytics

API/Web: httr2, jsonlite

Storage: RSQLite, DBI

Tables: DT

Database: Local SQLite file (crypto_data.sqlite) for caching historical and live data

🛠 Installation
Install R and RStudio

Save the project file as app.R

Open app.R in RStudio

In R console, install dependencies:

r
Copy
Edit
install.packages(c("shiny", "quantmod", "forecast", "ggplot2", "dplyr", "lubridate", "xts", 
                   "httr2", "jsonlite", "RSQLite", "DBI", "TTR", "plotly", 
                   "PerformanceAnalytics", "scales", "DT", "shinycssloaders"))
Click Run App in RStudio or run manually:

r
Copy
Edit
shiny::runApp("path/to/your/app_directory")
OS Compatibility: Windows, macOS, Linux

🚀 Usage
Launch the app via RStudio or CLI.

In browser:

Choose a cryptocurrency from sidebar

Go to the Strategy Analysis tab

Select a strategy and date range

Click Run Backtest

Explore:

Candlestick charts with trade markers

Performance stats

Trade logs and optimization tables

Inputs:

Strategy selection

Parameter tuning (RSI, MA, etc.)

Commission/slippage

Crypto asset & date range

Outputs:

Live price line charts

Forecast plots

Backtest result charts

Performance and trade tables

⚙️ Configuration
No API keys required — uses public Binance & Yahoo Finance endpoints

Customizable Parameters:

In code: LIVE_REFRESH_INTERVAL, DEBUG_MODE, DB_FILE

In UI: Strategy parameters, trading costs, filters

📁 Project Structure
Single file: app.R contains everything — UI, server logic, helper functions

Database: crypto_data.sqlite auto-created to cache fetched data

🧩 Limitations
📉 Overfitting Risk: Parameter optimization may not generalize well

🌐 API Dependency: Changes to Binance or Yahoo API could break functionality

🕒 Live Data Lag: Updates only every 30 seconds (not real-time streaming)

🚧 Single-threaded: Long computations (like optimization) freeze the UI temporarily

⏱️ No Intraday Support: Backtesting and forecasting use daily OHLCV data only

🌱 Roadmap
Add advanced strategies (e.g. Ichimoku Cloud, SuperTrend)

Enable custom user-defined strategy logic

Integrate additional exchanges (Coinbase, Kraken, Bybit)

Intraday backtesting support (1h, 4h candles)

WebSocket integration for live streaming

Deployment guide for shinyapps.io or Shiny Server

Portfolio-level backtesting & rebalancing


csharp
Copy
Edit
This project is currently closed-source and not licensed for distribution.
✉️ Contact
Include your GitHub or email (optional), or leave this section out.

Let me know if you want this as a downloadable .md file or want changes like:

Making it more beginner-friendly

Adding command-line usage examples

Integrating screenshots or demo GIFs
