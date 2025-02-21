# Technical Analysis Backtesting

## Description
This project implements a backtesting framework for various technical analysis indicators, including RSI, EMA, and SMA. The script allows users to evaluate trading strategies based on these indicators using historical stock price data.

## Features
- Backtesting for RSI-based trading strategies.
- Backtesting for EMA and SMA crossover strategies.
- Automated retrieval of stock data using Yahoo Finance (optional).
- Data visualization for technical indicators.

## Installation
Ensure that Python and the required libraries are installed. The following packages are required:
- `pandas`
- `numpy`
- `matplotlib`
- `ta`
- `yfinance` (optional)

Install dependencies using:
```bash
pip install ta pandas numpy matplotlib yfinance
```

## Usage

### 1. Load Historical Data
The script allows loading stock price data from a CSV file:
```python
df = pd.read_csv('/content/HistoricalData_1740111227348.csv').set_index('Date')
```
Alternatively, stock data can be retrieved from Yahoo Finance:
```python
import yfinance as yf
df = yf.download("AAPL", start='2025-02-20')['Close']
```

### 2. Compute Technical Indicators
The script calculates key technical indicators:
```python
RSI_14 = RSIIndicator(price, window=14).rsi()
EMA_14 = EMAIndicator(price, window=14).ema_indicator()
SMA_14 = SMAIndicator(price, window=14).sma_indicator()
```

### 3. Run Backtests
The framework supports backtesting of RSI, EMA, and SMA strategies:
```python
backtest_indicator(10_000, price, RSI_7, indicator_type="RSI", buy_level=30, sell_level=70)
backtest_indicator(10_000, price, EMA_7, indicator_type="EMA")
backtest_indicator(10_000, price, SMA_7, indicator_type="SMA")
```

### 4. Visualize Indicators
Price and technical indicators can be visualized using:
```python
plot_indicator(price, RSI_14, indicator_type="RSI")
plot_indicator(price, EMA_14, indicator_type="EMA")
plot_indicator(price, SMA_14, indicator_type="SMA")
```

## Data Sources
- CSV file (local storage)
- Yahoo Finance Package (optional)

## Contributing
Contributions are welcome. To contribute:
1. Fork the repository.
2. Create a feature branch (`git checkout -b feature-branch`).
3. Commit your changes (`git commit -m "Add new feature"`).
4. Push the branch (`git push origin feature-branch`).
5. Open a Pull Request.

## License
This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Contact
For questions or suggestions, feel free to reach out or open an issue in the repository.
