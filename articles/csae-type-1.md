# CSAE 34116 Type 1

### Technical Documentation required

| Item                                      | Description                                                           | Example |
|-------------------------------------------|-----------------------------------------------------------------------|---------|
| System architecture diagram               | A diagram that illustrates how data flows through the EDP system      | User interaction layer (data input via user actions) → Application layer (recording of trades, deposits, withdrawals, order matching engine, maintain financial balances [crypto & fiat]) → Data Storage layer (SQL/NoSQL database to store transaction history, user balances, audit logs, cold & hot wallets [linked to system but separate]) → External Services Layer (Blockchain API, Banking API, KYC/AML microservices) |
| Database architecture                     | A detailed description of the tables and relationships                | Define what tables exist (`transactions`, `accounts`, `users`, `audit_logs`), what fields each table contains (`transactions` table: `user_id`, `timestamp`, `amount`, `currency`) and their respective data types (`amount` is a decimal, `timestamp` is a datetime). Constraints & rules (`user_id` in `transactions` must match an existing ID in `accounts`). Define how tables relate to each other (a transaction must be linked to an account). Audit logs (if changes to financial data are logged, the `audit_logs` table should store who changed what and when). |
| Third-party integrations                  | APIs                                                                  | N/A     |
| Ledger and transaction processing logic   | How transactions are recorded & updated                               | N/A     |
| Data validation rules                     | How does your system prevent duplicate entries, rounding errors       | N/A     |
| Reconciliation processes                  | Automated vs manual reconciliation workflows                          | N/A     |
| User authentication & authorization       | Define if it is role-based, least privilege                           | N/A     |
| Database security policies                | Encryption and backup of data, retention policies                     | Include disaster recovery and data backup procedures |
| Logging & Monitoring setup                | System logs, anomaly detections                                       | N/A     |
| Version control and deployment            | How system changes are tracked                                        | How commits are handled in GitHub? |
| Software development lifecycle documentation | Documentation of SDLC processes                                      | N/A     |
| Report generation processes               | How financial reports are generated from the system                   | N/A     |
| Data export procedures                    | Formats, security measures when extracting financial data             | N/A     |
