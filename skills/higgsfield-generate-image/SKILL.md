---
name: higgsfield-generate-image
description: Genera una fotografía nueva de producto/marca combinando original, referencia, observación humana y contexto visual del cliente en Higgsfield Cinema Studio. Busca primero en Jockey y solo genera cuando una pieza del calendario/brief requiera un asset faltante. Incluye QA automático y un gate de revisión humana dentro de Higgsfield antes de registrar/subir el asset aprobado a Jockey.
---

# Generar imagen con Higgsfield — producción controlada

## 0. Prerrequisitos

Antes de ejecutar:
1. leer `STATUS.md` y `CONNECTIONS.md`;
2. confirmar Jockey MCP e Higgsfield `READY`;
3. confirmar que existe una necesidad concreta de calendario/campaña/brief;
4. buscar primero en Jockey con `skills/media-search-with-jockey/SKILL.md`;
5. generar solo si no existe asset aprobado suficiente.

## 1. Contexto obligatorio

Reunir:
- **Original** — Jockey `ORIGINALS`: identidad real a preservar.
- **Referencia** — Jockey `REFERENCES`: dirección visual puntual.
- **Observación humana** — metadata/nota humana asociada en Jockey o `media/MEDIA_INDEX.md`; explica qué interesa de la referencia.
- **Brand context** — `brand_context/design/`, especialmente `DESIGN_SYSTEM.md`, `PHOTOGRAPHY_SYSTEM.md`, `BRAND_WORLD_ADAPTATION.md`.
- **Brand world maestro** — solo según la adaptación aprobada.
- **Necesidad de pieza** — calendario/brief: uso, formato, copy, composición prevista, asset requerido.

Jerarquía:
1. identidad del original;
2. reglas aprobadas de marca;
3. necesidad funcional de la pieza;
4. observación humana;
5. referencia visual;
6. interpretación adicional del modelo.

## 2. Brief previo

Antes de abrir la generación, sintetizar:

```text
PIEZA / ID:
USO DEL ASSET:
ORIGINAL:
INVARIANTES:
REFERENCIA:
ATRIBUTOS A TRANSFERIR:
OBSERVACIÓN HUMANA:
REGLAS DE MARCA:
ATRIBUTOS A IGNORAR:
ASPECT RATIO:
CRITERIO DE ÉXITO:
```

Si faltan datos críticos, detenerse.

## 3. Configuración en Higgsfield

Usar el proyecto/folder documentado en `STATUS.md`, `CONNECTIONS.md` o `PHOTOGRAPHY_SYSTEM.md`.

Pasos:
1. Cinema Studio → Imagen.
2. Entrar al proyecto/folder correcto de la marca/categoría.
3. Adjuntar original + referencia.
4. Confirmar modo de cámaras cinematográficas.
5. Aplicar preset/cámara documentado.
6. Ajustar aspect ratio al destino de la pieza.

No re-elegir cámara arbitrariamente si ya existe configuración aprobada.

## 4. Prompt — crear, no reemplazar

No pedir “reemplaza X por Y”. Ese framing tiende a producir montaje inconsistente.

Pedir una **fotografía nueva** guiada por dos anclas:
- original = identidad;
- referencia = composición/luz/styling/atmósfera.

Ejemplo conceptual:

> Crea una fotografía nueva con la composición, iluminación y atmósfera de la referencia, usando el original únicamente como ancla de identidad del producto. Mantén forma, ingredientes, colores y rasgos distintivos. Aplica además las restricciones de marca y la observación humana indicada.

Traducir cualquier sidecar humano a instrucciones explícitas.

## 5. Auto QA antes de presentar a revisión

Evaluar:
1. ¿el producto/sujeto sigue siendo el mismo?
2. ¿hay deformaciones, manos/anatomía incorrecta, bordes o artefactos?
3. ¿composición, luz y atmósfera sirven para la pieza?
4. ¿se respetó la observación humana?
5. ¿se respeta `PHOTOGRAPHY_SYSTEM.md`?
6. ¿se respeta `BRAND_WORLD_ADAPTATION.md`?
7. ¿el resultado cumple la función específica del calendario/brief?

Un fallo obvio no se presenta como candidato final.

## 6. HUMAN REVIEW GATE — obligatorio

Después del auto QA, **no registrar como approved/final todavía**.

La generación permanece en el folder de la marca en Higgsfield para revisión humana.

Mapear los estados reales de la interfaz a:
- `APPROVED`
- `CHANGES_REQUESTED`
- `PENDING / NEEDS_REVIEW`

### APPROVED
Puede registrarse/subirse a Jockey en `GENERATED/approved`. Si se convierte en asset reusable, promover a `FINAL_ASSETS`.

### PENDING
No descargar. No usar en Figma como asset aprobado.

### CHANGES_REQUESTED
Leer el comentario humano y convertirlo en delta:

```text
KEEP:
CHANGE:
PROTECT:
```

No rehacer la fotografía completa cuando el usuario pidió cambios puntuales. Mantener todo lo no cuestionado, salvo que exista un error técnico crítico.

Re-generar/revisar y volver al Human Review Gate.

Leer `context/IMAGE_APPROVAL_WORKFLOW.md`.

## 7. Registro en Jockey

Solo después de `APPROVED`:
1. registrar/subir la imagen aprobada en Jockey;
2. clasificarla en `GENERATED/approved` o `FINAL_ASSETS/<categoria>`;
3. actualizar `media/MEDIA_INDEX.md` con ID, estado, uso y notas;
4. registrar procedencia si el proyecto lo requiere.

Jockey `approved` significa **aprobado para producción/diseño**, no necesariamente `PUBLISH_READY`.

## 8. Metadata

Si esta imagen será input de Figma, no es obligatorio sanitizarla antes de componer solo por rutina.

Si se va a publicar/entregar directamente sin Figma, ejecutar `skills/metadata-clean-final/SKILL.md` sobre la copia publicable antes de considerarla final.
