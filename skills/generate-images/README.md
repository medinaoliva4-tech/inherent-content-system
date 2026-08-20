# /generate-images — Orquestador visual

## Propósito

Decidir **qué imagen hace falta para una pieza real**, qué materiales usar y cuándo invocar Higgsfield.

No genera por inspiración suelta salvo solicitud directa aprobada.

## Contexto obligatorio

Leer:
- `context/BRAND.md`
- `context/DESIGN.md`
- `context/CONTENT.md`
- `context/PILARESDECONTENIDO.md`
- `context/IMAGE_REFERENCE_GUIDE.md`
- `context/IMAGE_APPROVAL_WORKFLOW.md`
- `context/BRAND_WORLD_METHOD.md`
- `brand_context/design/`
- `brand_context/calendar/`
- brief/campaña activa
- `media/JOCKEY_LIBRARY.md`
- `media/MEDIA_INDEX.md`
- `media/COLLECTIONS.md`
- `skills/media-search-with-jockey/SKILL.md`

## Flujo

```text
1. leer pieza/calendario/brief
2. identificar foto/assets necesarios
3. buscar en Jockey assets aprobados
4. revisar `FINAL_ASSETS` y `GENERATED/approved`
5. hacer gap analysis
6. definir solo assets faltantes
7. seleccionar original desde Jockey
8. seleccionar referencia desde Jockey
9. leer observación humana/metadata asociada
10. consultar design context + brand world adaptado
11. construir brief visual
12. ejecutar Higgsfield
13. auto QA
14. human review en Higgsfield
15. solo approved → Jockey `GENERATED/approved` o `FINAL_ASSETS/<categoría>`
16. entregar asset aprobado a la composición Figma
```

## Modelo

```text
NECESIDAD = por qué existe esta imagen
ORIGINAL = qué debe seguir siendo cierto
REFERENCIA = cómo queremos que se vea
OBSERVACIÓN = qué parte exacta importa
MARCA = reglas aprobadas
BRAND WORLD = dirección macro adaptada
```

## Regla de ahorro

No regenerar un asset que ya existe y cumple la función. Primero buscar; luego producir.

## Clasificación

Clasificar por **función visual**, no solo por objetos detectados.

## Higgsfield

Usar `skills/higgsfield-generate-image/SKILL.md`.
