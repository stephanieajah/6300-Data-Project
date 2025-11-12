# Stock Price Forecasting of Top Technology Companies Using Market Data and News Sentiment Analysis

## Project Overview

This project implements a comprehensive big data analysis system for forecasting stock prices of top technology companies using multi-source data integration, sentiment analysis, and machine learning models. The system combines historical stock prices, technical indicators, news sentiment, social media sentiment, macroeconomic factors (forex rates, commodity prices, inflation, treasury rates), and market performance metrics to predict future stock prices.

## Companies Analyzed

- **AAPL** (Apple Inc.) - IPO: 1980-12-12
- **AMZN** (Amazon.com Inc.) - IPO: 1997-05-15
- **GOOG** (Google/Alphabet Inc.) - IPO: 2004-08-19
- **META** (Meta Platforms Inc.) - IPO: 2012-05-18
- **MSFT** (Microsoft Corporation) - IPO: 1986-03-13
- **NVDA** (NVIDIA Corporation) - IPO: 1999-01-22

## Project Structure

```
Big Data Project/
│
├── data_pulling_joining.ipynb          # Main data collection and preprocessing notebook
├── stock_price_data.py                  # Script for pulling stock price data
├── merging_technical_indicator_companywise.py  # Script for merging technical indicators
├── api.env                              # API keys configuration (not included in repo)
│
├── Stock_Price_Data/                    # Historical stock price data
│   ├── AAPL_stock_prices.csv
│   ├── AMZN_stock_prices.csv
│   ├── GOOG_stock_prices.csv
│   ├── META_stock_prices.csv
│   ├── MSFT_stock_prices.csv
│   └── NVDA_stock_prices.csv
│
├── raw_news_data/                       # Raw news articles data
│   ├── AAPL_news_data.csv
│   ├── AMZN_news_data.csv
│   ├── GOOG_news_data.csv
│   ├── META_news_data.csv
│   ├── MSFT_news_data.csv
│   └── NVDA_news_data.csv
│
├── press_release_data/                  # Company press releases
│   ├── AAPL_press_release_data.csv
│   ├── AMZN_press_release_data.csv
│   ├── GOOG_press_release_data.csv
│   ├── META_press_release_data.csv
│   ├── MSFT_press_release_data.csv
│   └── NVDA_press_release_data.csv
│
├── social_sentiment_data/               # Social media sentiment data
│   ├── AAPL_social_sentiment_data.csv
│   ├── AMZN_social_sentiment_data.csv
│   ├── META_social_sentiment_data.csv
│   ├── MSFT_social_sentiment_data.csv
│   └── NVDA_social_sentiment_data.csv
│
├── complete_news_data/                  # Processed and merged news sentiment data
│   ├── AAPL_complete_news_data.csv
│   ├── AMZN_complete_news_data.csv
│   ├── GOOG_complete_news_data.csv
│   ├── META_complete_news_data.csv
│   ├── MSFT_complete_news_data.csv
│   └── NVDA_complete_news_data.csv
│
├── technical_indicators/                # Technical analysis indicators
│   ├── ADX/                             # Average Directional Index
│   ├── DEMA/                            # Double Exponential Moving Average
│   ├── EMA/                             # Exponential Moving Average
│   ├── RSI/                             # Relative Strength Index
│   ├── SMA/                             # Simple Moving Average
│   ├── STANDARDDEVIATION/               # Standard Deviation
│   ├── TEMA/                            # Triple Exponential Moving Average
│   ├── WILLIAMS/                        # Williams %R
│   ├── WMA/                             # Weighted Moving Average
│   ├── Merged_Technical_Indicators/     # Merged technical indicators per company
│   ├── technical_indicators.py          # Script for fetching technical indicators
│   └── merged_technical_indicators.py   # Script for merging indicators
│
├── forex_data/                          # Foreign exchange rate data
│   ├── CADUSD_forex_data.csv
│   ├── CHFUSD_forex_data.csv
│   ├── CNHUSD_forex_data.csv
│   ├── EURUSD_forex_data.csv
│   ├── GBPUSD_forex_data.csv
│   ├── JPYUSD_forex_data.csv
│   └── KRWUSD_forex_data.csv
│
├── commodity_data/                      # Commodity price data
│   ├── Copper_commodity_data.csv
│   ├── Gold_commodity_data.csv
│   ├── Lithium_commodity_data.csv
│   ├── Palladium_commodity_data.csv
│   └── Silver_commodity_data.csv
│
├── market_performance/                  # Market performance metrics
│   ├── historical_sector_performance.csv
│   └── sector_pe_ratio.csv
│
├── treasury_rates_data.csv              # US Treasury rates data
├── inflation_rates_data.csv             # Inflation rates data
│
├── full_models_complete_datasets/       # Complete datasets and modeling notebooks
│   ├── full_complete_datasets/          # Final merged datasets for each company
│   │   ├── AAPL_raw_complete_data.csv
│   │   ├── AMZN_raw_complete_data.csv
│   │   ├── GOOG_raw_complete_data.csv
│   │   ├── META_raw_complete_data.csv
│   │   ├── MSFT_raw_complete_data.csv
│   │   └── NVDA_raw_complete_data.csv
│   ├── Forecasted Data/                 # Model forecast outputs
│   ├── apple_cleaning_modelling.ipynb   # Apple stock forecasting model
│   ├── Amazon_Stock_Price_Forecasting.ipynb  # Amazon stock forecasting model
│   ├── google_cleaning_modelling.ipynb  # Google stock forecasting model
│   ├── meta_work.ipynb                  # Meta stock forecasting model
│   ├── Microsoft_Stock_Price_Forecasting.ipynb  # Microsoft stock forecasting model
│   └── nvidia_modelling.ipynb           # NVIDIA stock forecasting model
│
├── Interesting_articles_for_lit_review/ # Research papers and literature
│   └── [Various PDF research papers]
│
├── Others/                              # Additional resources
│   ├── LSTM_Model.ipynb                 # LSTM model implementation
│   └── Big Data Streamline Process.docx # Project documentation
│
└── Stock_Price_Prediction_of_Top_Technology_Companies_Using_Market_Data_and_News_Sentiment_Analysis.pdf
    # Final project report
```

## Data Sources

### 1. Stock Price Data
- **Source**: Tiingo API
- **Data**: Historical daily stock prices (open, high, low, close, volume, adjusted close)
- **Period**: From IPO date to current date

### 2. News Data
- **Source**: Financial Modeling Prep (FMP) API
- **Data**: Stock news articles, headlines, and briefs
- **Processing**: VADER sentiment analysis applied to news articles

### 3. Press Releases
- **Source**: FMP API
- **Data**: Company press releases with dates and content
- **Processing**: VADER sentiment analysis

### 4. Social Media Sentiment
- **Source**: FMP API
- **Data**: Twitter and StockTwits sentiment data
- **Metrics**: Posts, likes, sentiment scores

### 5. Technical Indicators
- **Source**: FMP API
- **Indicators**: ADX, DEMA, EMA, RSI, SMA, Standard Deviation, TEMA, Williams %R, WMA
- **Period**: Daily data from IPO date

### 6. Forex Data
- **Source**: FMP API
- **Currencies**: EUR/USD, GBP/USD, JPY/USD, CNH/USD, KRW/USD, CHF/USD, CAD/USD
- **Data**: Daily exchange rates

### 7. Commodity Data
- **Source**: FMP API
- **Commodities**: Gold, Silver, Lithium, Copper, Palladium
- **Data**: Historical daily prices

### 8. Macroeconomic Data
- **Treasury Rates**: US Treasury rates (1 month to 30 years)
- **Inflation Rates**: US inflation rate data
- **Market Performance**: Sector performance and P/E ratios

## Methodology

### 1. Data Collection
The project uses multiple APIs to collect comprehensive financial data:
- **Tiingo API**: Stock price data
- **Financial Modeling Prep (FMP) API**: News, sentiment, technical indicators, forex, commodities, and macroeconomic data

### 2. Data Preprocessing

#### Text Cleaning and Sentiment Analysis
- **VADER Sentiment Analyzer**: Applied to news articles and press releases
- **Text Cleaning**:
  - URL removal
  - Special character handling
  - Percentage and number formatting (M → million, B → billion)
  - Sentence splitting for granular sentiment analysis

#### Sentiment Classification
Sentiment scores are classified into five categories:
- **Strongly Positive**: score > 0.5
- **Weakly Positive**: 0.05 < score ≤ 0.5
- **Neutral**: -0.05 ≤ score ≤ 0.05
- **Weakly Negative**: -0.5 ≤ score < -0.05
- **Strongly Negative**: score < -0.5

#### Daily Aggregation
- Sentiment scores are averaged by date to create daily sentiment metrics
- Multiple sentiment sources are merged (news, press releases, social media)

### 3. Feature Engineering

#### Technical Indicators
Nine technical indicators are calculated for each stock:
1. **ADX** (Average Directional Index)
2. **DEMA** (Double Exponential Moving Average)
3. **EMA** (Exponential Moving Average)
4. **RSI** (Relative Strength Index)
5. **SMA** (Simple Moving Average)
6. **Standard Deviation**
7. **TEMA** (Triple Exponential Moving Average)
8. **Williams %R**
9. **WMA** (Weighted Moving Average)

#### Data Merging
All datasets are merged on the date column using outer joins to preserve all available data points:
- Stock prices
- Technical indicators
- News sentiment (stock news, press releases, social media)
- Forex rates
- Commodity prices
- Treasury rates
- Inflation rates
- Market performance metrics

### 4. Machine Learning Models

The project implements multiple forecasting models for each company:

#### 1. LSTM (Long Short-Term Memory)
- Deep learning model for time series forecasting
- Architecture: Multi-layer LSTM with dropout regularization
- Features: Handles sequential patterns in stock prices

#### 2. BiLSTM (Bidirectional LSTM)
- Bidirectional LSTM for capturing patterns in both directions
- Enhanced feature extraction from time series data

#### 3. Lasso Regression
- Regularized linear regression with L1 regularization
- Feature selection through coefficient shrinkage
- Handles multicollinearity in high-dimensional data

#### 4. Random Forest
- Ensemble learning method
- Handles non-linear relationships
- Feature importance analysis

#### 5. ARIMA/SARIMAX
- Statistical time series model
- AutoARIMA for automatic parameter selection
- Handles seasonality and trends

### 5. Model Evaluation

Models are evaluated using multiple metrics:
- **RMSE** (Root Mean Squared Error)
- **MAE** (Mean Absolute Error)
- **MAPE** (Mean Absolute Percentage Error)
- **Pearson Correlation Coefficient**
- **Spearman Correlation Coefficient**

### 6. Forecasting
- Models generate forecasts for future stock prices
- Forecasts are compared with actual prices (where available)
- March 2025 forecasts are generated and stored for evaluation

## Installation and Setup

### Prerequisites
- Python 3.7 or higher
- Jupyter Notebook
- API keys for:
  - Financial Modeling Prep (FMP) API
  - Tiingo API (optional, for stock prices)

### Required Python Packages

```python
# Data manipulation and analysis
pandas
numpy

# API requests
requests

# Sentiment analysis
vaderSentiment

# Machine learning
scikit-learn
tensorflow
keras

# Time series analysis
statsmodels
pmdarima

# Data visualization
matplotlib
seaborn

# Environment variables
python-dotenv

# Statistical analysis
scipy
```

### Installation Steps

1. **Clone the repository** (if applicable)
   ```bash
   git clone <repository-url>
   cd "Big Data Project"
   ```

2. **Install required packages**
   ```bash
   pip install pandas numpy requests vaderSentiment scikit-learn tensorflow keras statsmodels pmdarima matplotlib seaborn python-dotenv scipy
   ```

3. **Set up API keys**
   - Create an `api.env` file in the project root
   - Add your API keys:
     ```
     fmp_api_key=your_fmp_api_key_here
     openai_api_key=your_openai_api_key_here (optional)
     ```
   - For Tiingo API, update the token in `stock_price_data.py`

4. **Run data collection scripts**
   - Execute `data_pulling_joining.ipynb` to collect all data
   - Run `stock_price_data.py` to fetch stock prices
   - Run `technical_indicators/technical_indicators.py` to fetch technical indicators
   - Run `merging_technical_indicator_companywise.py` to merge technical indicators

## Usage

### 1. Data Collection

#### Collect Stock Prices
```bash
python stock_price_data.py
```

#### Collect Technical Indicators
```bash
cd technical_indicators
python technical_indicators.py
python merged_technical_indicators.py
```

#### Collect All Data and Process Sentiment
Open and run `data_pulling_joining.ipynb`:
- Fetches news data, press releases, social sentiment
- Applies VADER sentiment analysis
- Aggregates daily sentiment scores
- Merges all datasets

### 2. Data Preprocessing

The preprocessing is handled in `data_pulling_joining.ipynb`:
- Text cleaning
- Sentiment analysis
- Daily aggregation
- Data merging

### 3. Model Training and Forecasting

For each company, open the corresponding modeling notebook:
- `apple_cleaning_modelling.ipynb` for Apple
- `Amazon_Stock_Price_Forecasting.ipynb` for Amazon
- `google_cleaning_modelling.ipynb` for Google
- `meta_work.ipynb` for Meta
- `Microsoft_Stock_Price_Forecasting.ipynb` for Microsoft
- `nvidia_modelling.ipynb` for NVIDIA

Each notebook includes:
1. Data loading and cleaning
2. Feature selection
3. Train-test splitting
4. Model training (LSTM, BiLSTM, Lasso, Random Forest, ARIMA)
5. Model evaluation
6. Forecasting
7. Visualization

### 4. Results

Forecasted prices are saved in `full_models_complete_datasets/Forecasted Data/` for each company.

## Key Features

1. **Comprehensive Data Integration**: Combines multiple data sources for robust forecasting
2. **Sentiment Analysis**: Uses VADER for news and social media sentiment analysis
3. **Technical Analysis**: Incorporates nine technical indicators
4. **Multiple Models**: Implements five different forecasting approaches
5. **Macroeconomic Factors**: Includes forex, commodities, inflation, and treasury rates
6. **Market Context**: Incorporates sector performance and P/E ratios

## Data Quality

### Data Cleaning Steps
- Duplicate removal
- Missing value handling (forward fill, interpolation)
- Date standardization (DD-MM-YYYY format)
- Data type conversion
- Outlier detection and handling

### Data Statistics
- **News Articles**: ~130,000+ articles across all companies
- **Press Releases**: ~2,400+ press releases
- **Social Sentiment**: Historical sentiment data for 5 companies
- **Stock Prices**: Daily data from IPO to current date
- **Technical Indicators**: 9 indicators per company
- **Forex Data**: 7 currency pairs
- **Commodity Data**: 5 commodities
- **Time Period**: 1980 to 2025 (varies by company IPO date)

## Limitations

1. **API Rate Limits**: Some APIs have rate limits that may require delays between requests
2. **Data Availability**: Some data sources may have limited historical data
3. **Sentiment Analysis**: VADER may not capture all nuances in financial news
4. **Model Performance**: Stock price forecasting is inherently challenging and predictions may not always be accurate
5. **External Factors**: Unforeseen events (e.g., pandemics, geopolitical events) may affect predictions

## Future Improvements

1. **Additional Data Sources**: Incorporate more data sources (e.g., options data, insider trading)
2. **Advanced Sentiment Analysis**: Use transformer models (BERT, GPT) for better sentiment analysis
3. **Feature Engineering**: Create more sophisticated features (e.g., lagged features, rolling statistics)
4. **Ensemble Methods**: Combine predictions from multiple models
5. **Real-time Updates**: Implement real-time data collection and forecasting
6. **Risk Analysis**: Add risk metrics and confidence intervals to forecasts
7. **Hyperparameter Tuning**: Systematic hyperparameter optimization for all models

## API Keys and Security

**Important**: 
- Never commit API keys to version control
- The `api.env` file is included in `.gitignore`
- Use environment variables for API keys in production
- Rotate API keys regularly

## Citation

If you use this project in your research, please cite:
```
Stock Price Prediction of Top Technology Companies Using Market Data and News Sentiment Analysis
Big Data Analysis Project, University of Guelph, 2025
```

## License

This project is for educational and research purposes only. Please ensure compliance with API terms of service and data usage policies.

## Contact

For questions or issues, please refer to the project documentation or contact the project team.

## Acknowledgments

- Financial Modeling Prep (FMP) for financial data API
- Tiingo for stock price data API
- VADER Sentiment Analysis tool
- All contributors to the open-source libraries used in this project

---

**Note**: This project is part of a Big Data Analysis course at the University of Guelph. The models and forecasts are for educational purposes and should not be used for actual investment decisions without proper validation and risk assessment.

