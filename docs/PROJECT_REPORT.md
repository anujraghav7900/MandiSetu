# MandiSetu — Project Report
## 1. Vision
MandiSetu is a market-intelligence and transaction-enablement platform bridging the information gap between smallholder farmers/FPOs and buyers. It combines transparent price discovery with cost-aware sale decisions and a trust-verified transaction layer.
## 2. Problem statement
Farmers may see a headline price without knowing the net amount after transport, commission, storage and other costs. They may lack reliable historical market context, trusted buyer information, aggregation options and transparent order/dispute records.
## 3. Objectives
- Aggregate live and historical mandi prices with source/date/market details.
- Forecast short-term price trends and estimate suitable sale windows.
- Compare net realization across offers and include all major selling costs.
- Support digital produce lots, structured quality details and verification.
- Represent verified buyers and explainable reliability indicators.
- Enable FPO aggregation, logistics coordination, transaction tracking and dispute resolution.
## 4. Technology
Frontend: React + Vite + CSS. Backend starter: Node.js + Express REST API. Database starter: MySQL. Future ML service: Python, pandas and scikit-learn. Market, weather, maps and payment integrations are future integrations.
## 5. Pages
1. Market Overview — high-level lot, buyer and transaction snapshot.
2. Market Intelligence — sample lot price board and illustrative history; no live mandi feed.
3. Sell-Time Advisor — compares current price with user-entered later scenario less holding cost; not an ML forecast.
4. Net Realization — quantity × offer price less transport, commission, storage and other costs.
5. Digital Lots & Quality — creates local demo lots with variety, grade, quantity and location; no actual certification.
6. Buyer Network — sample profiles and illustrative scores; no real verification.
7. FPO Aggregation — quantity aggregation preview; no persistent member contribution/consent.
8. Logistics — local delivery status controls; no carrier quotes/GPS.
9. Transactions & Disputes — demo order records and local dispute form; no payments or persistence.
10. Admin & Trust Center — sample verification queue and dispute oversight.
## 6. Architecture
React browser UI → planned Express API → MySQL. Optional future services: official market data ingestion, Python forecasting service, maps/logistics, weather, payment provider and notification service. Current frontend state is not wired to the API.
## 7. Database
Schema tables: users, fpos, fpo_members, produce_lots, quality_checks, market_prices, price_forecasts, buyers, fpo_aggregations, aggregation_contributions, transactions, cost_estimates, logistics, disputes and audit_logs. Foreign keys connect lots, users, orders and related records.
## 8. Net realization
Gross value = quantity × offer price. Net realization = gross value − transport − commission − storage − other costs. Compare offers using net proceeds and unit net realization, not headline price alone.
## 9. Forecast and sell-time logic
Future model should use dated, source-validated historical prices, define forecast horizon, use time-based train/test validation and report error metrics. A sale-window recommendation should compare expected net proceeds after holding/storage costs and communicate uncertainty; it must not guarantee prices.
## 10. Trust layer
Buyer verification requires evidence and a review workflow. Reliability scores should use explainable signals such as completed orders, on-time payments, cancellations and substantiated disputes. Include appeal processes and safeguards against manipulation or unfair penalties.
## 11. Status
Implemented in browser: navigation, lot search/filter, lot creation, item request, cost-separated net calculator, sell-now vs user-entered later scenario, FPO aggregation preview, buyer cards, local transaction status, dispute submission. Simulated: market prices, historical charts, buyer scores, verification, aggregation, logistics, payments and admin summaries. Not implemented: ML model, live data, real verification, payment, maps, production authentication, persistent UI/API connection.
## 12. Testing checklist
Search and filter lots; create a lot; check that it appears; change each cost and verify net value; compare sale scenarios; preview FPO quantity; create transaction; change logistics status; submit a dispute; after backend setup, test /api/health and database-backed /api/lots, /api/buyers, /api/transactions.
## 13. Security and limitations
This is an academic prototype. Do not use real financial or identity data. Production requires authentication, role-based authorization, input validation, HTTPS, rate limits, secret management, audit logs, backups, dispute evidence controls and secure payment-provider checkout.
## 14. Future roadmap
1. Integrate official market price sources and historical records.
2. Build and validate short-term forecasting model with uncertainty.
3. Create sale-window recommendation logic using forecast and all holding costs.
4. Add real buyer verification and explainable reliability score.
5. Persist FPO aggregation contributions and consent.
6. Connect transport quotes, delivery proof and transaction records.
7. Add secure payments, dispute evidence and admin audit trail.
