Company Branch and Employee Database
Overview
This work involves designing and building a relational database system for managing a company's data across multiple branches, employees, clients, and suppliers. It demonstrates how to define and manage relationships between entities using SQL. The database includes table creation, use of primary and foreign keys, and enforcement of relational integrity.

The SQL script is compatible with tools like MySQL Workbench, pgAdmin, or SQLiteStudio.

Purpose
The database is structured to manage information related to:

Employees and their supervisors

Company branches and their managers

Clients associated with each branch

Sales activities between employees and clients

Suppliers providing materials to branches

This setup supports various operations such as:

Identifying branch managers

Tracking employee-client sales relationships

Viewing reporting hierarchies

Listing suppliers linked to specific branches

Database Tables
employee
Stores personal and employment details of staff, including supervisor and branch associations.

branch
Represents company branches, including their names, manager IDs, and manager start dates.

client
Contains data about clients, each linked to a specific branch.

works_with
Maps employees to clients along with total sales figures, enabling many-to-many relationships.

branch_supplier
Links branches to suppliers and records the type of materials supplied, forming a many-to-many relationship.
