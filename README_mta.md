# 🎯 Multi-Touch Attribution (MTA) — End-to-End Python Implementation

> Part of the [Marketing Analytics Portfolio](../)  
> **Domain:** Retail / CPG | **Technique:** Game Theory · Probabilistic Modelling  
> **Author:** Shashank Paliwal | [LinkedIn](https://linkedin.com/in/shashank-paliwal-ba1ba171) | [Medium Article](#)

---

## Business Problem

A customer sees a TV ad, clicks a digital display ad, receives a loyalty coupon, and converts in-store. **Which channel deserves the credit?**

Last Touch attribution gives 100% to the final touchpoint — systematically overvaluing conversion channels (coupons, email) and undervaluing awareness channels (TV, OOH). This leads to budget decisions that kill the top of the funnel while over-investing in the bottom.

This notebook implements 6 attribution models — from simple rule-based to advanced data-driven — and shows exactly how budget decisions change depending on which model you trust.

---

## What This Notebook Covers

| Section | Description |
|---------|-------------|
| **1. Journey Simulation** | 50,000 customer journeys across 8 channels with realistic conversion probabilities |
| **2. EDA** | Touchpoint frequency, journey length distribution, conversion rate by channel |
| **3. Rule-Based Models** | Last Touch, First Touch, Linear, Time Decay |
| **4. Shapley Values** | Game-theoretic marginal contribution across all channel coalitions |
| **5. Markov Chain** | Transition matrix + removal effect per channel |
| **6. Model Comparison** | Heatmap + grouped bar comparing all 6 models |
| **7. Budget Implications** | How attribution choice shifts budget allocation |
| **8. Key Takeaways** | When to use each model + MTA vs MMM |

---

## Channels Modelled

| Type | Channels |
|------|---------|
| **Offsite (4)** | TV, Digital Display, OOH, Radio |
| **Onsite (4)** | Email, Loyalty Coupon, In-store Display, Leaflet |

---

## Methodology

### Shapley Value Attribution

From cooperative game theory — each channel's credit = its average marginal contribution across all possible channel coalitions:

$$\phi_i = \sum_{S \subseteq N \setminus \{i\}} \frac{|S|!(|N|-|S|-1)!}{|N|!} [v(S \cup \{i\}) - v(S)]$$

- Theoretically the fairest attribution model
- Captures channel interactions (TV + Digital together > TV + Digital separately)
- For 8 channels: 2⁸ = 256 coalitions evaluated per channel

### Markov Chain Attribution

Models the journey as probabilistic state transitions:

1. Build transition matrix from observed journey sequences
2. Simulate baseline conversion probability via random walks
3. Remove each channel and recalculate conversion probability
4. **Removal effect** = drop in conversion probability = channel's credit

---

## Key Finding

Last Touch systematically overvalues conversion channels and undervalues awareness channels. Moving from Last Touch to Shapley attribution typically shifts **15–25% of budget** between channels — a multi-million pound decision for large retailers.

---

## Real-World Context

Built on experience delivering MTA frameworks alongside MMM for large UK grocery and CPG clients:

- **Complementary to MMM** — MTA handles digital individual-level tracking; MMM handles offline aggregate attribution
- **A/B test validation** — MTA results validated against holdout experiments
- **Journey scale** — implemented on datasets of millions of customer journeys

*All data in this notebook is synthetic. No client or proprietary data is used.*

---

## How to Run

```bash
pip install pandas numpy matplotlib seaborn scikit-learn jupyter
jupyter notebook multi_touch_attribution.ipynb
```

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](#)

---

## Related Projects

| Project | Link |
|---------|------|
| Market Mix Modeling (MMM) | [01_market_mix_modeling/](../01_market_mix_modeling/) |
| Price Elasticity | [03_price_elasticity/](../03_price_elasticity/) *(coming soon)* |
| Customer Segmentation | [04_customer_segmentation/](../04_customer_segmentation/) *(coming soon)* |

---

## Connect

- 💼 [LinkedIn](https://linkedin.com/in/shashank-paliwal-ba1ba171)
- 📝 [Medium Article — Multi-Touch Attribution: Why Last Click Is Lying to You](#)
- 📧 spshashankpaliwal@gmail.com
