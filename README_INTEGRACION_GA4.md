
# Integración GA4 — Σ–χ (pasos exactos)

1) Crea propiedad GA4 y copia tu Measurement ID (G-XXXXX).
2) Inserta `GTAG_SNIPPET.html` en tu sitio (o vía GTM).
3) Da de alta las dimensiones/métricas en GA4 según `GA4_CUSTOM_DEFINITIONS.json`.
4) (Opcional) Enlaza BigQuery.
5) Para PDFs: agrega `data-sha256` al enlace y llama a `trackSigmaDownload(...)` en el click.
6) Para Σ-metrics en demo/tablero: emite `trackSigmaLock(LI, R, RMSE, KAPPA, Z)`.
7) Para predicciones Σ-Earth: usa `trackPredictionPublished` / `trackPredictionVerified`.

Inventario y SHA-256: `INVENTARIO_SHA256.csv` — 2025-11-02.
