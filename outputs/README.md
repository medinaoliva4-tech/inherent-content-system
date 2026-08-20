# Outputs

Resultados aprobados o entregables del sistema.

- `_staging_exports/` — exports de Figma pendientes de sanitización; NO publish-ready.
- `ads/` — anuncios finales.
- `organic/` — piezas orgánicas finales.
- `campaigns/` — entregables agrupados por campaña.
- `video/` — video final/masters.

## Diferencia crítica

Jockey contiene imagenes/videos aprobados para uso en Figma. `outputs/` contiene staging y entregables finales, no una biblioteca permanente de media.

Un arte final exportado desde Figma pasa:

```text
_staging_exports
↓
Metadata2Go Remove Metadata
↓
QA
↓
destino final
```

## Regla

Outputs no son contexto estratégico. Si un resultado produce un aprendizaje permanente, documentarlo en `brand_context/`.
