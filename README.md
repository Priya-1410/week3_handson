# 🧪 Reproducibility Report
Course: CS 5588 – Data Science Capstone
Assignment: Reproducibility Lab
Team / Student: team4 - Mohini priya Chinthoti
GitHub Repo: https://github.com/Priya-1410/week3_handson.git
Date: [09/15/2025]
---
## 1. Upstream Repository
- Original Project Repo: https://github.com/ivebotunac/PrimoAgent  
- Commit Hash Used: [commit ID]
- Citation (if applicable): [Paper/DOI/ArXiv link]
---
## 2. Environment
- Python version: 3.12.11
- Operating System / Platform: Google colab
- Hardware (CPU/GPU): Google Colab default CPU
- Frameworks & Libraries (versions):
  - ta 
  - langchain = [...]  
  - yfinance = [...]  
  - Other dependencies as listed in `requirements.txt`  
- Dependency lock file: requirements.lock.txt
---
## 3. Data
- Dataset(s) Used:
- Name: Stock price and financial news data
- Source/URL: yFinance, Finnhub APIs 
- Version/Revision (if from Hugging Face or Kaggle): Data fetched dynamically from APIs during runs 
- Checksum (MD5/SHA): N/A
- Preprocessing steps applied: Automated by PrimoAgent during runtime
---
## 4. Baseline Run
- Command Executed:
python main.py
- Interactive inputs piped in (automated in `run_all.sh`):  
- Stock symbol: AAPL  
- Start date: 2025-05-28  
- End date: 2025-06-30  
- Output Location: runs/baseline/  
- Results / Metrics:  
- Trading days analyzed: 24  
- Successfully completed Data Collection and Technical Analysis agents  
- Some GPT-based summary steps failed due to rate limits (see notes)  
- Sample Output (qualitative):  
Current Price: $200.19
Technical Success: True


---
## 5. Controlled Variation
- Parameter Changed: Stock symbol changed from `AAPL` to `TSLA`  
- Command Executed:  python main.py
- Interactive inputs piped in as above with new stock symbol  
- Output Location: runs/variation/  
- Results / Metrics:  
- Trading days analyzed: Same (24)  
- Analysis completed up to technical agent for TSLA stock  
- Comparison Table:

| Run       | Stock Symbol | Trading Days | Notes                        |
|-----------|--------------|--------------|------------------------------|
| Baseline  | AAPL         | 24           | Partial success, GPT rate limit |
| Variation | TSLA         | 24           | Similar partial success       |

---

## 6. Reproducibility Notes
- Steps taken to ensure reproducibility:  
- Fixed random seed (`PYTHONHASHSEED=42`)  
- Logged environment info and Git commit hash  
- Automated runs with `run_all.sh` including inputs  
- Saved outputs and logs in versioned folders `runs/` and `logs/`  
- Challenges encountered:  
- Could not install `pyfolio` dependency on Colab; skipped this optional library  
- OpenAI API rate limits caused GPT-based sections to fail; documented in logs  
- `ta` library missing initially but installed manually  
- Deviations from upstream instructions:  
- Removed or bypassed pyfolio due to build issues in Colab  
- Used fixed inputs piped in for automation instead of manual inputs  

---

## 7. Reflection
- **Relevance to capstone:** PrimoAgent’s multi-agent architecture for financial analysis aligns with our team’s interest in combining NLP with technical indicators for stock prediction.  
- **Overlap:** Project uses real-time data APIs and advanced NLP features, similar to our plan to integrate multiple data sources for robust analysis.  
- **Reproducibility:** Installation and running baseline was straightforward once dependencies were managed; interactive inputs were handled well via scripting. Handling API limits was the main challenge.  
- **Application:** Learned the importance of environment logging, fixed seeds, and automating experiments for reproducibility; will apply these best practices in our project workflow.  

---
