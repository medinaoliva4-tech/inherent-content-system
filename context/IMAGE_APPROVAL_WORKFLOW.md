# IMAGE_APPROVAL_WORKFLOW.md — Gate humano para imágenes generadas

> Protocolo reusable. Evita que una generación pase a la biblioteca aprobada antes de una revisión humana.

## Principio

Higgsfield es mesa de producción. Jockey es biblioteca aprobada de media.

Una imagen generada no se convierte en output solo porque pase QA automático.

## Flujo

```text
NECESIDAD DE CALENDARIO/BRIEF
        ↓
GENERACIÓN HIGGSFIELD
        ↓
AUTO QA
        ↓
HUMAN REVIEW EN HIGGSFIELD
        ↓
APPROVED | CHANGES REQUESTED | PENDING
        ↓
solo APPROVED
        ↓
descarga
        ↓
Jockey GENERATED/approved o FINAL_ASSETS/<categoría>/
```

Los nombres reales de status pueden variar en la interfaz. Mapear semánticamente al modelo anterior.

## Auto QA

Antes de pedir revisión humana:
1. identidad del producto/sujeto;
2. anatomía/artefactos visibles;
3. composición y luz;
4. observación humana de la referencia;
5. `PHOTOGRAPHY_SYSTEM.md`;
6. `BRAND_WORLD_ADAPTATION.md`;
7. necesidad concreta de la pieza/calendario.

Un fallo obvio no debe presentarse como candidato final.

## Human Review

### APPROVED
Descargar y clasificar.

### PENDING
No descargar. No tratar como output.

### CHANGES REQUESTED
Leer el comentario humano como un **delta**, no como un brief nuevo.

Separar:

```text
KEEP = lo aprobado implícita o explícitamente
CHANGE = solo lo solicitado
PROTECT = identidad/invariantes que no deben alterarse
```

No reimaginar elementos que el comentario no pidió cambiar.

## Regla de calidad

La revisión humana ocurre antes de registrar/subir assets approved en Jockey y antes de componer artes finales en Figma.
