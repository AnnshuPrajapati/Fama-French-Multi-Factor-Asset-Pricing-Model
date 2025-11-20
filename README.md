# Fama-French Multi-Factor Asset Pricing Model: Bull vs Bear Market Analysis

**FF5 outperforms FF3 in bear markets due to profitability & investment factors**

Bull vs Bear market analysis of Fama-French models. FF5 outperforms FF3 in bear markets due to RMW/CMA factors. Regime-filtered momentum strategy achieves 4.38% CAGR with 0.58 Sharpe.

Python • Machine Learning • Factor Investing

## 🎯 Key Finding

FF5 significantly beats FF3 during bear markets (higher R² and Alpha) because RMW and CMA factors capture stress dynamics. In bull markets, both models perform identically.

## 📊 Results (2005-2024)

**Regime-Filtered Momentum Strategy**:
- CAGR: 4.38% | Sharpe: 0.58 | Final Value: $2.27
- 13 total trades (7 entries, 6 exits) over 19.1 years

**Model Performance**:
| Market | Winner | Why |
|--------|--------|-----|
| Bear | FF5 | Higher R² & Alpha - profitability/investment factors matter |
| Bull | Tie | Both ~identical - market beta dominates |

## 🔑 Key Insights

✅ **FF5 excels in bear markets** - RMW and CMA factors capture stress dynamics  
✅ **FF3 sufficient for bull markets** - Simpler model, nearly identical performance  
✅ **Higher alpha in bear markets** - Especially for FF5 (better stock selection)  
✅ **ML captures nonlinear patterns** - RF/XGBoost effective in volatile regimes  
✅ **Regime-aware trading reduces risk** - Only 13 trades vs constant market exposure  

## 📈 Portfolio Strategy

**Assets**: 10 diversified ETFs (stocks, bonds, gold, commodities, REITs)  
**Weighting**: Equal-weighted, monthly rebalancing  
**Entry Signal**: Bull market + positive 12-month momentum  
**Exit Signal**: Regime switch to bear OR momentum turns negative  
**Costs**: 0.15% transaction cost, 30% portfolio turnover  

## 🛠️ Tech Stack

Python • pandas • NumPy • scikit-learn • statsmodels • yfinance  
**Models**: FF3, FF5, Linear Regression, Random Forest, XGBoost, Ridge

## 🔬 Methodology
```python
# 1. Regime Detection
bull = SPY_returns.rolling(252).sum() > 0

# 2. Factor Regression
# FF3: R-Rf = α + β1(Mkt-Rf) + β2(SMB) + β3(HML)
# FF5: adds β4(RMW) + β5(CMA)

# 3. Trading Signal
signal = (bull) & (momentum > 0)  # Enter only in bull + positive momentum
```


## 📁 Files

- `bull_bear_analysis.py` - Implementation
- `Annshu_Project_Slides_Final.pdf` - Full presentation

## 💡 Why FF5 Wins in Bear Markets

- **RMW (Profitability)**: Robust companies outperform weak ones during stress
- **CMA (Investment)**: Conservative investment beats aggressive in downturns
- **Result**: FF5 explains more variance and generates higher alpha

## 🎓 Factor Definitions

**FF3**: Market (Mkt-RF), Size (SMB), Value (HML)  
**FF5**: + Profitability (RMW), Investment (CMA)

