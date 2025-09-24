-- schema.sql
-- SQLite schema for Premarket Scanner Bot
-- Run with: sqlite3 scanner.db < schema.sql

PRAGMA foreign_keys = ON;

-- Table for scan results (multi-timeframe RSI + gap/volume data)
CREATE TABLE IF NOT EXISTS scans (
    id INTEGER PRIMARY KEY AUTOINCREMENT,
    timestamp DATETIME DEFAULT CURRENT_TIMESTAMP,
    ticker TEXT NOT NULL,
    gap_pct REAL,
    rel_vol REAL,
    rsi_1m REAL,
    rsi_5m REAL,
    rsi_15m REAL,
    rsi_1d REAL,
    overall_rsi REAL
);

-- Table for order records (live or paper)
CREATE TABLE IF NOT EXISTS orders (
    id INTEGER PRIMARY KEY AUTOINCREMENT,
    ticker TEXT NOT NULL,
    side TEXT CHECK(side IN ('BUY','SELL')),
    qty INTEGER,
    limit_price REAL,
    status TEXT,
    created_at DATETIME DEFAULT CURRENT_TIMESTAMP
);

-- Table for executed trades
CREATE TABLE IF NOT EXISTS trades (
    id INTEGER PRIMARY KEY AUTOINCREMENT,
    order_id INTEGER,
    entry_time DATETIME,
    exit_time DATETIME,
    pnl REAL,
    notes TEXT,
    FOREIGN KEY(order_id) REFERENCES orders(id) ON DELETE CASCADE
);
