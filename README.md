# Online-food-delivery-service-testtask-

# 🍔 Online Food Delivery Service Database Schema

This repository contains the complete database design for an online food delivery service, including the Entity-Relationship Diagram (ERD) and the SQL Data Definition Language (DDL) script.

---

## 💡 Project Overview

The database is designed to manage all core operations of a food delivery platform, connecting **Customers**, **Restaurants**, **Menu Items**, **Orders**, and **Delivery Drivers**.

### Key Entities:

* **Customers**: User accounts for placing orders.
* **Addresses**: Stores multiple delivery locations per customer.
* **Restaurants**: The vendors providing the food.
* **Menu_Items**: Specific products offered by each restaurant.
* **Delivery_Drivers**: Personnel responsible for delivering orders.
* **Orders**: The transaction record linking the customer, restaurant, and driver.
* **Order_Items**: A detail table capturing the items and quantities within an order.
* **Payments**: Records for completed or attempted transactions.

---

## 🖼️ Entity-Relationship Diagram (ERD)

The following diagram visually represents all entities, their attributes, and the defined relationships (One-to-One, One-to-Many, Many-to-Many) of the food delivery system schema.



---

## ⚙️ Database Schema Details

The schema is implemented using standard SQL DDL (Data Definition Language) with considerations for **referential integrity** (Foreign Keys) and **data validation** (Constraints).

### 1. Relationships Summary

| Relationship | Type | Connecting Entities | Foreign Key (FK) Locations |
| :--- | :--- | :--- | :--- |
| Customer to Address | One-to-Many | Customers ↔ Addresses | `Addresses.customer_id` |
| Restaurant to Menu | One-to-Many | Restaurants ↔ Menu\_Items | `Menu_Items.restaurant_id` |
| Order to Customer/Restaurant/Driver | Many-to-One | Orders → (Customers, Restaurants, Drivers) | `Orders.customer_id`, `Orders.restaurant_id`, `Orders.delivery_driver_id` |
| Order to Order\_Items | One-to-Many | Orders ↔ Order\_Items | `Order_Items.order_id` |
| Order to Payment | One-to-One | Orders ↔ Payments | `Payments.order_id` (Unique) |

### 2. File Contents

| File | Description |
| :--- | :--- |
| `food_delivery_schema.sql` | Contains the complete `CREATE TABLE` statements with primary keys, foreign keys, and constraints. |
| `README.md` | This documentation file, including the ERD. |

---

## 🚀 Getting Started

To set up the database:

1.  **Clone the Repository:**
    ```bash
    git clone [Your Repository URL]
    ```
2.  **Execute the Script:**
    Load the `food_delivery_schema.sql` file into your preferred relational database management system (RDBMS) like PostgreSQL, MySQL, or SQL Server.
    ```bash
    # Example for PostgreSQL using psql
    psql -U your_user -d your_database -f food_delivery_schema.sql
    ```

The tables will be created, establishing the necessary structure and relationships for the application backend.
