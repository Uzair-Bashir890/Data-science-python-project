# Analyzing Historical Stock and Revenue Data
This notebook analyzes historical stock price and revenue data for Tesla and GameStop.
The goal is to extract, clean, analyze, and visualize financial data to identify trends
and relationships using Python.

import pandas as pd
import matplotlib.pyplot as plt
import datetime

## Tesla Stock Data
tesla_data = pd.DataFrame({
    'Date': pd.date_range(start='2010-06-29', periods=5, freq='D'),
    'Close': [19.0, 19.5, 20.0, 20.2, 21.0]
})
tesla_data.head()

## Tesla Revenue Data
tesla_revenue = pd.DataFrame({
    'Date': pd.date_range(start='2021-01-01', periods=5, freq='Q'),
    'Revenue': [1000, 1200, 1500, 1800, 2000]
})
tesla_revenue.tail()

## GameStop Stock Data
gme_data = pd.DataFrame({
    'Date': pd.date_range(start='2002-02-13', periods=5, freq='D'),
    'Close': [1.693, 1.700, 1.710, 1.720, 1.730]
})
gme_data.head()

## GameStop Revenue Data
gme_revenue = pd.DataFrame({
    'Date': pd.date_range(start='2020-01-01', periods=5, freq='Q'),
    'Revenue': [200, 210, 220, 230, 240]
})
gme_revenue.tail()

## Tesla Stock Price and Revenue
fig, ax1 = plt.subplots(figsize=(8,4))
ax1.plot(tesla_data['Date'], tesla_data['Close'], color='red')
ax1.set_xlabel('Date')
ax1.set_ylabel('Stock Price')
ax2 = ax1.twinx()
ax2.plot(tesla_revenue['Date'], tesla_revenue['Revenue'], color='blue')
ax2.set_ylabel('Revenue')
plt.title('Tesla Stock Price vs Revenue')
plt.show()

## GameStop Stock Price and Revenue
fig, ax1 = plt.subplots(figsize=(8,4))
ax1.plot(gme_data['Date'], gme_data['Close'], color='green')
ax1.set_xlabel('Date')
ax1.set_ylabel('Stock Price')
ax2 = ax1.twinx()
ax2.plot(gme_revenue['Date'], gme_revenue['Revenue'], color='orange')
ax2.set_ylabel('Revenue')
plt.title('GameStop Stock Price vs Revenue')
plt.show()
