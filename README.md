# Quant News Sentiment Analysis Using FinBERT

This project analyzes stock market news using **FinBERT**, a financial sentiment model.  
The goal is to understand whether the news around each stock is **positive, neutral, or negative**, and then create a **News Impact Index** to rank stocks based on sentiment pressure.

This helps in making better trading or research decisions.

---

## 📌 What This Project Does

1. Loads stock news data (headlines + tickers)  
2. Cleans the data (removes duplicates, missing headlines)  
3. Uses FinBERT (PyTorch) to find:
   - Positive sentiment  
   - Neutral sentiment  
   - Negative sentiment  
4. Creates a numerical sentiment score between -1 and +1  
5. Builds a News Impact Index  
6. Ranks stocks based on sentiment  
7. Compares sentiment with stock returns

---

## 🧠 How FinBERT Works

FinBERT is trained on financial text.  
It reads a headline like:

> “Apple stock could drop 30% on valuation risks”

and outputs:

- **Sentiment:** Negative  
- **Confidence:** 0.91  
- **Sentiment score:** -0.91  

This allows us to measure the sentiment strength for each stock.

---

## 🧮 News Impact Index

To measure the overall sentiment impact of a stock, we compute:

