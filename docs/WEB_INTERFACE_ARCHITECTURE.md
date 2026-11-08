# Web interface architecture

FreightIQ has two presentation surfaces backed by the same Python decision engines:

```text
web/ (Node static server)
  └── /api/* proxy ──► backend/main.py (FastAPI)
                           ├── forecasting
                           ├── optimizer
                           ├── scenario engine
                           ├── Decision Twin / Strategy Arena
                           ├── backtesting and validation
                           └── reporting and audit storage

app/Home.py (Streamlit workspace) ──► the same backend modules
```

## Browser client

The browser command center is a lightweight JavaScript client in `web/`. It handles navigation, form state, responsive layout, tables, charts, downloads, audit notes, and error states. Plotly and MapLibre assets are self-hosted under `web/vendor/` so the demo remains usable without a runtime CDN dependency.

## Python service

FastAPI owns all decision calculations. The route-aware web endpoints in `backend/web_api.py` expose the browser contract while reusing the same forecasting, optimizer, simulation, validation, and reporting code used by Streamlit.

## Data and provenance

The default mode is deterministic synthetic data. Connector adapters under `backend/integrations/` define the boundary for future live feeds and expose source status and provenance rather than silently presenting synthetic values as live data.

## Persistence

SQLite stores local decision versions and audit notes. `FREIGHTIQ_DB_PATH` can point to an isolated database during testing or deployment.

