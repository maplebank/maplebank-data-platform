# MapleBank Data Platform 🍁🏦

End-to-end data engineering pipeline for a fictional Canadian retail bank,
built on the modern Azure banking stack.

## Stack
- **PySpark on Databricks (serverless)** — Bronze → Silver → Gold Medallion Architecture
- **Delta Lake** — ACID, time travel, SCD Type 2 via MERGE
- **Unity Catalog volumes** — governed file storage
- **Azure Data Factory** — EOD batch orchestration
- **Talend** — ETL design patterns, PII masking

## Canadian Banking Compliance Focus
- **PIPEDA** — SIN masking (last-3 + hash), postal codes reduced to FSA
- **FINTRAC** — LCTR report for transactions ≥ CAD $10,000, structuring detection
- **OSFI** — audit trails, 7-year retention, Delta time travel for as-of queries

## Architecture
Sources (Core Banking, Interac, Cards) → Bronze (raw Delta) →
Silver (cleansed + PII-masked) → Gold (Customer 360, FINTRAC LCTR,
daily branch summary) → Data Mart → Power BI

## Repo Map
| Folder | Contents |
|--------|----------|
| `databricks/` | Bronze/Silver/Gold pipeline notebook |
| `sample-data/` | Synthetic data generator (no real PII) |
| `adf/` | Pipeline JSON |
| `docs/sessions/` | Training documentation PDFs |
| `interview-prep/` | Project pitch and Q&A |
