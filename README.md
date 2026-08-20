# Inherent Content System — v8 Jockey MCP

Sistema operativo de contenido de Inherent, basado en el OS reusable v8 con MCPs.

## Arquitectura

```text
context/                  = metodología reusable
brand_world_reference/    = inspiración visual central
brand_context/            = verdad/estrategia del cliente
media/                    = punteros e inventario logico de Jockey
skills/                   = procedimientos
integrations/             = herramientas y setup
outputs/                  = staging y producción final; no biblioteca permanente de media
```

Archivos raíz clave:
- `CLAUDE.md` — constitución del agente.
- `OPERATIONS.md` — flujo end-to-end + setup de conexiones.
- `CONNECTIONS.md` — estado real de herramientas.
- `PROJECT_READINESS.md` — gate de repo completo.
- `STATUS.md` — estado variable del cliente.

## Flujo completo

```text
REPO COMPLETO + CONNECTIONS READY
↓
ESTRATEGIA
↓
APIFY RESEARCH (cuando aplica)
↓
HIPÓTESIS
↓
CALENDARIO
↓
ASSETS NECESARIOS
↓
JOCKEY SEARCH / GAP ANALYSIS
↓
HIGGSFIELD si falta material aprobado
↓
AUTO QA
↓
HUMAN REVIEW
↓
JOCKEY generated/approved o final assets
↓
FIGWRIGHT + FIGMA
↓
EXPORT A _staging_exports
↓
METADATA2GO REMOVE METADATA
↓
OUTPUT FINAL / PUBLISH_READY
```

## Principios

- No generar imágenes random: la necesidad nace del calendario/brief.
- Apify aporta señales recientes; no garantiza alcance.
- Jockey es la biblioteca central de media: originals, references, generated, final assets y video.
- El repo no guarda imagenes/videos fisicos de produccion; guarda contexto, reglas, links, IDs y metadata.
- Higgsfield es mesa de producción; Jockey recibe solo aprobados.
- Figwright compone usando estrategia + design context + assets aprobados recuperados desde Jockey.
- Influencer marketing, UGC, affiliate y partnerships son vehiculos estrategicos planificados en `brand_context/content/marketing_vehicles/`.
- El arte final se sanitiza después del export de Figma.
- Un folder documentado sin conexión funcional no equivale a un sistema operativo.

## Primer uso

1. Crear repo desde template.
2. Poblar contexto real del cliente.
3. Cargar/adaptar brand world.
4. Configurar `media/` con link/Store ID de Jockey y colecciones.
5. Completar `CONNECTIONS.md` con pruebas reales.
6. Pasar `PROJECT_READINESS.md`.
7. Marcar `READY_FOR_PRODUCTION`.
8. Clonar/actualizar localmente.
9. Abrir Claude Code en raíz.
10. Operar según `OPERATIONS.md`.
