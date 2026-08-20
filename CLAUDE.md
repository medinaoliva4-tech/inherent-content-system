# INHERENTE — CLAUDE CODE OPERATING SYSTEM v8 Jockey MCP

> Constitución operativa del repo. Define cómo debe razonar Claude antes de investigar, calendarizar, generar, diseñar, exportar o publicar.

## 0. Principio rector

Claude NO opera como una fábrica aislada de contenido. Opera un sistema de crecimiento:

**metodología → estrategia de marca → research de señales → calendario → necesidades de producción → generación/diseño → aprobación → export final → sanitización → distribución → análisis → aprendizaje**.

Toda salida relevante debe poder responder:
1. ¿Qué deseo, tensión o necesidad del público activa?
2. ¿Qué posicionamiento refuerza?
3. ¿Qué promesa demuestra o hace creíble?
4. ¿Qué resultado de negocio busca?
5. ¿Qué evidencia real de la marca la sostiene?
6. ¿Qué necesidad concreta del calendario/brief está resolviendo?

Si no puede responder, debe buscar contexto, pedir una decisión o etiquetar la salida como hipótesis.

---

## 1. El repo completo es el proyecto

El repositorio GitHub de cada cliente es la única fuente de verdad compartida.

Claude Code local debe abrir **la raíz del repo clonado** como proyecto. No debe producir desde un prompt aislado ni desde un subfolder parcial.

La raíz debe contener y mantener sincronizados:
- `CLAUDE.md`
- `OPERATIONS.md`
- `PROJECT_READINESS.md`
- `CONNECTIONS.md`
- `STATUS.md`
- `context/`
- `brand_world_reference/`
- `brand_context/`
- `media/`
- `skills/`
- `integrations/`
- `outputs/`

### NO CLONE BEFORE READY

Antes de producción:
- `PROJECT_READINESS.md` debe pasar;
- `STATUS.md` debe indicar `PROJECT_STATUS: READY_FOR_PRODUCTION`;
- las conexiones requeridas para esa producción deben estar `READY` en `CONNECTIONS.md`.

Estructura creada ≠ proyecto listo. README de scaffolding ≠ contexto real.

---

## 2. Arquitectura de contexto y autoridad

### 2.1 `context/` — metodología reusable e inmutable

Núcleo metodológico preservado:
- `ICP.md`
- `BRAND.md`
- `OFFER.md`
- `CONTENT.md`
- `DESIGN.md`
- `CALENDAR.md`
- `PILARESDECONTENIDO.md`
- `ANALYTICS.md`
- `COMMUNITY.md`

Protocolos complementarios:
- `IMAGE_REFERENCE_GUIDE.md`
- `IMAGE_APPROVAL_WORKFLOW.md`
- `BRAND_WORLD_METHOD.md`
- `CORE_INTEGRITY.md`

No adaptar estos archivos a un cliente particular.

### 2.2 `brand_world_reference/` — inspiración visual central

Brand guideline / brand world maestro de Dirección Creativa. No es identidad final.

Clasificar por cliente:
- `KEEP`
- `ADAPT`
- `INSPIRE`
- `REJECT`
- `TBD`

La adaptación final vive en `brand_context/design/BRAND_WORLD_ADAPTATION.md`.

### 2.3 `brand_context/` — verdad de la marca activa

- `brand/` — posicionamiento, promesa, narrativa, personalidad, voz, valores y prueba.
- `icp/` — público, psicografía, deseos, tensiones y segmentos.
- `offer/` — productos, servicios, precios, paquetes, claims y evidencia.
- `content/` — canales, formatos, mensajes, briefs y aprendizajes.
- `design/` — adaptación del brand world, design system, fotografía, tipografía, color y cámara.
- `calendar/` — piezas, fechas, objetivos, assets necesarios y estado de producción.
- `analytics/` — performance, resultados e hipótesis.
- `community/` — conversaciones, FAQs y señales de pertenencia.
- `founder/` — historia, autoridad, opiniones y activos.
- `competitors/` — competencia y referentes estratégicos.
- `research/` — investigación; `research/apify/` documenta señales externas recolectadas con Apify.

### 2.4 `media/` — biblioteca logica conectada a Jockey

Jockey es la fuente de verdad para imagenes y videos.

El repo no debe almacenar copias fisicas de produccion. Debe guardar:
- link directo al folder/store de Jockey;
- Store ID si aplica;
- IDs de assets;
- colecciones;
- estados;
- notas humanas;
- restricciones de uso.

Colecciones esperadas en Jockey:
- `ORIGINALS`
- `REFERENCES`
- `GENERATED/pending`
- `GENERATED/changes_requested`
- `GENERATED/approved`
- `FINAL_ASSETS`
- `VIDEO`

### 2.5 `skills/` — procedimientos

Las skills ejecutan decisiones ya fundamentadas. No sustituyen metodología ni contexto de marca.

### 2.6 `integrations/` — herramientas

- Figwright → ejecución de diseño en Figma Desktop.
- Jockey → busqueda, recuperacion y registro de media aprobada.
- Higgsfield → generación visual.
- Apify → research de señales y scraping para hipótesis de contenido.
- Metadata2Go → sanitización de metadatos del archivo final publicable.

### 2.7 `outputs/` — resultados

- `media/` + Jockey = biblioteca de imagenes/videos aprobados para producción/diseño.
- `outputs/_staging_exports/` = export temporal, todavía NO publicable.
- `outputs/ads/`, `organic/`, `campaigns/`, `video/` = destinos finales según tipo.

Un output no se convierte automáticamente en regla de marca.

---

## 3. Jerarquía de decisión

1. Instrucción explícita actual del usuario.
2. Hechos confirmados en `brand_context/`.
3. Decisiones aprobadas en `brand_context/design/`.
4. Metodología en `context/`.
5. Observaciones humanas asociadas a referencias.
6. Brand world maestro como inspiración.
7. Señales externas de research/Apify.
8. Interpretación propia de Claude.

### Evidencia

No inventar público, oferta, claims, métricas, precios, resultados, tipografías, colores o decisiones.

Estados:
- `CONFIRMADO`
- `HIPÓTESIS`
- `POR DEFINIR`

### Conflictos

- Brand context aprobado > brand world maestro.
- Design system > referencia estética.
- Fidelidad del producto > similitud con la referencia.
- Estrategia de marca > tendencia externa.
- Comentario humano de revisión > reinterpretación automática.

---

## 4. CONNECTION PREFLIGHT — obligatorio

Antes de ejecutar una tarea que dependa de herramientas externas:
1. leer `CONNECTIONS.md`;
2. identificar qué conexiones requiere la tarea;
3. confirmar que estén `READY`;
4. si no, seguir el setup de `OPERATIONS.md` + `integrations/<tool>/README.md`;
5. no fingir ejecuciones, scraping, diseños, generaciones o limpiezas no realizadas.

Ejemplos:
- diseño → Figma Desktop + Figwright;
- generación → Higgsfield;
- research scraping → Apify;
- publish-ready → Metadata2Go cuando aplique.

---

## 5. Gate estratégico antes de producir

Resolver:

```text
OBJETIVO DE NEGOCIO:
HÉROE / SEGMENTO:
DESEO O TENSIÓN:
POSICIONAMIENTO A REFORZAR:
PROMESA A DEMOSTRAR:
CAPA: funcional | emocional | cultural
ATRIBUTO DE IDENTIDAD:
PILAR:
FORMATO:
CANAL:
RESULTADO DE MEDIA ESPERADO:
RESULTADO DE NEGOCIO ESPERADO:
EVIDENCIA DISPONIBLE:
DECISIONES VISUALES APROBADAS:
RIESGOS / DATOS FALTANTES:
```

---

## 6. RESEARCH SIGNAL GATE — Apify antes de ideación cuando se requiera

Apify sirve para observar qué está captando atención y convertirlo en hipótesis, **no para garantizar alcance** ni copiar contenido.

Cuando se necesiten ideas/research reciente:
1. leer estrategia y `CONTENT_SYSTEM.md`;
2. definir pregunta de research;
3. usar `skills/research-with-apify/SKILL.md`;
4. documentar corrida en `brand_context/research/apify/`;
5. extraer mecanismo/patrón;
6. filtrar por ICP, posicionamiento, promesa y pilares;
7. aprobar/rechazar hipótesis;
8. solo entonces pasar piezas al calendario.

Flujo:

```text
APIFY SIGNALS
↓
PATTERN / MECHANISM
↓
STRATEGIC FIT
↓
HYPOTHESIS
↓
CALENDAR TEST
↓
MEASURE
```

---

## 7. CALENDAR → PRODUCTION NEEDS GATE

No generar imágenes random.

Toda producción debe responder a:
- pieza del calendario;
- campaña;
- brief aprobado;
- solicitud directa aprobada.

Cada pieza debe especificar, cuando aplique:
- objetivo;
- mensaje/copy;
- formato/canal;
- CTA;
- layout necesario;
- fotografía necesaria;
- assets necesarios;
- assets existentes;
- assets faltantes;
- estado de producción.

Antes de generar:

```text
ASSETS REQUERIDOS
↓
INVENTARIO EXISTENTE
↓
GAP ANALYSIS
↓
GENERAR SOLO FALTANTES
```

---

## 8. IMAGE PRODUCTION GATE — Higgsfield

Para imágenes:

```text
NECESIDAD DE PIEZA
+
ORIGINAL = identidad
+
REFERENCIA = dirección visual
+
OBSERVACIÓN HUMANA
+
DESIGN CONTEXT
+
BRAND WORLD ADAPTADO
↓
HIGGSFIELD
```

Usar `skills/higgsfield-generate-image/SKILL.md`.

### Human approval obligatorio

Una generación no entra automáticamente a Jockey como `approved` o `final`.

```text
GENERATE
↓
AUTO QA
↓
HUMAN REVIEW EN HIGGSFIELD
↓
APPROVED | CHANGES REQUESTED | PENDING
```

Solo `APPROVED` se registra/sube a Jockey como `GENERATED/approved`. Si se vuelve reusable, se promueve a `FINAL_ASSETS`.

`CHANGES REQUESTED` se interpreta como delta:
- `KEEP`
- `CHANGE`
- `PROTECT`

Leer `context/IMAGE_APPROVAL_WORKFLOW.md`.

---

## 9. DESIGN CONTEXT GATE — obligatorio antes de Figwright

Antes de llamar Figwright resolver:
1. objetivo de la pieza;
2. ICP/segmento;
3. oferta/mensaje;
4. calendario/brief activo;
5. formato/canal;
6. `BRAND_WORLD_ADAPTATION.md`;
7. `DESIGN_SYSTEM.md`;
8. `PHOTOGRAPHY_SYSTEM.md` si usa fotografía;
9. assets requeridos y aprobados desde Jockey;
10. `media/MEDIA_INDEX.md` y `media/COLLECTIONS.md`;
11. restricciones del brief.

Ruta:

```text
REPO + ESTRATEGIA + CALENDARIO + JOCKEY ASSETS APROBADOS
↓
CLAUDE CODE
↓
FIGWRIGHT MCP
↓
FIGMA DESKTOP
↓
COMPOSICIÓN FINAL
```

Figwright ejecuta; no decide la estrategia.

---

## 10. FINAL ASSET SANITIZATION GATE

Un arte final exportado no es `PUBLISH_READY` hasta completar el gate de metadata cuando aplique.

### Si la pieza pasa por Figma

```text
FIGMA
↓
EXPORT
↓
outputs/_staging_exports/
↓
Metadata2Go Remove Metadata
↓
QA
↓
destino final en outputs/
```

No es necesario limpiar cada foto fuente antes de Figma solo por rutina. Lo obligatorio es sanitizar **el archivo final que será publicado/entregado**, porque ese es el archivo que sale del sistema.

### Si una imagen de Higgsfield se publica directamente

Sanitizar la copia publicable antes de su entrega/publicación.

Usar `skills/metadata-clean-final/SKILL.md`.

---

## 11. Regla de contenido

Cada pieza debe buscar:
1. impacto inicial;
2. involucramiento narrativo;
3. punto de virada.

Operar como científico:
**observar → explicar → formular hipótesis → probar → medir → documentar → replicar**.

Después de validar formatos:
- 70% validado;
- 20% experimentación;
- 10% optimización.

Nunca tratar views/seguidores como fin. Conectar media con leads, conversión, ingresos y comunidad.

---

## 12. Sincronización y frescura

Antes de producción local:
1. confirmar `READY_FOR_PRODUCTION`;
2. clonar o actualizar/pull;
3. revisar último commit validado;
4. revisar `CONNECTIONS.md`;
5. no producir con clone o contexto desactualizado.

---

## 13. Definition of Done

Una pieza no está terminada solo porque se ve bien.

Debe:
- responder a estrategia y calendario/brief;
- usar el sistema visual aprobado;
- usar assets correctos y aprobados;
- haber pasado human review si incluye imágenes generadas;
- haber pasado QA de composición;
- haber pasado sanitización de metadata si es un archivo publicable final;
- estar en el destino correcto de `outputs/`;
- poder vincularse a objetivo de negocio;
- documentar aprendizaje reutilizable cuando exista.

Estados útiles:
- `DRAFT`
- `IN_PRODUCTION`
- `NEEDS_REVIEW`
- `APPROVED`
- `BLOCKED_METADATA_SANITIZATION`
- `PUBLISH_READY`
