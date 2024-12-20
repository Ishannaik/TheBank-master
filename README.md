# 💼💳 Banking App (✨The Bank✨)

This project is a full-stack 🛠️ banking application built with [Next.js](https://nextjs.org) 🚀 and Prisma 🏛️ for database management. It includes MySQL 🏦 as the database.

---

## ⚙️ Getting Started

### 🔢 Prerequisites
- [Node.js](https://nodejs.org) (🌱 LTS version recommended)
- [MySQL Server](https://dev.mysql.com/downloads/) 🏦
- [MySQL Workbench](https://dev.mysql.com/downloads/workbench/) ⚖️

---

### 🔄 Installation

1. 🔧 Clone the repository:
   ```bash
   git clone https://github.com/your-repo/the-bank.git
   cd the-bank
   ```

2. 📂 Install dependencies:
   ```bash
   npm install
   # or
   yarn install
   # or
   pnpm install
   ```

3. 🔎 Create a `.env` file in the root directory and add the following:

   ```env
   # 🛠️ Database Connection
   DATABASE_URL=mysql://<username>:<password>@localhost:3306/banking_app

   # 🌎 Your custom environment variables
   NEXT_PUBLIC_APP_NAME=The Bank
   ```

   Replace `<username>` and `<password>` with your MySQL 🔐 credentials.

4. 🌟 Start the development server:
   ```bash
   npm run dev
   ```

   Open [http://localhost:3000](http://localhost:3000) with your browser 🌐 to view the app.

---

## 🔧 Setting Up MySQL Server and MySQL Workbench

1. 🔄 Download and install [MySQL Server](https://dev.mysql.com/downloads/installer/).
   - During setup, create a user (e.g., `admin`) and password (e.g., `password`).

2. 🛠️ Open [MySQL Workbench](https://dev.mysql.com/downloads/workbench/).
   - Connect to the local MySQL server.
   - Create a new database:
     ```sql
     CREATE DATABASE banking_app;
     ```

3. 🔑 Grant permissions to your MySQL user:
   ```sql
   GRANT ALL PRIVILEGES ON banking_app.* TO 'admin'@'localhost';
   FLUSH PRIVILEGES;
   ```

---

## 🔧 Prisma Setup and Migration

1. 🏋️‍♂️ Validate the Prisma schema:
   ```bash
   npx prisma validate
   ```

2. 🏛️ Apply database migrations:
   ```bash
   npx prisma migrate dev --name init
   ```

   This will create the necessary tables (“User” and “Transaction”) in your database.

3. 🌍 Generate the Prisma Client:
   ```bash
   npx prisma generate
   ```

4. 🔍 Test the database connection:
   ```bash
   npx prisma db pull
   ```

---

## 🔎 Testing the App

1. 📅 Add a balance for an existing user (for testing):
   ```sql
   UPDATE User
   SET balance = 1000
   WHERE id = 'user_1';
   ```

2. 📈 Create two new accounts for testing:
   ```sql
   INSERT INTO User (id, email, balance) VALUES
   ('user_2', 'user2@example.com', 500),
   ('user_3', 'user3@example.com', 700);
   ```

3. 💳 Test transferring money between accounts using the app.

---

