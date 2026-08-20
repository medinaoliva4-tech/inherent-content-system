---
name: design-with-figwright
description: Ejecuta composición en Figma desde Claude Code local usando Figwright, después de que estrategia, calendario, copy, design context y assets aprobados de Jockey estén resueltos. Exporta primero a staging; el archivo final no es publish-ready hasta pasar sanitización de metadata cuando aplique.
---

# Diseñar con Figwright usando el repo completo

## Gate 0 — repo y conexiones

1. leer `STATUS.md`;
2. confirmar `READY_FOR_PRODUCTION`;
3. leer `CONNECTIONS.md`;
4. confirmar Figma Desktop + Figwright + Jockey MCP `READY`;
5. confirmar clone actualizado.

## Gate 1 — pieza real

Resolver:

```text
PIEZA / ID:
OBJETIVO:
CANAL / DESTINO:
FORMATO / DIMENSIONES:
ICP / SEGMENTO:
OFERTA / MENSAJE:
COPY:
CTA:
PILAR:
ASSETS NECESARIOS:
ASSETS APROBADOS DISPONIBLES:
BRAND WORLD ADAPTATION:
DESIGN SYSTEM:
PHOTOGRAPHY SYSTEM:
RESTRICCIONES:
```

Leer calendario/brief correspondiente. No diseñar una composición huérfana de estrategia.

## Gate 2 — assets

Usar primero assets aprobados desde Jockey:
- `FINAL_ASSETS/<categoria>` para imagenes listas para composicion;
- `GENERATED/approved` para imagenes aprobadas aun no promovidas;
- `ORIGINALS` cuando una pieza requiera explicitamente material real;
- `REFERENCES` solo como direccion visual, no como material final salvo autorizacion explicita.

Si falta un asset requerido, volver al production gap, buscar referencias en Jockey y producirlo antes de componer.

Registrar en el brief los Jockey asset IDs usados.

## Design Brief operativo

```text
OBJETIVO DE NEGOCIO:
MENSAJE PRINCIPAL:
JERARQUÍA:
FRAMES / SLIDES:
DIRECCIÓN VISUAL:
TIPOGRAFÍA:
COLOR:
FOTOGRAFÍA:
ELEMENTOS GRÁFICOS:
ASSETS EXACTOS:
JOCKEY ASSET IDS:
ELEMENTOS A EVITAR:
CTA:
CRITERIO DE ÉXITO:
```

## Ejecutar Figwright

1. conectar al archivo/proyecto documentado;
2. seleccionar/crear página o frame correcto;
3. reutilizar componentes aprobados;
4. mantener texto editable;
5. respetar naming;
6. construir la composición con los assets exactos;
7. no inventar estilos ya definidos.

## QA de composición

1. objetivo y mensaje;
2. jerarquía;
3. design system;
4. brand world adaptation;
5. fotografía correcta para la función;
6. assets correctos;
7. legibilidad;
8. dimensiones/canal;
9. editabilidad;
10. ausencia de copia literal indebida de referentes.

## Export

Cuando la composición esté aprobada:
1. exportar el formato final requerido;
2. guardar inicialmente en `outputs/_staging_exports/`;
3. no marcar `PUBLISH_READY` todavía;
4. ejecutar `skills/metadata-clean-final/SKILL.md` si el archivo se publicará/entregará;
5. después de sanitización y QA, mover al destino final (`outputs/organic/`, `ads/`, `campaigns/`, etc.).

## Aprendizaje

Si surge una regla reusable aprobada, documentarla en `brand_context/design/`, no en `context/`.
