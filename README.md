# E-Commerce-Data-Preparation-Insights
Data preparation on real-world Brazilian ecommerce public dataset  made for category-level Masrket Basket Analysis

## Repository Structure
- `data_preparation.ipynb` — main Python file
- `data/raw/` — original CSVs (unmodified)
- `data/processed/` — final table for Tableau
- `MBA_Olist.twbx` — Tableau packaged workbook

## Data
Source: [Brazilian E-Commerce Public Dataset by Olist.](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce/data)

Orders made at [Olist store](https://www.olist.com/) (Brazil) in 2016 to 2018. Collection methodology: Random Sampling.

## Key Metrics 
Market Basket Analysis relies on a few standard metrics to evaluate the strength of associations between items:

- Frequency – the raw count of how many times an item (or item pair) occurs in the dataset. 
- Support – the proportion of all transactions that include a given item or item pair.
 `Support(A ⇒ B) = (Transactions containing A and B) / (Total Transactions)`
- Confidence – the conditional probability that a transaction containing item A also contains item B.
 `Confidence(A ⇒ B) = (Transactions containing A and B) / (Transactions containing A​)`
- Lift – a measure of how much more likely items A and B occur together than if they were independent.
  `Lift(A ⇒ B) = Support(A ⇒ B)/(Support(B) * Support (A)​)`.
Lift > 1 indicates a positive association (complementary products). Lift < 1 indicates a negative association (substitudes). Lift = 1: Product A and Product B are randomly ordered together.

Together, these metrics highlight not just how often items co-occur, but whether their co-occurrence is stronger than chance.


## Possible Next Steps
- Aggregate categories into broader groups to increase support.
- Olist full product-level MBA (instead of category-level) — more pairs, but will be still sparse.
- Investigate data collection bias — it’s possible the dataset reflects a preference for single-product or single-category orders (e.g., promotional setup, platform-specific ordering habits).
