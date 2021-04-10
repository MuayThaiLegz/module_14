# Working the role of a financial advisor at one of the top five financial advisory firms in the world. 

* Goal
------

Enhance the existing trading signals with machine learning algorithms that can adapt to new data.
------

## Explanation
* Implement an algorithmic trading strategy that uses machine learning to automate the trade decisions.
* Adjust the input parameters to optimize the trading algorithm.
* Train a new machine learning model and compare its performance to that of a baseline model.
------

## Technologies 
# Pandas
We used Pandas

* Importing the data.
* Creating SMA DataFrames with Pandas methods.
* Using Pandas methods on our dataframes.
------
```
# Import the OHLCV dataset into a Pandas Dataframe
ohlcv_df = pd.read_csv(
    Path("./Resources/emerging_markets_ohlcv.csv"), 
    index_col='date', 
    infer_datetime_format=True, 
    parse_dates=True
)

# Review the DataFrame
ohlcv_df.head()

# Set the short window and long window
short_window = 4
long_window = 100

# Generate the fast and slow simple moving averages (4 and 100 days, respectively)
signals_df['SMA_Fast'] = signals_df['close'].rolling(window=short_window).mean()
signals_df['SMA_Slow'] = signals_df['close'].rolling(window=long_window).mean()

signals_df = signals_df.dropna()

# Review the DataFrame
display(signals_df.head())
display(signals_df.tail())

# Select the start of the training period
training_begin = X.index.min()

# Select the ending period for the training data with an offset of 3 months
training_end = X.index.min() + DateOffset(months=3)

# Generate the X_train and y_train DataFrames
X_train = X.loc[training_begin:training_end]
y_train = y.loc[training_begin:training_end]

# Review the X_train DataFrame
X_train.head()
```

------
```
