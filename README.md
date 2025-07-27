📊 Crypto Analyzer Dashboard (R Shiny)
An all-in-one interactive R Shiny dashboard for cryptocurrency analysis — tailored for traders, analysts, and researchers. It offers:

⚡ Live Price Tracking

📈 Statistical Forecasting

🧠 Backtesting Engine with Strategy Optimization

All wrapped in a browser-accessible Shiny app.

🔍 Key Features
✅ Real-Time Price Tracking
Fetches price data from Binance API every 30 seconds
Displays updated prices using line charts and text panels
Auto-saves live ticks to a local SQLite database

✅ Multi-Crypto Support
Bitcoin, Ethereum, Solana, and more
Easily extendable to additional assets

✅ Backtesting Engine
Supports the following strategies:
Moving Average Crossover
RSI Threshold
MACD Crossover
Bollinger Bands (Breakout & Mean Reversion)
ATR Breakout

Includes:
Volume confirmation filter
Parameter grid search optimization
Configurable slippage and commission

✅ Forecasting
Uses auto.arima() from the forecast package
Projects future prices with confidence intervals
Configurable training window and forecast horizon

✅ Interactive Visualizations
Candlestick charts (Plotly)
Buy/Sell markers overlaid on strategy outputs
Performance metrics & trade logs

🧱 Tech Stack

| Category       | Libraries                                    |
| -------------- | -------------------------------------------- |
| Language       | R                                            |
| UI & Logic     | `shiny`, `shinycssloaders`, `DT`             |
| Charts         | `plotly`, `ggplot2`                          |
| Time Series    | `forecast`, `quantmod`, `TTR`, `xts`         |
| Data Wrangling | `dplyr`, `lubridate`, `PerformanceAnalytics` |
| API & Storage  | `httr2`, `jsonlite`, `RSQLite`, `DBI`        |


Database: crypto_data.sqlite (auto-generated for live + historical data)

🚀 Installation
1. Install R & RStudio
https://cran.r-project.org/
https://posit.co/download/rstudio-desktop/

2. Clone Repository and Open app.R
```
git clone https://github.com/shreyas70773/cryptopricetracker-live.git
```
4. Install Dependencies in R Console
```
install.packages(c(
  "shiny", "quantmod", "forecast", "ggplot2", "dplyr", "lubridate", "xts",
  "httr2", "jsonlite", "RSQLite", "DBI", "TTR", "plotly", "PerformanceAnalytics",
  "scales", "DT", "shinycssloaders"
))
```
5. Launch the App
```
shiny::runApp("path/to/your/app_directory")
```

Compatible with Windows, macOS, and Linux.

🌐 Usage Guide
🖥️ In Your Browser:
Choose a Cryptocurrency
View Live Prices on the "Live View" tab
Generate Forecasts in the "Forecast" tab
Run Backtests under "Strategy Analysis"

✅ Inputs:
Strategy & parameters (e.g., MA lengths, RSI thresholds)

Crypto asset
Date range
Commission & slippage

📊 Outputs:
Live price charts
ARIMA forecasts

Backtest results:
Candlestick with buy/sell markers
Trade logs
Performance metrics

⚙️ Configuration
Setting	Location	Description
LIVE_REFRESH_INTERVAL	app.R	Live update frequency (default: 30s)
DEBUG_MODE	app.R	Enables console logging and debug UI
DB_FILE	app.R	SQLite file path

✅ No API keys required — relies on public endpoints from Binance and Yahoo Finance.

📁 Project Structure
```
crypto-dashboard/
├── app.R               # Main Shiny app file (UI + Server)
├── crypto_data.sqlite  # Local SQLite DB (auto-generated)
```
🧩 Known Limitations
📉 Risk of overfitting when optimizing strategy parameters
🌐 Dependent on Binance and Yahoo Finance APIs
🕒 Updates every 30s — not real-time streaming
🚧 Single-threaded: heavy operations may freeze UI
⏱️ No intraday backtesting yet (daily OHLCV only)

🗺️ Roadmap
 Add advanced indicators (Ichimoku, SuperTrend)
 Enable custom strategies via UI
 Integrate more exchanges (Coinbase, Kraken)
 Support for 1h/4h candles
 WebSocket streaming for real-time charts
 Deployment support: shinyapps.io, Shiny Server
 Portfolio-level backtesting

📸 Screenshots

<img width="1900" height="881" alt="{5FEE943B-17AA-4A1E-85D3-13B7CC8EAA00}" src="https://github.com/user-attachments/assets/649f3ba3-6abe-4552-8d06-d35d47354513" />


<img width="1897" height="1023" alt="{199E22AE-0FC2-4911-8ED2-4B941AAB3595}" src="https://github.com/user-attachments/assets/d835558f-4cee-4dd1-9372-44295e331bb0" />

<img width="1896" height="945" alt="{6B022E07-0FD8-4DEB-A1B1-0D18F3D5805C}" src="https://github.com/user-attachments/assets/24d5a2ab-b988-494d-8bbe-1fa048b89c3c" />

<img width="1907" height="935" alt="{806A806E-CDA1-4901-808C-5925EBC6F762}" src="https://github.com/user-attachments/assets/91ee9b28-ba8f-4cb6-b673-05af77a471e6" />

<img width="1877" height="952" alt="image" src="https://github.com/user-attachments/assets/4a9b9163-9eea-48d5-b8f7-259cd97d9a6d" />

<img width="1876" height="910" alt="image" src="https://github.com/user-attachments/assets/fce5a1bf-dd14-4226-a62a-565e5ec9afa6" />

<img width="1417" height="496" alt="{85ECE6D9-9F3C-4954-A309-2F54EF805331}" src="https://github.com/user-attachments/assets/95da1bef-6321-4ff2-ba91-1f439f8fe499" />

📂 Example Use Cases
Here's how different users can benefit from the app:
💹 Retail Traders: Validate trading strategies like RSI or MACD crossovers before using them in real trading platforms.
📊 Quant Analysts: Forecast crypto price trends using ARIMA and run batch backtests for statistical modeling.
🎓 Researchers & Students: Use it as a sandbox to explore trading strategies, calculate risk metrics, or include visual results in academic papers.
📈 Data-Driven Investors: Identify historically high-performing strategies, analyze trade logs, and tune portfolio parameters offline.

📤 Export & Reporting
You can export most outputs directly or customize the app for deeper reporting:

Exportable Content	Format / Method
Trade Logs	Downloadable CSV via DT table
Performance Tables	Copy or customize with export buttons
Forecast Charts	Exportable via Plotly UI
Strategy Results	View or copy from optimization tables

Pro Tip: Add write.csv() or ggsave() in app.R to automate report saving.

🔌 Extensibility & Customization
This project is structured to support future development and advanced use:
➕ Add New Strategies
Implement new logic in the run_strategy() block
Add indicator calculations in the indicator engine
Update UI inputs and plotting code

🔗 Integrate Other Data Sources
Replace or supplement Binance/Yahoo API with:
CoinGecko
Alpha Vantage
Local CSVs or REST APIs

🎨 UI Theming
Add bslib or shinythemes for dark/light themes
Use custom HTML/CSS for branding or layout tweaks

🧱 Modular Codebase
Although it’s a single app.R, it can be split into:
ui.R / server.R
/modules/ for strategies and plotting
/utils/ for helpers and API calls

🧪 Testing & Validation
While the app is not bundled with unit tests, you can validate components by:
Using testthat or shinytest2 for automated tests
Verifying strategy logic on known patterns
Cross-checking forecast outputs against external models
Logging intermediate values via DEBUG_MODE = TRUE

🔐 Security Considerations
This app is read-only and client-safe by default:
No write/delete endpoints

Local SQLite database (no cloud data writes)
Uses public, anonymous APIs (no secret keys)
Input sanitization is handled for all UI fields

If deploying to a public server:

Consider rate-limiting or caching API response
Add shiny::req() and validate() checks
Set up access restrictions or authentication

🚀 Deployment Options
Although this is currently for local use, it can be deployed via:

| Platform         | Notes                                                                                     |
| ---------------- | ----------------------------------------------------------------------------------------- |
| **shinyapps.io** | Easiest hosted deployment. May need to bundle `crypto_data.sqlite` or disable DB caching. |
| **Shiny Server** | Great for intranet / self-hosting. Place app in `/srv/shiny-server/`.                     |
| **Docker**       | Build a containerized version for reliable deployment. Add `Dockerfile` and dependencies. |


❓ FAQ
🔧 Do I need Binance API keys?
No. It uses public endpoints — no authentication is required.

🔒 Licensing
This project is closed-source and not licensed for distribution.

💾 Where is the data stored?
All fetched data (live & historical) is stored locally in a file called crypto_data.sqlite.

🕒 How frequently is price data updated?
Every 30 seconds, but you can change this via the LIVE_REFRESH_INTERVAL constant.

📉 Can I add my own strategy?
Not yet — but it's on the roadmap. Future versions may allow user-defined logic or scripting via UI/code modules.

🧪 Is this suitable for real trading?
It’s designed for analysis and simulation only. While the calculations simulate real-world conditions (e.g., slippage, lag), you should not use it to execute trades directly.

🧠 What data frequency is used?
Only daily OHLCV data is used for forecasting and backtesting.

🔁 Will intraday support be added?
Yes, it's on the roadmap to support 1h and 4h candles in future updates.

🚀 How do I deploy this online?
Deployment instructions (via shinyapps.io or Shiny Server) will be added in a future version.

📬 Can I contribute?
The project is currently closed-source, but feel free to reach out for collaboration or testing opportunities.

📬 Contact
Have questions or want a demo? Reach out at:
📧 shreyassunil010@gmail.com
🌐 LinkedIn Profile : https://www.linkedin.com/in/shreyas-sunil-2a44b2321/



