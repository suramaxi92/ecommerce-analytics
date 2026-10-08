# Data Dictionary

## Orders Table

| Column | Description | Data Type | Role |
|---|---|---|---|
| order_id | Unique identifier for an order | String | Primary Key |
| customer_id | Identifier linking the order to a customer record | String | Foreign Key |
| order_status | Current status of the order | String | Attribute |
| order_purchase_timestamp | Date and time when the order was placed | String | Timestamp |
| order_approved_at | Date and time when the order payment was approved | String | Timestamp |
| order_delivered_carrier_date | Date and time when the order was handed to the carrier | String | Timestamp |
| order_delivered_customer_date | Date and time when the order was delivered to the customer | String | Timestamp |
| order_estimated_delivery_date | Estimated delivery date provided for the order | String | Date |

## Customers Table

| Column | Description | Data Type | Role |
|---|---|---|---|
| customer_id | Identifier for a customer record associated with an order | String | Primary Key |
| customer_unique_id | Identifier representing the underlying unique customer | String | Customer Identifier |
| customer_zip_code_prefix | ZIP-code prefix of the customer location | Integer | Attribute |
| customer_city | City of the customer | String | Attribute |
| customer_state | State of the customer | String | Attribute |

## Order Items Table

| Column | Description | Data Type | Role |
|---|---|---|---|
| order_id | Identifier linking the item to an order | String | Foreign Key |
| order_item_id | Sequential identifier of an item within an order | Integer | Item Identifier |
| product_id | Identifier of the purchased product | String | Foreign Key |
| seller_id | Identifier of the seller who sold the product | String | Foreign Key |
| shipping_limit_date | Date and time by which the seller should ship the item | String | Timestamp |
| price | Price of the purchased item | Float | Measure |
| freight_value | Shipping/freight cost associated with the item | Float | Measure |

## Products Table

| Column | Description | Data Type | Role |
|---|---|---|---|
| product_id | Unique identifier for a product | String | Primary Key |
| product_category_name | Product category in the original Portuguese naming | String | Attribute |
| product_name_lenght | Length of the product name | Float | Attribute |
| product_description_lenght | Length of the product description | Float | Attribute |
| product_photos_qty | Number of photos associated with the product | Float | Attribute |
| product_weight_g | Product weight in grams | Float | Attribute |
| product_length_cm | Product length in centimeters | Float | Attribute |
| product_height_cm | Product height in centimeters | Float | Attribute |
| product_width_cm | Product width in centimeters | Float | Attribute |

## Sellers Table

| Column | Description | Data Type | Role |
|---|---|---|---|
| seller_id | Unique identifier for a seller | String | Primary Key |
| seller_zip_code_prefix | ZIP-code prefix of the seller location | Integer | Attribute |
| seller_city | City where the seller is located | String | Attribute |
| seller_state | State where the seller is located | String | Attribute |

## Payments Table

| Column | Description | Data Type | Role |
|---|---|---|---|
| order_id | Identifier linking the payment to an order | String | Foreign Key |
| payment_sequential | Sequence number of the payment within an order | Integer | Attribute |
| payment_type | Payment method used by the customer | String | Attribute |
| payment_installments | Number of installments used for the payment | Integer | Attribute |
| payment_value | Monetary value of the payment | Float | Measure |

## Reviews Table

| Column | Description | Data Type | Role |
|---|---|---|---|
| review_id | Unique identifier for a review | String | Primary Key |
| order_id | Identifier linking the review to an order | String | Foreign Key |
| review_score | Customer rating for the order | Integer | Measure |
| review_comment_title | Title of the customer's written review | String | Attribute |
| review_comment_message | Written message provided by the customer | String | Attribute |
| review_creation_date | Date when the review was created | String | Date |
| review_answer_timestamp | Date and time when the review was answered | String | Timestamp |

## Geolocation Table

| Column | Description | Data Type | Role |
|---|---|---|---|
| geolocation_zip_code_prefix | ZIP-code prefix associated with the geographic record | Integer | Attribute |
| geolocation_lat | Latitude of the geographic location | Float | Attribute |
| geolocation_lng | Longitude of the geographic location | Float | Attribute |
| geolocation_city | City associated with the geographic record | String | Attribute |
| geolocation_state | State associated with the geographic record | String | Attribute |

## Category Translation Table

| Column | Description | Data Type | Role |
|---|---|---|---|
| product_category_name | Product category name in Portuguese | String | Key |
| product_category_name_english | English translation of the product category | String | Attribute |

