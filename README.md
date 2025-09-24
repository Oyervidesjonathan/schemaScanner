# schemaScanner


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
