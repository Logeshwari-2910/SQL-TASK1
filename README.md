# Company Branch and Employee Database

## Overview

This work involves designing and building a relational database system for managing a company's data across multiple branches, employees, clients, and suppliers. It demonstrates how to define and manage relationships between entities using SQL. The database includes table creation, use of primary and foreign keys, and enforcement of relational integrity.

The SQL script is compatible with tools like MySQL Workbench, pgAdmin, or SQLiteStudio.

## Purpose

The database is structured to manage information related to:

* Employees and their supervisors
* Company branches and their managers
* Clients associated with each branch
* Sales activities between employees and clients
* Suppliers providing materials to branches

This setup supports various operations such as:

* Identifying branch managers
* Tracking employee-client sales relationships
* Viewing reporting hierarchies
* Listing suppliers linked to specific branches

## Database Tables

1. **employee**
   Stores personal and employment details of staff, including supervisor and branch associations.

2. **branch**
   Represents company branches, including their names, manager IDs, and manager start dates.

3. **client**
   Contains data about clients, each linked to a specific branch.

4. **works\_with**
   Maps employees to clients along with total sales figures, enabling many-to-many relationships.

5. **branch\_supplier**
   Links branches to suppliers and records the type of materials supplied, forming a many-to-many relationship.

## Relationships

* **Branch → Employee (One-to-Many)**: One branch can have many employees; each employee belongs to one branch.

* **Branch → Client (One-to-Many)**: One branch can serve many clients; each client is linked to one branch.

* **Employee → Employee (Self-Referencing One-to-Many)**: An employee can have one supervisor; a supervisor can manage many employees.

* **Employee ↔ Client (Many-to-Many via `works_with`)**: Employees can work with multiple clients, and clients can be handled by multiple employees.

* **Branch ↔ Supplier (Many-to-Many via `branch_supplier`)**: Branches can have multiple suppliers; a supplier can supply multiple branches.

Foreign keys and constraints (e.g., `ON DELETE SET NULL`, `ON DELETE CASCADE`) are used to maintain data consistency across tables.


##  **Normalization in the Schema**

1. **1NF (First Normal Form)** 

   * All table columns contain **atomic (indivisible) values**.
   * There are **no repeating groups or arrays**.
   * Example: In `employee`, columns like `first_name`, `salary`, etc., hold single values.

2. **2NF (Second Normal Form)**

   * The schema is in 1NF and **all non-key columns are fully dependent on the entire primary key**.
   * Example: In `works_with`, the `total_sales` depends on both `emp_id` and `client_id` together (composite key).

3. **3NF (Third Normal Form)** 

   * It’s in 2NF and **no transitive dependencies** exist (non-key columns don't depend on other non-key columns).
   * Example: In `branch`, the `branch_name` and `mgr_start_date` depend only on `branch_id`, not on `mgr_id`.



## Usage Instructions

1. Open a supported SQL tool (e.g., MySQL Workbench, pgAdmin).
2. Execute the SQL script to create the database schema.
3. Use `SELECT` queries to explore and test relationships and constraints.

## Concepts Covered

* Creating tables using SQL DDL
* Defining primary and foreign keys
* Implementing self-referencing relationships
* Managing many-to-many relationships via junction tables
* Enforcing referential integrity with constraints
* Understanding relational schema design and normalization



