# Indian Stock Market Volatility Prediction

A machine learning project that predicts volatility for major Indian stock market indices using historical data and various regression models.

##  Overview

This project analyzes and predicts volatility for three major Indian stock market indices:
- **NIFTY 50** - India's benchmark stock market index
- **NIFTY NEXT 50** - Index of the next 50 large-cap stocks
- **BANK NIFTY** - Banking sector index

The project implements multiple machine learning models to predict market volatility using technical indicators and historical price data.

##  Features

- **Data Processing**: Automated data cleaning and preprocessing for multiple stock indices
- **Feature Engineering**: Creation of technical indicators including:
  - Daily returns
  - Moving averages (5-day and 10-day)
  - Rolling volatility measures
  - Lag features for time series analysis
- **Multiple ML Models**: Implementation of 5 different regression models:
  - Random Forest Regressor
  - Gradient Boosting Regressor
  - Support Vector Regressor (SVR)
  - Decision Tree Regressor
  - Linear Regression
- **Model Evaluation**: Comprehensive evaluation using MAE, MSE, RMSE, and R² metrics
- **Visualization**: Actual vs predicted volatility plots for model comparison

##  Requirements

### Python Version
- Python 3.7 or higher

### Dependencies
```
pandas>=1.3.0
numpy>=1.21.0
matplotlib>=3.4.0
seaborn>=0.11.0
scikit-learn>=1.0.0
```

##  Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/yourusername/indian-stock-volatility-prediction.git
   cd indian-stock-volatility-prediction
   ```

2. **Create a virtual environment (recommended)**
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. **Install required packages**
   ```bash
   pip install -r requirements.txt
   ```

## 📁 Project Structure

```
indian-stock-volatility-prediction/
│
├── data/
│   ├── NIFTY50.csv
│   ├── NIFTYNEXT50.csv
│   └── BANKNIFTY.csv
│
│
├── notebooks/
│   └── volatility_analysis.ipynb
│
│
├── README.md
├── requirements.txt
├── .gitignore
└── LICENSE
```

##  Data Format

The CSV files should contain the following columns:
- `Date`: Trading date
- `Open`: Opening price
- `High`: Highest price of the day
- `Low`: Lowest price of the day
- `Close`: Closing price
- `Volume`: Trading volume (optional)

##  Usage

### Basic Usage

1. **Place your data files** in the `data/` directory with the following names:
   - `NIFTY50.csv`
   - `NIFTYNEXT50.csv`
   - `BANKNIFTY.csv`

2. **Run the main script**
   ```bash
   python src/volatility_prediction.py
   ```

### Jupyter Notebook

For interactive analysis, use the provided Jupyter notebook:
```bash
jupyter notebook notebooks/volatility_analysis.ipynb
```

### Customization

You can modify the following parameters in the script:
- **Feature engineering window sizes**: Adjust moving average periods
- **Train-test split ratio**: Default is 80-20 split
- **Model hyperparameters**: Tune model-specific parameters
- **Evaluation metrics**: Add or modify performance metrics

##  Model Performance

The project evaluates models using multiple metrics:

| Metric | Description |
|--------|-------------|
| **MAE** | Mean Absolute Error - Average prediction error |
| **MSE** | Mean Squared Error - Squared prediction error |
| **RMSE** | Root Mean Squared Error - Standard deviation of errors |
| **R²** | Coefficient of determination - Variance explained |

##  Results

The models are compared across all three indices, with results showing:
- **Random Forest** typically performs best for volatility prediction
- **Gradient Boosting** shows competitive performance
- **Linear models** provide baseline performance for comparison

Sample output:
```
NIFTY50 Model Comparison:
Model                    MAE      MSE      RMSE     R²
Random Forest           0.003245  0.000021  0.004612  0.847
Gradient Boosting       0.003456  0.000024  0.004899  0.823
Support Vector Regressor 0.004123  0.000032  0.005657  0.765
```

##  Technical Details

### Feature Engineering
- **Volatility Calculation**: `(High - Low) / Open`
- **Rolling Statistics**: Moving averages and standard deviations
- **Lag Features**: Previous period volatility for time series context
- **Returns**: Percentage change in closing prices

### Time Series Considerations
- **Chronological Splitting**: Train-test split maintains temporal order
- **No Data Leakage**: Future information excluded from training
- **Stationarity**: Features designed to capture market dynamics

##  Visualization

The project generates several visualizations:
- Actual vs Predicted volatility time series
- Model performance comparison charts
- Feature importance plots (for tree-based models)

##  Contributing

Contributions are welcome! Please follow these steps:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Disclaimer

This project is for educational and research purposes only. The predictions should not be used as the sole basis for investment decisions. Always consult with financial professionals and conduct thorough research before making investment decisions.

## Acknowledgments

- Data sources: Historical stock data from major Indian indices
- Scikit-learn library for machine learning implementations
- Pandas and NumPy for data manipulation
- Matplotlib and Seaborn for visualizations

##  Contact

For questions or suggestions, please open an issue on GitHub or contact [tiwari.pratyush25@gmail.com].

---

