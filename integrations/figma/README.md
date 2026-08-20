# Figma / Figwright

> `OPERATIONS.md` define el flujo end-to-end. Este archivo resume el rol local.

## Rol

**Figwright es la capa primaria de ejecución de diseño local en Figma desde Claude Code.**

```text
repo completo
↓
Claude Code
↓
Design Context Gate
↓
design-with-figwright
↓
Figwright MCP
↓
Figma Desktop
↓
export a outputs/_staging_exports/
```

## Antes de diseñar

Confirmar en `CONNECTIONS.md`:
- Figma Desktop = READY;
- Figwright MCP/plugin = READY.

Leer:
- calendario/brief;
- `brand_context/design/BRAND_WORLD_ADAPTATION.md`;
- `DESIGN_SYSTEM.md`;
- `PHOTOGRAPHY_SYSTEM.md`;
- contexto de marca/ICP/oferta;
- assets aprobados;
- `media/MEDIA_INDEX.md` y assets aprobados en Jockey.

## Después de diseñar

El export final no va directo a publicación. Primero entra a `_staging_exports/` y, cuando aplique, pasa `metadata-clean-final`.

Figwright ejecuta diseño; no reemplaza estrategia, dirección creativa ni selección de assets.
