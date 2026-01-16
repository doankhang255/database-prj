# 🛒 E-Commerce Database Management System (DBLAB PRJ)

> **Note on Project Focus**: This website is primarily built as a functional interface to test and demonstrate the logic of **SQL Stored Procedures**. The web interface is intentionally kept simple and minimal to prioritize the complexity and efficiency of the backend database architecture.
## 📌 Project Overview
This project is a comprehensive Lab study on E-commerce database design. The core objective is to offload critical business logic from the application layer to the **SQL Server** database using **Stored Procedures**, **Transactions**, and **Triggers**.

By utilizing a Node.js/EJS frontend, the system provides a manual testing dashboard to interact with the T-SQL logic in real-time.

## 🛠 Technical Architecture

### 1. Database Layer (SQL Server)
The backend is built with high-performance T-SQL techniques:
* **Security**: Implements `SHA2_256` password hashing directly within the database for user authentication.
* **Integrity & ACID**: Uses **SQL Transactions** during the checkout process to ensure data consistency across orders, inventory, and payments.
* **Automation**: **Triggers** are implemented to handle automated stock level updates and order status logging.
* **Dynamic Processing**: Uses `FOR JSON PATH` and `OPENJSON` to bridge the gap between relational data and JavaScript objects.

### 2. Application Layer (Node.js/Express)
The webapp serves as a testing harness for the database:
* **Database Connection**: Uses `mssql` connection pooling for efficient query execution.
* **Middleware**: Injects the SQL pool into requests to trigger Stored Procedures directly from UI actions.
* **View Engine**: Uses **EJS** to render dynamic data returned by the database.
* 
## 📂 Project Structure
Based on the `DBLAB PRJ` directory:

```text
DBLAB PRJ/
├── insertion/
│   ├── bulk_insert_products.sql   # Mass data seeding for testing
│   └── insert_data_mssql.sql      # Initial system configuration data
├── sql/
│   ├── create_tables_mssql.sql    # DDL: Database Schema
│   ├── create_indexes_mssql.sql   # Performance tuning for high-traffic tables
│   ├── create_triggers_mssql.sql  # Real-time data automation
│   ├── customer_mssql.sql         # Client-side logic (Cart, Checkout, Profile)
│   └── admin_mssql.sql            # Admin-side logic (Revenue, Inventory Reports)
├── webapp/
│   ├── src/
│   │   ├── views/                 # EJS templates for the simple UI
│   │   └── server.js              # Express server and SP route mapping
│   └── package.json
└── Documentation/                 # ERD Diagrams and Project Specs
