📈 Market Mix Modeling (MMM) — End-to-End Python Implementation
> Part of the [Marketing Analytics Portfolio](../)  
> **Domain:** Retail / CPG | **Technique:** Econometric Modelling  
> **Author:** Shashank Paliwal | [LinkedIn](https://linkedin.com/in/shashank-paliwal-ba1ba171) | [Medium Article](#)
---
Business Problem
A large retailer spends £50m+ annually across 8 media channels — TV, Radio, Out-of-Home, Digital, In-store Displays, Leaflets, Loyalty Campaigns, and Sampling. The marketing team wants to know:
Which channels are actually driving incremental sales?
What is the true ROI of each channel after controlling for seasonality, holidays, and macroeconomics?
How should budget be reallocated to maximise sales impact?
Traditional reporting (comparing sales during vs. after campaigns) can't answer this — it confounds media effects with seasonality, competitor activity, and external events. Market Mix Modeling solves this.
---
What This Notebook Covers
Section	Description
1. Data Generation	104 weeks of synthetic retail data — 8 channels, 40+ external variables
2. EDA	Sales trends, spend distribution, correlation heatmap
3. Adstock Transformation	Geometric decay to capture carry-over advertising effects
4. Model Building	Log-log OLS regression with HC3 robust standard errors
5. Model Diagnostics	R², MAPE, actual vs predicted, residual analysis
6. Sales Decomposition	Baseline vs Media vs External factor contribution splits
7. ROI by Channel	Elasticity-driven channel-level ROI with bubble chart
8. Budget Optimisation	SLSQP constrained optimisation for maximum incremental sales
9. Key Takeaways	Summary + real-world extensions
---
Methodology
Why Log-Log OLS?
The log-log specification is the industry standard for MMM:
```
log(Sales_t) = α + Σ βᵢ × log(Adstock_i,t) + Σ γⱼ × X_j,t + ε_t
```
βᵢ = channel elasticity (% change in sales per 1% change in spend)
Automatically handles diminishing returns
Coefficients are directly interpretable as elasticities
Stable, well-understood inference
Adstock Transformation
Advertising has a carry-over effect — a TV ad seen this week influences purchases next week too. Adstock captures this:
```
Adstock(t) = Spend(t) + λ × Adstock(t-1)
```
Channel-specific decay rates (λ) used in this model:
Channel	Decay (λ)	Rationale
TV	0.60	Long brand recall
Loyalty	0.50	Habitual repeat behaviour
Radio	0.45	Moderate recall
OOH	0.40	Passive exposure
In-store Display	0.35	Point-of-purchase stimulus
Digital	0.30	Immediate response
Leaflet	0.25	Short promotional window
Sampling	0.20	In-the-moment trial
External Variable Controls (40+)
Category	Variables
Holidays	Christmas, Easter, Bank Holidays, Black Friday, Back to School, Cyber Monday, Diwali, and more
Sports Events	FIFA World Cup, Rugby World Cup, Six Nations, Cricket
Macroeconomics	CPI Index, Unemployment, GDP, Petrol Price, Consumer Confidence
Weather	Average Temperature, Snowfall, Total Precipitation
Festivals	Shrove Tuesday, Burns Night, Diwali, Hinduism festivals
School Holidays	UK school holiday calendar
---
Key Outputs
Sales Decomposition
Breaks total sales into:
Baseline (~60–65%): sales without any marketing activity
Media contribution (~25–30%): incremental sales per channel
External factors (~10%): holidays, seasonality, macroeconomics
ROI by Channel
Elasticity-based ROI showing £ generated per £1 of media spend — the foundation for budget reallocation conversations.
Budget Optimisation
Given a fixed total budget, the model recommends how to reallocate spend across channels using constrained optimisation to maximise incremental sales.
---
Real-World Context
This notebook is inspired by a real MMM implementation for the UK's second largest grocery retailer (~£32bn revenue):
Covered ~£50m+ in annual media spend across 8 channels
Controlled for 40+ external variables across 6 categories
Reduced reporting cycle from 4–6 weeks to daily automated outputs (~90% time saving)
15,000+ campaigns evaluated through the framework
Contributed to ~10–15% cost savings in media spend optimisation
All data in this notebook is synthetic. No client or proprietary data is used.
---
How to Run
```bash
# Install dependencies
pip install pandas numpy scipy statsmodels scikit-learn matplotlib seaborn jupyter

# Launch notebook
jupyter notebook market_mix_modeling.ipynb
```
Or run directly in Google Colab: (no installation needed)  
![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)
---
Dependencies
```
pandas >= 1.5.0
numpy >= 1.23.0
scipy >= 1.9.0
statsmodels >= 0.13.0
scikit-learn >= 1.1.0
matplotlib >= 3.6.0
seaborn >= 0.12.0
```
---
Further Reading
📝 Medium Article: How Market Mix Modeling Actually Works
📂 Next Project: Multi-Touch Attribution
🔗 Google's Meridian MMM (open source)
🔗 Meta's Robyn MMM (open source)
---
Connect
Found this useful? Let's connect:
💼 LinkedIn
📝 Medium
📧 spshashankpaliwal@gmail.com
