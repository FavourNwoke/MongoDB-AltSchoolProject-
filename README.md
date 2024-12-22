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

 Steps to Run Scripts
1.	Set Up Environment:
o	Install MongoDB (local or Atlas).
o	Install Python dependencies:
pip install pymongo

3.	Run the Scripts:
o	Use the provided Python scripts to:
	Create collections and insert sample data.
	Execute queries and aggregation pipelines.

4.	Execute Analytical Queries:
o	Modify queries as needed based on analysis goals.

5. Analytical Findings
1.	Revenue Analysis:
o	Total Revenue: $200,000 (example value).
o	Highest Revenue Category: Electronics.
# Query to find highest revenue category
pipeline = [
    {"$lookup": { ... }},
    {"$unwind": "$product_orders"},
    {"$group": { ... }},
    {"$sort": {"total_revenue": -1}}
]

2.	Customer Insights:
o	Top Customer by Spending: Alice Smith.
o	Inactive Customers: Bob Jones (no orders).

# Query to find inactive customers
db.customers.aggregate([
    {"$lookup": { ... }},
    {"$match": {"orders": {"$size": 0}}}
])

3.	Product Trends:
o	Top-Selling Product: Laptop.
o	Out-of-Stock Products: None.

5. Advanced Concepts
1.	Transactions: Simulated atomic updates to orders and product inventory.

with client.start_session() as session:
    with session.start_transaction():
        db.orders.insert_one({ ... }, session=session)
        db.products.update_one({ ... }, session=session)
2.	Change Streams: Monitored real-time changes in the orders collection to detect new orders or status changes.

6. Key Insights
•	Revenue Distribution: Electronics contributed to 80% of total revenue.
•	Customer Spending: The top 5% of customers accounted for 50% of sales.
•	Product Inventory: No products were out of stock during the analysis period.

7. Conclusion
This project demonstrates the application of MongoDB for managing and analyzing e-commerce data. It highlights the benefits of schema design, indexing, and advanced MongoDB features for data-driven insights.


