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


## Key Steps (Short)
1. Inspect & validate raw tables (types, nulls, duplicates).
2. Add `quantity`, aggregate `(order_id, product_id)` to one row.
3. Drop products with missing categories; join category translations.
4. Build final table: `order_id`, `product_id`, `product_category_name_english`.
5. Explore multi-category orders; result: ~0.75% of orders have >1 category.

## Findings (Short)
- Orders are overwhelmingly single-category → sparse co-occurrences.
- MBA metrics (lift/confidence) unstable for most pairs due to low support.

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

## Possible actions 
- Aggregate categories into broader groups to increase support.
- Olist full product-level MBA (instead of category-level) — more pairs, but will be still sparse.
- Investigate data collection bias — it’s possible the dataset reflects a preference for single-product or single-category orders (e.g., promotional setup, platform-specific ordering habits).

## Next Step
I have made s separate MBA project using a dataset with richer, multi-item baskets to demonstrate meaningful association rules. This project remains published here as an example of data preparation and exploratory analysis for real-world datasets.
