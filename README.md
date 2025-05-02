# SQL-Ecommerce-Order-Supply-Chain-Analytics-Project
## 1. Introduction & Motivation
In the fast-paced world of e-commerce, understanding customer behavior, optimizing supply chain processes, and improving delivery performance are crucial for business success. This project explores the E-Commerce Order and Supply Chain Dataset to uncover trends, inefficiencies, and business opportunities hidden in transactional and logistics data. The motivation behind this project is to simulate real-world analytics tasks using relational data and draw insights that can support operational and strategic decision-making in e-commerce businesses.  

---

## 2. Dataset Access
This dataset is publicly available on Kaggle:  
- **Dataset Title**: E-commerce Order & Supply Chain Dataset
- **Source**: Kaggle  
- **License**: Open for public use (refer to Kaggle page for detailed license)  
You can download the dataset directly via the Kaggle API or web interface.
---
## 3. Dataset Overview: Structure & Data Dictionary
The dataset contains 5 primary tables:

| Table Name         | Description                                                  |
|--------------------|--------------------------------------------------------------|
| `customers`        | Unique customer records with city, state, and zip code       |
| `orders`           | Master table containing order status, timestamps, and channel |
| `order_items`      | Order-level product details and seller info                 |
| `order_payments`   | Payment method and value per order                           |
| `order_reviews`    | Customer feedback, rating, and review comments               |

**Data Dictionary Preview**
| **Field Name**         | **Data Type** | **Description**                                                                 |
|------------------------|---------------|---------------------------------------------------------------------------------|
| `customer_id`          | STRING        | Unique identifier for each customer                                             |
| `order_id`             | STRING        | Unique identifier for each order                                                |
| `order_status`         | STRING        | Status of the order (delivered, shipped, etc.)                                  |
| `order_approved_at`    | DATETIME      | Timestamp when the order was approved                                           |
| `order_delivered_carrier_date` | DATETIME | When the order was handed to the logistics provider                            |
| `order_delivered_customer_date` | DATETIME | When the customer received the order                                           |
| `product_id`           | STRING        | Unique ID for each product in an order                                          |
| `seller_id`            | STRING        | Unique ID of the seller who sold the product                                    |
| `payment_type`         | STRING        | Type of payment used (credit card, boleto, etc.)                                |
| `payment_value`        | FLOAT         | Value of payment in Brazilian Real (R$)                                         |
| `review_score`         | INTEGER       | Score given by customer (1 to 5)                                                |
| `review_comment_title` | STRING        | Title of the review comment (if any)      

---
## 4. Project Goals / Business Problems
The primary objectives of this project are:

- Analyze **delivery performance** (on-time vs late delivery)
- Understand **payment behaviors** and their link to customer satisfaction
- Identify **high-performing sellers and products**
- Detect **pain points in the customer journey** using review and delivery timelines
- Provide actionable **recommendations** for improving operations and CX

---
## 5. Data Processing & Exploratory Data Analysis (EDA)
### 5.1 Analyze **delivery performance** (on-time vs late delivery)
**Query 01**:  
- SQL code:

- Results:




