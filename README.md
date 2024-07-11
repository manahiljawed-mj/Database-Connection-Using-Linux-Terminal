# PostgreSQL Database Setup and Usage Guide 💻🔑📊

This guide will help you set up a PostgreSQL database on your Linux machine and perform basic operations.

## Installation

First, update your package list and install PostgreSQL:

```bash
sudo apt update
sudo apt install postgresql
```

## Access PostgreSQL

Access the PostgreSQL interactive terminal as the postgres user:

```bash
sudo -u postgres psql
```

## Create Database and Table

Create a new database (mydatabase) and a users table with some sample data:

```bash
CREATE DATABASE mydatabase;
```
```bash
\c mydatabase
```
```bash
CREATE TABLE users (
    id SERIAL PRIMARY KEY,
    username VARCHAR(50) UNIQUE NOT NULL,
    password VARCHAR(100) NOT NULL,
    email VARCHAR(100) UNIQUE NOT NULL,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
```
```bash
INSERT INTO users (username, password, email, created_at)
VALUES ('john_doe', 'password123', 'john.doe@example.com', CURRENT_TIMESTAMP);
```

## View Data
Retrieve and view data from the users table:

```bash
SELECT * FROM users;
```

## Change PostgreSQL User Password If Needed For Connecting it with Dbeaver or any other software

Change the password for the postgres user:

```bash
\password postgres
```
## Security Considerations

When using PostgreSQL or any database system, it's essential to follow best practices to ensure the security of your data:

### 1. Use Strong Passwords

Always use strong, complex passwords for database users and ensure they are not easily guessable.

### 2. Restrict Database Access

Limit database access to only those users and applications that require it. Avoid using default or overly permissive access settings.

#### Example of restricting access in PostgreSQL:

```sql
-- Grant access to a specific user
GRANT ALL PRIVILEGES ON DATABASE mydatabase TO myuser;

-- Revoke access from a user
REVOKE ALL PRIVILEGES ON DATABASE mydatabase FROM public;
```

### Contributions

Contributions and feedback are welcome! Please feel free to submit issues or pull requests.
