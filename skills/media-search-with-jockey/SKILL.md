---
name: media-search-with-jockey
description: Busca y selecciona imagenes/videos en Jockey antes de generar, pedir o asumir que falta un asset. Usar para necesidades de calendario, briefs, Figwright y Higgsfield.
---

# Buscar media con Jockey

## Objetivo

Encontrar assets aprobados o referencias utiles en Jockey antes de crear media nueva.

## Inputs

- Calendario o brief.
- Necesidad visual.
- Brand context.
- Design context.
- Restricciones de uso.

## Orden de busqueda

1. `FINAL_ASSETS/<categoria>`
2. `GENERATED/approved`
3. `ORIGINALS`
4. `REFERENCES`
5. Generacion nueva via Higgsfield

## Resultado esperado

Cada busqueda debe devolver:

```text
ASSET NEED:
QUERY:
JOCKEY ASSET ID:
COLLECTION:
STATUS:
WHY SELECTED:
USAGE LIMITS:
NEXT ACTION:
```

## Regla

Si existe un asset `approved` suficiente, usarlo. No generar de nuevo.

Si solo existe referencia, pasar a Higgsfield con:
- original;
- reference;
- human note;
- brand context;
- design context;
- objetivo del calendario/brief.

