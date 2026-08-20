# CHANGELOG.md

## v8 — Jockey MCP como biblioteca central de media

- El paquete parte de v7 y conserva su arquitectura, skills e integraciones existentes.
- Se agrega `.mcp.json` con Jockey MCP, Figwright MCP y Apify MCP usando placeholders/env vars sin secretos hardcodeados.
- Se agrega `media/` con `README.md`, `JOCKEY_LIBRARY.md`, `MEDIA_INDEX.md` y `COLLECTIONS.md`.
- Jockey reemplaza `assets/originals/`, `assets/references/` y `outputs/images/` como biblioteca fisica permanente.
- El repo conserva contexto, metodologia, reglas, links, IDs y metadata; Jockey conserva originals, references, generated, final assets y video.
- Higgsfield ahora busca primero en Jockey y solo registra/sube a Jockey cuando el humano aprueba.
- Figwright recupera assets aprobados desde Jockey segun calendario/brief y exporta a staging.
- Metadata2Go sigue como limpieza del arte final exportado antes de `publish_ready`.
- Apify se mantiene como research de senales/ideas antes del calendario.
- `PROJECT_READINESS.md` exige Jockey MCP/conexiones verificadas para considerar el repo READY.
- Los nueve archivos metodologicos base de `context/` permanecen sin cambios.

## v7 — Research, review humano, conexiones y finalización segura

- Nuevo `CONNECTIONS.md` como preflight real de integraciones.
- Apify entra como capa de research de señales antes de ideación/calendario cuando aplica.
- Nueva integración `integrations/apify/` y skill `research-with-apify`.
- Nuevo workspace `brand_context/research/apify/` con fuentes, run log y signal log.
- Calendario ampliado para registrar fotos/assets necesarios, faltantes y estados de producción.
- Higgsfield ahora exige Human Review Gate antes de descargar a `outputs/images/`.
- Nuevo `context/IMAGE_APPROVAL_WORKFLOW.md`.
- Comentarios de revisión se procesan como delta KEEP / CHANGE / PROTECT.
- Nuevo `_staging_exports/` para exports de Figma todavía no publish-ready.
- Metadata2Go entra como gate de sanitización del archivo final publicable.
- Nueva integración `integrations/metadata2go/` y skill `metadata-clean-final`.
- Figma/Metadata: no se limpia cada input por rutina; se sanitiza el export final que se va a publicar. Una imagen directa de Higgsfield se sanitiza si no pasa por Figma.
- `PROJECT_READINESS.md`, `STATUS.md`, `CLAUDE.md`, `OPERATIONS.md` y skills actualizados.
- Los nueve archivos metodológicos base de `context/` permanecen sin cambios.
