# Functional verification

Run these commands from the repository root:

```powershell
python -m pytest -q
npm test
npm run build
```

The verification suite covers:

- FastAPI health, forecast, optimization, scenario, backtest, and report contracts.
- Forecast metrics, insufficient-data behavior, route isolation, and deterministic fallback behavior.
- Vessel capacity, port compatibility, laycan, cost arithmetic, sensitivity, and explainability.
- Decision Twin and Scenario Lab seed determinism, shock response, and bounded outputs.
- PDF generation and evidence consistency.
- Streamlit page smoke rendering.
- Node API proxy allowlisting, method enforcement, service errors, and static bundle generation.

