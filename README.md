# SQL-Ecommerce-Order-Supply-Chain-Analytics-Project
## 1. Introduction & Motivation
In the fast-paced world of e-commerce, understanding customer behavior, optimizing supply chain processes, and improving delivery performance are crucial for business success. This project explores the E-Commerce Order and Supply Chain Dataset to uncover trends, inefficiencies, and business opportunities hidden in transactional and logistics data. This project aims to simulate real-world analytics tasks using relational data and draw insights that can support operational and strategic decision-making in e-commerce businesses.  

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
| `Customers`        | Unique customer records with city, state, and zip code       |
| `Orders`           | Master table containing order status, timestamps, and channel |
| `Order_items`      | Order-level product details and seller info                 |
| `Payments`   | Payment method and others information                          |
| `Products`    | Information about products               |

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
**Query 01**:  What is the average delivery days of orders, and the proportion of each order status?
- SQL code:  
![image](https://github.com/user-attachments/assets/90b9649f-d95d-4f25-b38a-4d1926c4c9bd)
- Results: 
![image](https://github.com/user-attachments/assets/db0baead-0c51-42dd-b330-5dd9897a0a79)
- SQL code:  
![image](https://github.com/user-attachments/assets/99c7fbbe-443a-452c-900f-4c1dc61ebb59)
- Results:  
![image](https://github.com/user-attachments/assets/412c7b41-7aa6-4141-8af4-602f95e5bf65)

**Query 02**:  Is there a large difference in delivery success rates between states?
- SQL code:  
![image](https://github.com/user-attachments/assets/a7c6386e-a094-4384-8b32-80e3e178d3e8)

- Results:  
![image](https://github.com/user-attachments/assets/54069ba5-8fd4-4ca4-9b27-170bd14b1c31)

**Query 03**: Observe over time, are there any unusual incidents in the successful delivery rate?
- SQL code:
![image](https://github.com/user-attachments/assets/604f9e1b-f456-4848-85d8-6e611f62b20e)

- Results:  
![image](https://github.com/user-attachments/assets/2d8dc641-07b0-4eb1-82b7-4ca7f789104c)

**Query 04**: Top 3 best seller_id each state ? 
- SQL code:  
![image](https://github.com/user-attachments/assets/55229159-3482-4ffc-ad41-2a34a424aa12)
- Results:  
![image](https://github.com/user-attachments/assets/6ee56144-fcdd-446c-9b0b-473b600fb272)

**Query 05**: Payment trends over time
- SQL code:
![image](https://github.com/user-attachments/assets/ad98544e-9242-4b71-ba9b-4524d7033689)
- Results:  
![image](https://github.com/user-attachments/assets/41d6e5c1-9ae7-48fa-ac1b-f179dced22dc)
---
## 6. Key Insights & Recommendations
### 1. Delivery Days vs Average Delivered Day  
**Insights:**
- The average delivery time is set as 12 days.  
- Some orders are delivered significantly earlier (e.g., 2, 4, 6 days).  
- Some outliers exist with high delivery durations (> 38, 44 days).  

**Recommendations:**
- Investigate reasons behind delayed deliveries (e.g., seller processing time, shipping partner issues).  
- Set up alerts for unusually long delivery times (e.g., over 20 days).  
- Optimize logistics or offer shipping options to reduce average delivery time.

### 2. Customer State and Success Rate
**Insights:**
- Most states have a high delivery success rate (96–99%).
- States like MA (96.79%) and PI (96.69%) are at the lower end.

**Recommendations:**
- Identify infrastructure or logistical bottlenecks in lower-performing states.
- Partner with more reliable local delivery services in those areas.
- Offer customer incentives in regions with lower satisfaction to boost loyalty.
### 3. Monthly Orders and Delivery Rate
**Insights:**
- Delivery success rate improved over time, especially in 2017–2018 (most months >96%).
- The highest order volume was seen in late 2017 and 2018.
- Data from 2016 has very few orders—likely before scaling.

**Recommendations:**
- Continue monitoring monthly delivery success trends to catch drops early.
- Investigate what drove order growth in 2017–2018 and try to replicate it.
- Maintain or improve order handling capacity during high-volume months (e.g., holidays).
### 4. Top Sellers by State
**Insights:**
- The distribution of sellers per state is relatively balanced.

**Recommendations:**
- Promote high-performing sellers in other regions.
- Reward consistent performers with seller incentives or visibility boosts.
- Consider seller diversity in each state to avoid dependency on a few.

### 5. Payment Type Distribution
**Insights:**
- Credit cards are the dominant payment method (73.69%).
- Wallet usage (19.37%) is also significant.
- Vouchers and debit cards make up a small portion.

**Recommendations:**
- Promote wallet payments with cashback or discounts to reduce credit card processing fees.
- Understand why debit card usage is low — are there usability or trust issues?
- Use insights for marketing campaigns — e.g., partner with wallet providers.


