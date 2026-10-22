# Stock Market Price Prediction Using Deep Learning Techniques

## Overview

This project explores stock market price prediction using **Long Short-Term Memory (LSTM)**, a type of Recurrent Neural Network (RNN) designed to learn temporal patterns in sequential data. The project uses historical stock market data to analyze price movements, preprocess time-series data, train a deep learning model, and evaluate its predictive performance.

The primary objective is to investigate how deep learning techniques can be applied to historical stock price data for time-series forecasting.

## Objectives

- Analyze historical stock market data using Exploratory Data Analysis (EDA).
- Identify patterns and relationships among stock market variables.
- Preprocess and normalize closing-price data for deep learning.
- Develop an LSTM-based time-series prediction model.
- Evaluate model performance using Root Mean Squared Error (RMSE) and Mean Absolute Error (MAE).
- Visualize actual and predicted stock prices to assess forecasting behavior.

## Technologies Used

- **Programming Language:** Python
- **Deep Learning:** TensorFlow, Keras, LSTM
- **Data Processing:** Pandas, NumPy
- **Data Visualization:** Matplotlib, Seaborn, Plotly
- **Machine Learning Utilities:** Scikit-learn
- **Development Environment:** Google Colab, Jupyter Notebook

## Dataset

The project uses historical Yahoo stock market data, with the dataset referenced from Kaggle.

**Dataset source:** [Time Series Forecasting with Yahoo Stock Price](https://www.kaggle.com/datasets/arashnic/time-series-forecasting-with-yahoo-stock-price)

The dataset contains the following features:

| Feature | Description |
|---|---|
| Date | Historical trading date |
| Open | Opening stock price |
| High | Highest stock price during the trading period |
| Low | Lowest stock price during the trading period |
| Close | Closing stock price |
| Adj Close | Adjusted closing price |
| Volume | Number of shares traded |

The closing price (`Close`) is used as the target variable for the LSTM prediction model.

## Methodology

### 1. Exploratory Data Analysis

The dataset is explored to understand its structure, statistical properties, and relationships between features. The analysis includes:

- Missing-value inspection
- Descriptive statistical analysis
- Box plots for price-related variables
- Historical closing-price visualization
- Feature distribution analysis
- Scatter-matrix visualization
- Correlation-matrix analysis

### 2. Data Preprocessing

The data preprocessing pipeline includes:

- Converting the `Date` column to datetime format
- Setting the date as the DataFrame index
- Scaling closing prices using `MinMaxScaler`
- Splitting the time series into training and testing sets
- Creating sequential input samples using a 60-time-step sliding window

The model uses the previous 60 observations to predict the next closing price.

### 3. LSTM Model Development

An LSTM-based deep learning model is implemented using TensorFlow and Keras. LSTM networks are designed to learn temporal dependencies in sequential data and are commonly used in time-series forecasting.

The model is trained on historical closing-price sequences to learn patterns that may help estimate subsequent prices.

### 4. Model Evaluation

The model's performance is evaluated using two regression metrics:

- **Root Mean Squared Error (RMSE):** Measures the square root of the average squared prediction error.
- **Mean Absolute Error (MAE):** Measures the average absolute difference between actual and predicted prices.

### 5. Visualization

Interactive Plotly visualizations are used to compare actual stock prices with model predictions across the training and testing periods.

## Experimental Results

The following results were obtained from the current notebook execution.

| Evaluation Metric | Training Set | Testing Set |
|---|---:|---:|
| RMSE | 26.08 | 64.13 |
| MAE | 18.96 | 42.88 |

**Note:** These are preliminary experimental results from the current model configuration. The errors are expressed in the original stock-price units. The difference between training and testing errors suggests that further evaluation and model improvement may be beneficial.

## Repository Structure

```text
Stock-Market-Price-Prediction/
│
├── README.md
└── Stock_Market_Price_Prediction_saki_sir.ipynb
```

## How to Run the Project

You can run the notebook using Google Colab or a local Jupyter environment.

### Option 1: Google Colab

1. Open the notebook from this repository.
2. Upload the dataset to your Google Drive.
3. Update the dataset path in the notebook to match your file location.
4. Run the notebook cells sequentially.

**Notebook:** [Stock Market Price Prediction](https://github.com/raju-cse/Stock-Market-Price-Prediction/blob/main/Stock_Market_Price_Prediction_saki_sir.ipynb)

### Option 2: Local Environment

Clone the repository:

```bash
git clone https://github.com/raju-cse/Stock-Market-Price-Prediction.git
cd Stock-Market-Price-Prediction
```

Install the required libraries:

```bash
pip install pandas numpy matplotlib seaborn plotly scikit-learn tensorflow jupyter
```

Launch Jupyter Notebook:

```bash
jupyter notebook
```

Open `Stock_Market_Price_Prediction_saki_sir.ipynb` and update the dataset path before running the notebook.

## Future Improvements

Potential directions for future development include:

- Comparing LSTM with GRU, CNN-LSTM, and Transformer-based architectures
- Incorporating additional technical indicators and market features
- Implementing chronological validation and expanding-window evaluation
- Comparing performance against simple baseline forecasting methods
- Investigating hyperparameter optimization and regularization
- Evaluating performance across different stocks and forecasting horizons

## Limitations

Stock market prices are influenced by numerous factors, including economic conditions, market sentiment, and unexpected events. Historical price patterns alone cannot reliably predict future market movements. The model's results should therefore be interpreted as experimental forecasting results rather than guaranteed predictions.

## Author

**Raju Ahmad**

- GitHub: [raju-cse](https://github.com/raju-cse)
- Repository: [Stock-Market-Price-Prediction](https://github.com/raju-cse/Stock-Market-Price-Prediction)

## Disclaimer

This project is intended for educational and research purposes only. It does not constitute financial or investment advice.
