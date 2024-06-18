# PizzaSales

## Introduction
The PizzaSales project involves analyzing pizza sales data to extract various insights such as total orders, total revenue, popular pizza types, and more. This project utilizes SQL queries to perform data analysis on a pizza sales database.

## Table of Contents
1. [Introduction](#introduction)
2. [Installation](#installation)
3. [Usage](#usage)
4. [Features](#features)
5. [Dependencies](#dependencies)
6. [Configuration](#configuration)
7. [Documentation](#documentation)
8. [Examples](#examples)
9. [Troubleshooting](#troubleshooting)
10. [Contributors](#contributors)
11. [License](#license)

## Installation
To set up the PizzaSales project, follow these steps:
1. Ensure you have a SQL database system installed (e.g., MySQL, PostgreSQL).
2. Import the provided SQL files into your database.

```sh
mysql -u yourusername -p yourdatabase < PizzaSales\ 1.sql
mysql -u yourusername -p yourdatabase < PizzaSales\ 2.sql
# Repeat for all provided SQL files
```

## Usage
Execute the provided SQL queries to retrieve insights from the pizza sales data. Each file contains a specific query for different analyses. 

For example, to retrieve the total number of orders placed:
```sql
SELECT COUNT(order_id) AS total_orders FROM orders;
```

## Features
- Calculate total orders and total revenue
- Identify highest-priced and most common pizza
- List top 5 most ordered pizza types
- Analyze order distribution by hour and date
- Determine category-wise pizza distribution

## Dependencies
- A SQL database system (MySQL, PostgreSQL, etc.)

## Configuration
Ensure your database is configured to accept the schema used in the provided SQL files. Modify the connection settings as per your database configuration.

## Documentation
The provided SQL files perform the following analyses:

1. **PizzaSales 1.sql**: Retrieve the total number of orders placed.
2. **PizzaSales 2.sql**: Calculate the total revenue generated from pizza sales.
3. **PizzaSales 3.sql**: Identify the highest-priced pizza.
4. **PizzaSales 4.sql**: Identify the most common pizza size ordered.
5. **PizzaSales 5.sql**: List the top 5 most ordered pizza types along with their quantities.
6. **PizzaSales 6.sql**: Find the total quantity of each pizza category ordered.
7. **PizzaSales 7.sql**: Determine the distribution of orders by hour of the day.
8. **PizzaSales 8.sql**: Find the category-wise distribution of pizzas.
9. **PizzaSales 9.sql**: Calculate the average number of pizzas ordered per day.
10. **PizzaSales 10.sql**: Determine the top 3 most ordered pizza types based on revenue.
11. **PizzaSales 11.sql**: Calculate the percentage contribution of each pizza type to total revenue.
12. **PizzaSales 12.sql**: Analyze the cumulative revenue generated over time.
13. **PizzaSales 13.sql**: Determine the top 3 most ordered pizza types based on revenue for each pizza category.

## Examples
Here are a few example queries from the project:

To calculate the total revenue generated from pizza sales:
```sql
SELECT ROUND(SUM(order_details.quantity * pizzas.price), 2) AS total_sales
FROM order_details
JOIN pizzas ON pizzas.pizza_id = order_details.pizza_id;
```

To list the top 5 most ordered pizza types along with their quantities:
```sql
SELECT pizza_types.name, SUM(order_details.quantity) AS quantity
FROM pizza_types
JOIN pizzas ON pizza_types.pizza_type_id = pizzas.pizza_type_id
JOIN order_details ON order_details.pizza_id = pizzas.pizza_id
GROUP BY pizza_types.name
ORDER BY quantity DESC
LIMIT 5;
```

## Troubleshooting
- Ensure the SQL syntax is compatible with your database system.
- Verify the database schema matches the structure expected by the queries.

## Contributors
- [Naga Vineesha](nagavineesha18.v@gmail.com)

## License
This project is licensed under the MIT License.
