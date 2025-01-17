# Amazon-E-commerce-Database-Analysis


## Project Overview
This project involves designing and analyzing a relational database for an e-commerce platform. The database consists of nine interconnected tables, each designed to handle specific aspects of the business, such as product management, customer data, orders, payments, inventory, and shipping. By querying the database, insights were derived to answer key business questions and provide data-driven solutions.

## Objectives
- Design an Entity-Relationship Diagram (ERD) to model the e-commerce business data.
- Implement a relational database based on the ERD.
- Populate the tables with sample data to simulate real-world scenarios.
- Perform SQL queries to answer critical business questions, including customer behavior, sales performance, product analysis, and operational efficiency.

## Database Design
The database comprises the following tables, each with specific attributes and relationships:

### 1. Category
- **Primary Key**: `category_id`
- **Attributes**: `category_name`
- **Description**: Stores product category information to group similar products.

### 2. Products
- **Primary Key**: `product_id`
- **Attributes**: `product_name`, `price`, `cogs`, `category_id`
- **Relationships**: Linked to `Category` by `category_id`.
- **Description**: Manages product details, including pricing and cost of goods sold (COGS).

### 3. Inventory
- **Primary Key**: `inventory_id`
- **Attributes**: `product_id`, `stock`, `warehouse_id`, `last_stock_date`
- **Relationships**: Linked to `Products` by `product_id`.
- **Description**: Tracks stock levels and warehouse management.

### 4. Customers
- **Primary Key**: `customer_id`
- **Attributes**: `first_name`, `last_name`, `state`
- **Description**: Stores customer demographic information for segmentation and analysis.

### 5. Orders
- **Primary Key**: `order_id`
- **Attributes**: `order_date`, `customer_id`, `seller_id`, `order_status`
- **Relationships**: 
    - Linked to `Customers` by `customer_id`.
    - Linked to `Sellers` by `seller_id`.
- **Description**: Manages customer orders and their statuses.

### 6. Order Items
- **Primary Key**: `order_item_id`
- **Attributes**: `order_id`, `product_id`, `quantity`, `price_per_unit`
- **Relationships**:
    - Linked to `Orders` by `order_id`.
    - Linked to `Products` by `product_id`.
- **Description**: Tracks products included in each order.

### 7. Payments
- **Primary Key**: `payment_id`
- **Attributes**: `order_id`, `payment_date`, `payment_status`
- **Relationships**: Linked to `Orders` by `order_id`.
- **Description**: Records payment details for completed orders.

### 8. Shippings
- **Primary Key**: `shipping_id`
- **Attributes**: `order_id`, `shipping_date`, `return_date`, `shipping_providers`, `delivery_status`
- **Relationships**: Linked to `Orders` by `order_id`.
- **Description**: Tracks shipping and return details.

### 9. Sellers
- **Primary Key**: `seller_id`
- **Attributes**: `seller_name`, `origin`
- **Description**: Manages seller information for marketplace analysis.

## ERD (Entity-Relationship Diagram)
The ERD visually represents the database structure, including entities, attributes, and relationships. The diagram showcases how the tables are interconnected, ensuring efficient data management and integrity.

![ERD DIAGRAM]()

## Business Questions Answered
Using this database, I answered several key business questions, such as:
- **Sales Performance**: Which products generated the highest revenue?
- **Customer Insights**: What are the most active customer states?
- **Order Trends**: What is the average order size and frequency by month?
- **Product Analysis**: Which product categories have the highest demand?
- **Shipping Efficiency**: What percentage of orders are returned?
- **Inventory Management**: Which products are frequently out of stock?

## Tools and Technologies
- **Database Management System**: PostgreSQL
- **Database Design**: ERD created using DB design tools
- **Query Language**: SQL

## Key Features
- Normalized relational database design with nine tables.
- Comprehensive data model representing e-commerce operations.
- Efficient query performance for analytical insights.

## Future Work
- Incorporating data visualization tools to enhance insights.
- Adding time-series analysis for trends and forecasting.
