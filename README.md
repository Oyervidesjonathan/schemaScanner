# schemaScanner
This file defines the SQLite database structure for the Premarket Scanner Bot. It includes three main tables:

scans → Stores ticker scan results, gap %, relative volume, and multi-timeframe RSI values.

orders → Records order details such as ticker, side (BUY/SELL), quantity, price, and status.


premarket-scanner-bot/
├─ premarket_scanner_bot.py
├─ db.py
├─ schema.sql        <-- database schema (this file)
├─ config.example.yml
├─ .env.example
├─ requirements.txt
├─ README.md
└─ .gitignore
Then in your README.md, add a setup section like:

bash
Copy code
# Initialize the database from schema.sql
sqlite3 scanner.db < schema.sql
