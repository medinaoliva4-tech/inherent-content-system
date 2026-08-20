# PROJECT_READINESS.md — Gate para declarar un repo listo para producción

> “Repo completo” significa contexto real + media/Jockey + herramientas requeridas conectadas y probadas. Un folder con README no sustituye ninguna de esas tres cosas.

## 1. Metodología y sistema
- [ ] `context/` completo y sin modificaciones específicas de cliente.
- [ ] `CLAUDE.md` y `OPERATIONS.md` corresponden a la versión vigente.
- [ ] `CONNECTIONS.md` existe y refleja el entorno real.

## 2. Brand World
- [ ] `brand_world_reference/INVENTORY.md` refleja el material cargado.
- [ ] Brand guideline / brand world central cargado cuando aplique.
- [ ] `BRAND_WORLD_ADAPTATION.md` clasifica elementos relevantes como KEEP / ADAPT / INSPIRE / REJECT / TBD.

## 3. Marca activa
- [ ] `BRAND_PROFILE.md` poblado.
- [ ] `ICP_PROFILE.md` suficiente para producir.
- [ ] `OFFER_CATALOG.md` vigente.
- [ ] `CONTENT_SYSTEM.md` poblado.
- [ ] `DESIGN_SYSTEM.md` poblado.
- [ ] `PHOTOGRAPHY_SYSTEM.md` poblado si se usará fotografía.
- [ ] `CALENDAR_STATUS.md` actualizado y capaz de registrar assets necesarios.
- [ ] Competencia/research relevantes actualizados cuando afecten la tarea.

## 4. Research / Apify
Si el sistema usará scraping para ideación/research:
- [ ] `integrations/apify/README.md` revisado.
- [ ] Apify está `READY` en `CONNECTIONS.md`.
- [ ] Actor de prueba ejecutado y dataset recuperado.
- [ ] `brand_context/research/apify/` tiene fuentes/logs listos.

Si no aplica, documentar `NOT_REQUIRED`.

## 5. Media / Jockey
- [ ] `media/JOCKEY_LIBRARY.md` contiene link directo y Store ID si aplica.
- [ ] `media/COLLECTIONS.md` refleja la estructura real o esperada.
- [ ] `media/MEDIA_INDEX.md` registra assets criticos por ID/link.
- [ ] Jockey contiene o apunta a originals, references, generated, final assets y video.
- [ ] No hay imagenes/videos fisicos de produccion versionados en el repo.
- [ ] Jockey esta `READY` en `CONNECTIONS.md`.

## 6. Producción visual / Higgsfield
Si habrá generación:
- [ ] Higgsfield `READY` en `CONNECTIONS.md`.
- [ ] Proyecto/folder de la marca identificado.
- [ ] Preset/cámara documentado.
- [ ] Flujo de status/comentarios de revisión entendido.
- [ ] Flujo aprobado para registrar/subir en Jockey solo cuando el asset este `approved`.
- [ ] `IMAGE_APPROVAL_WORKFLOW.md` disponible.

## 7. Diseño / Figma + Figwright
Si habrá diseño:
- [ ] Figma Desktop `READY`.
- [ ] Archivo/proyecto destino identificado.
- [ ] Figwright MCP `READY`.
- [ ] Plugin local conectado.
- [ ] Prueba de lectura/escritura completada.

## 8. Metadata / publish-ready
Si se entregarán/publicarán imágenes o artes raster:
- [ ] Metadata2Go `READY` en `CONNECTIONS.md` o método alternativo aprobado documentado.
- [ ] Flujo `outputs/_staging_exports/` → sanitización → output final entendido.
- [ ] Export de prueba limpiado y verificado.

## 9. Outputs
- [ ] `outputs/` conserva estructura requerida.
- [ ] `outputs/` no se usa como biblioteca permanente de imagenes.
- [ ] `_staging_exports/` existe para exports no sanitizados.
- [ ] No hay aprobados finales guardados fuera de `outputs/` sin razón documentada.

## 10. Estado y sincronización
- [ ] `STATUS.md` tiene cliente, repo, branch y última actualización.
- [ ] No hay bloqueos críticos sin resolver.
- [ ] Remoto GitHub contiene todos los archivos necesarios.
- [ ] Último commit remoto corresponde al estado que se desea clonar.

## Resultado

Si todo lo requerido está completo:

`PROJECT_STATUS: READY_FOR_PRODUCTION`

Si falta un elemento crítico:

`PROJECT_STATUS: NOT_READY`

Un proyecto READY aún debe pasar los gates por pieza: strategy → research si aplica → calendar/asset gap → image review → design → metadata.
