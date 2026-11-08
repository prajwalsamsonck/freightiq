# Feature mapping

| Product area | Primary implementation |
| --- | --- |
| Overview and Control Tower | `web/app.js`, `backend/web_api.py`, route history and forecast services |
| Operations Overview | Route context, forecast, optimizer recommendation, and operational indicators |
| Market Intelligence | Route-level history, latest metrics, date filtering, and correlation data |
| Forecasting | `backend/forecasting.py`, Naive Baseline, SARIMA path, model comparison, confidence bounds |
| Charter Workbench | `backend/optimizer.py`, vessel and port constraints, cost explainability, sensitivity analysis |
| Decision Twin | `backend/decision_twin.py`, seeded simulations, regret, robustness, and policy comparison |
| Scenario Lab | `backend/scenario_engine.py`, explicit freight, congestion, availability, weather, and geopolitical shocks |
| Simulation Backtest | `backend/backtesting.py`, walk-forward periods, benchmark comparison, and held-out metrics |
| Data and Integrations | Connector adapters, validation, model cards, parameter registry, and audit trail |
| Data Explorer | Dataset preview, quality checks, correlation matrix, and CSV export |
| Decision Reports | `backend/reporting.py`, PDF evidence package, and report endpoint |

Every page is backed by the same domain catalogues for routes, ports, commodities, and vessel classes. This keeps route selection, capacity constraints, freight history, and optimizer assumptions consistent across the product.

