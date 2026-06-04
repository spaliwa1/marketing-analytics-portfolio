📊 Marketing Analytics Portfolio
> **Author:** Shashank Paliwal | Data Science Manager  
> **Current Role:** Accenture Strategy & Consulting  
> **LinkedIn:** [shashank-paliwal-ba1ba171](https://linkedin.com/in/shashank-paliwal-ba1ba171)  
> **Medium:** [Coming soon]
---
About This Repository
This portfolio contains end-to-end marketing analytics implementations in Python, built from 11+ years of real-world experience across Retail, CPG, Pharmaceutical, and Manufacturing sectors.
Each project is:
Production-inspired — modelled on real client engagements at scale
Fully documented — readable as a tutorial, not just runnable code
Self-contained — synthetic data included, no external dependencies beyond standard Python libraries
---
Projects
#	Project	Domain	Key Techniques	Notebook
1	Market Mix Modeling (MMM)	Retail / CPG	Adstock, Log-log OLS, Budget Optimisation	`01_market_mix_modeling/`
2	Multi-Touch Attribution (MTA)	Retail / Digital	Shapley Values, Markov Chains, Channel Attribution	`02_multi_touch_attribution/`
3	Price Elasticity Modelling	Pharma / Retail	Elasticity, Pricing Strategy, Margin Optimisation	`03_price_elasticity/`
4	Customer Segmentation	Retail / CPG	RFM Analysis, K-Means Clustering, Campaign Targeting	`04_customer_segmentation/`
---
1. Market Mix Modeling
Business Problem: A large retailer spends £50m+ annually across 8 media channels. Which channels are actually driving incremental sales — and how should budget be reallocated to maximise ROI?
What's covered:
Synthetic retail data generation (104 weeks, 8 channels, 40+ external variables)
Adstock transformation with channel-specific decay rates
Log-log OLS regression with HC3 robust standard errors
External variable controls — holidays, macroeconomics, weather, sporting events
Sales decomposition: Baseline vs Media vs External factors
ROI by channel with elasticity estimates
Constrained budget optimisation using `scipy.optimize`
Real-world context:  
Built on experience delivering a closed-loop MMM framework for the UK's second largest grocery retailer (~£32bn revenue) — reducing reporting lag from 4–6 weeks to daily automated outputs (~90% time saving), with 15K+ campaigns evaluated.
📂 View Project | 📝 Read Medium Article
---
2. Multi-Touch Attribution
Business Problem: A customer sees a display ad on Monday, clicks a search ad on Wednesday, and converts after an email on Friday. How much credit does each touchpoint deserve?
What's covered:
Customer journey simulation across digital and offline touchpoints
Last-touch, first-touch, and linear attribution (baseline comparisons)
Shapley value attribution (game-theoretic, model-agnostic)
Markov chain attribution with removal effect
Channel-level ROI comparison across attribution models
📂 View Project | 📝 Read Medium Article
---
3. Price Elasticity Modelling
Business Problem: How sensitive are customers to price changes — and what's the optimal price point that maximises revenue while remaining competitive?
What's covered:
Price elasticity estimation using log-log regression
Cross-price elasticity (competitor effects)
Demand curve visualisation and interpretation
Discount optimisation — finding the minimum discount needed to win
Margin impact modelling under different pricing scenarios
Real-world context:  
Built on experience delivering a pricing strategy framework for a large pharmaceutical client, identifying ~$14M in annual margin improvement opportunity.
📂 View Project | 📝 Read Medium Article
---
4. Customer Segmentation
Business Problem: Not all loyal customers are the same. How do you identify which customer segments to target with which campaigns — and measure whether it worked?
What's covered:
RFM (Recency, Frequency, Monetary) feature engineering
K-Means clustering with elbow method and silhouette scoring
Segment profiling and business interpretation
Campaign targeting strategy by segment
A/B test design for measuring campaign uplift
Real-world context:  
Built on experience delivering customer segmentation and campaign analytics for the UK's largest grocery retailer across 20M+ Clubcard transaction records.
📂 View Project | 📝 Read Medium Article
---
Tech Stack
```python
# Core
pandas · numpy · scipy

# Modelling
statsmodels · scikit-learn

# Visualisation
matplotlib · seaborn

# Notebooks
jupyter
```
---
How to Run
```bash
# Clone the repo
git clone https://github.com/your-username/marketing-analytics-portfolio.git
cd marketing-analytics-portfolio

# Install dependencies
pip install pandas numpy scipy statsmodels scikit-learn matplotlib seaborn jupyter

# Launch Jupyter
jupyter notebook
```
Each notebook is fully self-contained — synthetic data is generated within the notebook, no external files needed.
---
Medium Series
Each project has a companion Medium article explaining the business context, methodology decisions, and real-world lessons learned:
How Market Mix Modeling Actually Works — A Practitioner's Guide
Multi-Touch Attribution: Beyond Last Click (coming soon)
Price Elasticity Modelling for Margin Optimisation (coming soon)
Customer Segmentation That Actually Drives Campaign ROI (coming soon)
---
Connect
If you work on marketing analytics, pricing, or data science in retail/CPG — I'd love to connect.
💼 LinkedIn
📝 Medium
📧 spshashankpaliwal@gmail.com
---
All data in this repository is synthetic and generated for demonstration purposes. No client or proprietary data is used.
