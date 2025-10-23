# E-commerce Orders Cleanroom (PySpark)

**Problem →** ML team needs a clean orders table for demand forecasting.  
**Input →** `orders_data.parquet` (raw)  
**Output →** `orders_data_clean.parquet` (curated)

**Cleaning spec (implemented):**
- Drop orders placed **00:00–05:00 inclusive**.
- Convert `order_date` from timestamp → **date**.
- Add `time_of_day`: **morning** [05:00–12:00), **afternoon** [12:00–18:00), **evening** [18:00–24:00).
- Remove any product whose name contains **“TV”** (case-insensitive).
- Force lowercase for `product` and `category`.
- Derive `purchase_state` from `"House Street, City, State Zip"`.
