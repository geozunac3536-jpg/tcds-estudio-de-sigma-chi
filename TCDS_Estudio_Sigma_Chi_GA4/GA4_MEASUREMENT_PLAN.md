
# Plan de Medición GA4 — TCDS Σ–χ (v1.0)
Fecha: 2025-11-02

## 1) Objetivo
Instrumentar GA4 para medir adopción, trazabilidad y desempeño del estudio Estructura Σ–χ,
alineando eventos con Σ‑metrics (LI, R, RMSE_SL, κΣ) y el flujo de validación (predicciones, verificaciones).

## 2) Eventos GA4
- sigma_view_doc (doc_name, doc_sha256, section, reading_ms)
- sigma_download (artifact_name, sha256, size_bytes)
- sigma_lock (li, r_corr, rmse_sl, kappa_sigma, z_score)
- sigma_prediction_published (pred_date, region, mag_thr, hash_sha256)
- sigma_prediction_verified (pred_date, outcome, delta_t_hours)
- sigma_search (query, results_count)

## 3) Definiciones personalizadas
Dimensiones (event): doc_name, doc_sha256, section, artifact_name, region, pred_date, outcome, hash_sha256, query
Métricas (event): reading_ms, size_bytes, li, r_corr, rmse_sl, kappa_sigma, z_score, delta_t_hours, results_count

## 4) gtag.js — ejemplos
(ver GTAG_SNIPPET.html en este paquete)

## 5) GTM/Triggers
- All Links → .pdf → sigma_download
- Variable DOM data-sha256
- Trigger para sigma_lock cuando LI≥0.9 y Z≥5

## 6) BigQuery (sugerido)
Campos con tipos: ver GA4_CUSTOM_DEFINITIONS.json

## 7) KPI/Tableros
- Adopción: sigma_view_doc, sigma_download
- Σ: medias de li, r_corr, z_score
- Conversión: published→verified(hit)
- Calidad: reading_ms por doc

## 8) Checklist 100/100
- Carga asíncrona
- Dimensiones/métricas creadas en GA4
- Cache/compresión estática en sitio
