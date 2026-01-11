# Quant News Sentiment Analysis Using FinBERT

This project analyzes stock market news using **FinBERT**, a BERT-based financial sentiment model.  
The goal is to classify news as **positive, neutral, or negative**, generate a numerical sentiment score, and compute a **News Impact Index** for each stock.

This provides a useful quantitative signal to support trading, research, or market analysis.

---

## 📌 Project Workflow

1. Load stock news data (`ticker` + `headline`)  
2. Clean the dataset (remove duplicates & missing values)  
3. Run FinBERT to get:
   - Positive sentiment
   - Neutral sentiment
   - Negative sentiment  
4. Convert sentiment to a numerical score between **-1 and +1**  
5. Compute **News Impact Index**  
6. Rank stocks based on sentiment pressure  
7. Compare sentiment with stock performance (optional)

---

## 🧠 How FinBERT Works

FinBERT is trained on financial documents.  
For example, a headline:

> “Apple stock could drop 30% on valuation risks”

FinBERT outputs:

- **Sentiment:** Negative  
- **Confidence:** 0.91  
- **Sentiment Score:** -0.91  

This lets us quantify the sentiment strength for each stock.

---

## 🧮 News Impact Index Formula

News Impact Index = avg_sentiment * log(1 + news_count)

yaml
Copy code

- Higher index → stronger positive sentiment pressure  
- Lower index → stronger negative sentiment pressure  

This helps compare sentiment across stocks, even if all of them are negative or positive.

---

## 🚀 How to Run the Project

### 1. Install Requirements
pip install -r requirements.txt

shell
Copy code

### 2. Open the Notebook
stock.ipynb

yaml
Copy code

### 3. Run Cells in Order
- Load dataset  
- Clean and preprocess  
- Run FinBERT  
- Generate sentiment scores  
- Build News Impact Index  
- Display ranking  

---

## 📊 Example Output

| ticker | avg_sentiment | news_count | news_impact_index |
|--------|---------------|------------|-------------------|
| MSFT   | -0.24         | 100        | -1.11             |
| TSLA   | -0.32         | 99         | -1.50             |
| GOOGL  | -0.36         | 100        | -1.68             |
| AAPL   | -0.44         | 100        | -2.05             |
| AMZN   | -0.44         | 100        | -2.06             |

Even when sentiment is broadly negative, **relative rankings** still provide useful signals.

---

## 🎯 Why This Project Matters

- Helps quantify news sentiment using a domain-specific model  
- Provides a foundation for quantitative research  
- Can be extended into:
  - Price-based backtesting  
  - ML prediction models  
  - Real-time news pipelines  
- Strong portfolio project for finance + ML roles  

---

## 📝 Notes

- FinBERT runs locally using PyTorch  
- No API keys needed  
- Input dataset must contain at least:
  - `ticker`
  - `headline`

---

## 🙌 Future Improvements

- Add backtesting using historical returns  
- Categorize events (earnings, guidance, regulatory news, etc.)  
- Deploy interactive dashboards using Streamlit  
- Automate data ingestion (Yahoo Finance, Google News, APIs)

---

## 📁 Repository Structure

├── README.md
├── requirements.txt
└── stock.ipynb

---

