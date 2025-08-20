# Backend – Node.js + Express + SQLite

This folder is where you build your API (the backend) using **Express** and **SQLite**.

## 📦 What You Will Build

- An API route `/quotes` that returns a list of quotes
- A random quote route `/quotes/random`
- A SQLite database to store quotes

## 🛠️ How to Start

1. Open the `backend` folder in VS Code
2. Open terminal (View → Terminal)
3. Run:

   npm init -y  
   npm install express better-sqlite3

4. Create a file called `index.js`
5. Add this example:

   const express = require('express');  
   const Database = require('better-sqlite3');  
   const app = express();  
   const db = new Database('quotes.db');  
   const PORT = 3000;

   app.get('/quotes', (req, res) => {
     const stmt = db.prepare('SELECT * FROM quotes');  
     const quotes = stmt.all();  
     res.json(quotes);  
   });

   app.listen(PORT, () => {
     console.log(`Server running on http://localhost:${PORT}`);  
   });

6. Run your server:

   node index.js

7. Visit in browser:  
   http://localhost:3000/quotes

You should see the quotes if your database is set up.

---

## 🔁 Git Steps (in VS Code)

Do this for every new task:

1. Go to Git icon  
2. Make sure you’re on `main`  
3. Click 3 dots (⋮) → “Checkout to…” → “Create new branch”  
4. Name it like: `feature/quotes-api`
5. Make changes
6. Stage files, write commit message:  
   `Create /quotes API from SQLite`
7. Commit ✅ → Publish Branch → Open PR
