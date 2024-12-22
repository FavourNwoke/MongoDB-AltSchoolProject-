E-Commerce Data Analysis

This project demonstrates the application of MongoDB for managing and analyzing e-commerce data. It highlights the benefits of schema design, indexing, and advanced MongoDB features for data-driven insights.

This project demonstrates database modeling, querying, and analytics on an e-commerce platform using MongoDB. The system manages data about customers, products, orders, and order items, enabling insights such as revenue analysis, product trends, and customer insights.

Schema Design
1.	Collections:
o	customers: Contains information about customers.
o	products: Contains product details.
o	orders: Tracks customer orders.
o	order_items: Tracks specific items within an order.
2.	Design Decisions:
o	Referencing: Used for linking orders and products for scalability.
o	Embedding: Used for nested fields like customer addresses for simplicity.
3.	Indexes:
o	Indexes were added to frequently queried fields like customer_id and product_id to improve query performance.

