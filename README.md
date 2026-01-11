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


```

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

```
News Impact Index = avg_sentiment * log(1 + news_count)
```

Higher score → more positive news pressure  
Lower score → more negative news pressure  

---

## 🚀 How To Run

### 1. Install required packages:

```
pip install -r requirements.txt
```

### 2. Open the main notebook:

```
stock.ipynb
```

### 3. Run cells step-by-step:
- Load data  
- Clean data  
- Run FinBERT  
- Create sentiment scores  
- Build impact index  
- View results  

---

## 📊 Example Output

| ticker | avg_sentiment | news_count | news_impact_index |
|--------|---------------|------------|-------------------|
| MSFT   | -0.24         | 100        | -1.11             |
| TSLA   | -0.32         | 99         | -1.50             |
| GOOGL  | -0.36         | 100        | -1.68             |
| AAPL   | -0.44         | 100        | -2.05             |
| AMZN   | -0.44         | 100        | -2.06             |

Even if all are negative, **relative ranking** still gives useful signal.

---

## 🎯 Why This Project is Useful

- Helps understand market sentiment  
- Builds a real quantitative research pipeline  
- Can be extended with:
  - price prediction  
  - event classification  
  - live news ingestion  
- Great project for resumes and interviews  

---

## 📝 Notes

- FinBERT works offline using PyTorch  
- No API keys required  
- Dataset must contain at least a `headline` and `ticker` column  

---

## 🙌 Future Improvements

- Add price-based backtesting  
- Add event categories (earnings, product launch, etc.)  
- Deploy as a Streamlit dashboard  
