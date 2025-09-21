### JBank – Mini Banking Application in Java

## 📌 Overview

JBank is a mini banking application developed in Java that uses JDBC to connect and interact with a MySQL database.
It allows users to create accounts, log in, check balances, and transfer money securely.

This project demonstrates the use of Java, JDBC, and MySQL for handling user accounts and banking transactions.

## ⚙️ Features

# 📝 Create Account – Register a new user

# 🔑 Login – Securely log in to your account

# 💰 View Balance – Check your current account balance

# 🔄 Transfer Money – Send money to another customer account

# ✅ Transaction Management – Uses setAutoCommit(false), commit(), and rollback() to ensure reliable operations

## 🛠️ Prerequisites

Before running this project, ensure you have the following installed:

Java JDK (8 or later)

Eclipse IDE (or any Java IDE)

MySQL Database

MySQL JDBC Connector (JAR)

## 🔧 Setup Instructions

# 1. Clone the repository

git clone https://github.com/your-username/JBank.git
cd JBank

# 2. Create MySQL Database

CREATE DATABASE JBank;
USE JBank;

Example tables (you can expand as needed):

CREATE TABLE users (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(100),
    email VARCHAR(100) UNIQUE,
    password VARCHAR(100),
    balance DECIMAL(10,2) DEFAULT 0.00
);

CREATE TABLE transactions (
    id INT AUTO_INCREMENT PRIMARY KEY,
    sender_id INT,
    receiver_id INT,
    amount DECIMAL(10,2),
    timestamp TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    FOREIGN KEY (sender_id) REFERENCES users(id),
    FOREIGN KEY (receiver_id) REFERENCES users(id)
);

# 3. Update Database Configuration in Java
In your connection class (ConnectionProvider.java):

String url = "jdbc:mysql://localhost:3306/JBank";
String user = "root";
String pass = "your_mysql_password";

# 4. Add MySQL Connector JAR

   Download MySQL Connector/J
   Add it to your project’s build path in Eclipse.

# 5. Run the Application

Open Main.java in Eclipse.
Run the program to access the menu-driven console interface.

## 📖 How It Works

JDBC manages all database connections.

Each transaction (like money transfer) is handled as a unit of work.

If one step fails, the system rolls back changes to keep data consistent.

Users interact via a console-based menu system.

## 🚀 Future Enhancements

Add GUI interface with JavaFX or Swing

Implement encryption for storing passwords

Add admin module to manage customers

Provide mini statements and transaction history

## 🧑‍💻 Author

Developed by Aman Manwatkar as part of a Java mini project.
