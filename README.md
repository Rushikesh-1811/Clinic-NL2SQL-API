# Clinic-NL2SQL-API
A production-grade Natural Language to SQL (NL2SQL) backend built for a simulated Clinic Management System. This API allows users to query complex relational data using plain English, automatically translating intent into secure, executable SQLite queries.

This project strictly implements the Vanna 2.0 Autonomous Agent Architecture combined with a highly optimized FastAPI endpoint layer for seamless front-end integration.

# ✨ Key Technical Features
Advanced Component Parsing: Implements an asynchronous FastAPI stream parser that hunts for and extracts raw SQL markdown and DataFrame objects natively from Vanna's UiComponent wrapper, scrubbing out LLM system noise for pristine JSON payloads.
Hardened Security Middleware: Features a custom SecureSqliteRunner transparent proxy. This intercepts internal tool calls to validate that generated SQL is strictly SELECT-based and contains no destructive (DROP, DELETE) or system-level (sqlite_master) keywords before execution.
Few-Shot Memory Seeding: Utilizes Vanna's local DemoAgentMemory system, pre-seeded with 15 highly complex Q&A pairs (handling multi-table JOINs, temporal grouping, and mathematical aggregations) to ensure high-accuracy zero-shot inference.
Legacy-Compatible Payloads: Dynamically structures the Pandas DataFrame output into clean columns, rows, and row_count arrays to support standard enterprise charting libraries.
