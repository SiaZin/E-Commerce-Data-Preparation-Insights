# Data Notes

## Raw
- `olist_order_items_dataset.csv` — order-product lines 
- `olist_products_dataset.csv` — products metadata 
- `product_category_name_translation.csv` — Portuguese → English mapping 

## Processed
- `olist_orders.csv` — final table:
  - `order_id` (str)
  - `product_id` (str)
  - `product_category_name_english` (str)
  - `quantity` (int)

## Data source 
- [Brazilian E-Commerce Public Dataset by Olist.](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce/data)
 The dataset has information of 100k orders from 2016 to 2018 made at multiple marketplaces in Brazil.
This is real commercial data, it has been anonymised, and references to the companies and partners in the review text have been replaced with the names of Game of Thrones great houses.
