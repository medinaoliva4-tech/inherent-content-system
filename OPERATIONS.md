# OPERATIONS.md — Workflow operativo v8 Jockey MCP

> Archivo agnóstico de marca. Documenta CÓMO opera el sistema end-to-end y cómo preparar las conexiones. No reemplaza `context/`, `brand_world_reference/` ni `brand_context/`.
>
> Para conexión y operación end-to-end, este archivo tiene prioridad sobre los README puntuales de `integrations/`.

---

## 0. Modelo operativo

```text
GITHUB REPO COMPLETO
        ↓
CLONE / UPDATE
        ↓
CLAUDE CODE LOCAL
(abierto en la raíz)
        ↓
CONNECTION PREFLIGHT
        ↓
STRATEGY / RESEARCH / CALENDAR
        ↓
PRODUCTION NEEDS
        ↓
JOCKEY SEARCH / HIGGSFIELD / FIGWRIGHT
        ↓
HUMAN REVIEW + QA
        ↓
FIGMA EXPORT
        ↓
METADATA SANITIZATION
        ↓
FINAL OUTPUTS
```

GitHub = fuente de verdad compartida para contexto, estrategia, reglas, links e IDs.
Jockey = fuente de verdad para imagenes y videos.
Clone local = espacio de producción.
Herramientas externas = brazos de ejecución que deben estar conectados y probados.

---

## 1. Qué significa “repo completo”

Un repo no está listo porque los folders existan.

Debe pasar:
- `PROJECT_READINESS.md`;
- `STATUS.md` = `READY_FOR_PRODUCTION`;
- `CONNECTIONS.md` con las herramientas requeridas en `READY`.

### NO CLONE BEFORE READY

1. crear repo;
2. poblar contexto, brand world, brand context, media/Jockey y setup;
3. validar readiness;
4. verificar conexiones;
5. confirmar remoto completo;
6. clonar para producción.

---

## 2. Setup y conexiones — obligatorio

Sin conexiones reales, los folders son solo documentación. Este setup debe completarse por entorno y registrarse en `CONNECTIONS.md`.

### 2.1 GitHub

Objetivo: clonar/actualizar el repo completo y, cuando el entorno lo permita, sincronizar resultados.

Verificar:
- repo remoto correcto;
- branch correcta;
- clone/pull funcionando;
- último commit validado;
- mecanismo de write-back conocido.

### 2.2 Figma Desktop + Figwright

Objetivo: que Claude Code pueda ejecutar diseño con todo el contexto del repo.

Verificar:
- Figma Desktop instalado/abierto;
- archivo/proyecto del cliente identificado;
- plugin de Figwright activo en Figma;
- servidor MCP de Figwright disponible para Claude Code;
- prueba real de lectura/escritura en un frame no crítico.

Marcar `READY` solo después de la prueba.

### 2.3 Jockey MCP

Objetivo: buscar, recuperar y registrar media sin convertir GitHub en biblioteca de imagenes/videos.

Verificar:
- Jockey MCP disponible para Claude Code;
- autenticacion OAuth completada sin secretos hardcodeados;
- knowledge store/folder de la marca identificado;
- link directo y Store ID documentados en `media/JOCKEY_LIBRARY.md`;
- busqueda de prueba funcionando;
- consulta de colecciones/metadata funcionando;
- proceso de `jockey_add_media` o equivalente entendido para assets aprobados.

Endpoint documentado:

```text
https://mcp.twelvelabs.io/jockey/mcp
```

### 2.4 Higgsfield Cinema Studio

Objetivo: generar imágenes por necesidad de pieza, no de forma aislada.

Verificar:
- sesión accesible;
- proyecto/folder de la marca identificado;
- configuración de cámara/preset documentada;
- original + referencia pueden adjuntarse;
- generación de prueba completa;
- flujo de status/comentarios de revisión entendido.

### 2.5 Apify

Objetivo: scrapear señales recientes para research de formatos/ideas y convertirlas en hipótesis.

Setup preferido en Claude Code:
1. abrir `/mcp`;
2. habilitar `plugin:apify:apify`;
3. autenticar mediante OAuth para ejecutar Actors y acceder a datos de cuenta;
4. buscar un Actor de prueba;
5. ejecutar muestra pequeña;
6. recuperar dataset;
7. registrar `READY` en `CONNECTIONS.md`.

Apify también documenta su MCP server y CLI. La integración concreta puede cambiar por entorno; `integrations/apify/README.md` contiene el setup operativo.

### 2.6 Metadata2Go

Objetivo: eliminar metadata del **archivo final publicable**.

No requiere asumir una API/MCP en este template. Se opera vía web/browser:
- `https://www.metadata2go.com/delete-metadata`

Verificar una vez por entorno:
1. subir un export de prueba;
2. eliminar metadata;
3. descargar;
4. revisar integridad visual;
5. comprobar metadata si el proyecto lo requiere;
6. registrar `READY`.

Si el entorno no puede operar navegador, mantener este gate como paso manual obligatorio.

---

## 3. Cloud/Cowork vs Claude Code local

### Cloud/Cowork

Ideal para:
- estrategia;
- research;
- análisis de documentos;
- ICP/posicionamiento/promesa/narrativa;
- briefs;
- decisiones que luego se escriben al repo mediante el mecanismo disponible.

No asumir escritura directa al remoto ni acceso a localhost.

### Claude Code local

Entorno principal de producción:
- clone completo;
- Figma Desktop;
- Figwright;
- navegador/herramientas locales;
- Higgsfield cuando se opere desde el entorno local;
- Apify MCP/plugin.

Siempre abrir Claude Code en la raíz del repo.

---

## 4. Sincronización antes de producir

Antes de una sesión:
1. validar remoto;
2. `git pull`/actualización equivalente;
3. leer `STATUS.md`;
4. leer `CONNECTIONS.md`;
5. confirmar que la pieza/calendario usa el estado más reciente;
6. no producir si un cambio estratégico relevante está pendiente de sync.

---

## 5. Apify — research para ideas con evidencia

### Qué sí hace

Recolecta datos recientes para detectar:
- formatos repetidos;
- hooks;
- temas;
- visuales;
- estructuras narrativas;
- señales de interacción;
- zeitgeist;
- patrones competitivos.

### Qué NO hace

No garantiza alcance. No demuestra causalidad por sí solo. No convierte una pieza viral ajena en estrategia propia.

### Flujo

```text
PREGUNTA ESTRATÉGICA
↓
APIFY SCRAPE
↓
DATASET
↓
PATTERN EXTRACTION
↓
STRATEGIC FILTER
↓
CONTENT HYPOTHESIS
↓
CALENDAR TEST
↓
MEASUREMENT
```

Documentar:
- `brand_context/research/apify/SOURCES.md`
- `RUN_LOG.md`
- `CONTENT_SIGNAL_LOG.md`

Usar `skills/research-with-apify/SKILL.md`.

---

## 6. Estrategia → calendario → assets necesarios → Jockey

La metodología define la estrategia; el calendario la convierte en producción concreta.

Cada pieza debe registrar, cuando aplique:
- objetivo;
- mensaje;
- formato;
- canal;
- CTA;
- fotografía necesaria;
- assets necesarios;
- assets existentes;
- assets faltantes;
- estado de Higgsfield;
- estado de composición Figma;
- estado final.

### Asset Gap

Antes de generar:
1. buscar primero en Jockey con `skills/media-search-with-jockey/SKILL.md`;
2. revisar `FINAL_ASSETS` y `GENERATED/approved`;
3. revisar `ORIGINALS` y `REFERENCES` si no existe final asset;
4. identificar faltantes reales;
5. generar solo lo necesario.

No producir “por si acaso” sin propósito documentado.

---

## 7. Higgsfield — producción visual

Usar `skills/higgsfield-generate-image/SKILL.md`.

Modelo:

```text
PIEZA / NECESIDAD
+
ORIGINAL
+
REFERENCIA
+
OBSERVACIÓN HUMANA
+
BRAND_CONTEXT/DESIGN
+
BRAND WORLD ADAPTADO
↓
NUEVA FOTOGRAFÍA
```

No pedir reemplazo/montaje. Pedir creación nueva con original como ancla de identidad.

### 7.1 Auto QA

Antes de human review:
- fidelidad del producto;
- artefactos/anatomía;
- composición/luz;
- coherencia con referencia y observación;
- photography system;
- utilidad para la pieza concreta.

### 7.2 Human Review Gate dentro de Higgsfield

La generación permanece en Higgsfield hasta revisión humana.

Mapeo semántico:
- `APPROVED` → descargar;
- `CHANGES REQUESTED` → leer comentario y revisar;
- `PENDING/NEEDS REVIEW` → no descargar.

Los nombres exactos pueden variar según la UI; conservar la lógica.

Comentarios de cambio = delta:
- KEEP;
- CHANGE;
- PROTECT.

No reimaginar lo que no se pidió cambiar.

Solo imagenes aprobadas se registran/suben a Jockey en `GENERATED/approved`. Si se vuelven reutilizables, se promueven a `FINAL_ASSETS`.

---

## 8. Figwright = capa primaria de composición local

Una vez que están listos:
- estrategia;
- calendario/brief;
- copy;
- design context;
- assets aprobados recuperados desde Jockey;

Claude Code usa `skills/design-with-figwright/SKILL.md` → Figwright → Figma Desktop.

Figwright compone la pieza. No sustituye la selección estratégica ni la producción de assets.

---

## 9. Export final desde Figma

El export recién salido de Figma todavía es staging.

Guardar primero en:

`outputs/_staging_exports/`

No marcar como `PUBLISH_READY` todavía.

---

## 10. Metadata2Go — gate final de limpieza

### ¿Hay que limpiar las fotos de Higgsfield antes de Figma?

**No como rutina si solo serán inputs de Figma.** El archivo que realmente importa para publicación es el export final de la composición.

Figma crea un nuevo export PNG/JPG, pero este template no asume una garantía documental de que cualquier metadata quede eliminada. Por eso el punto robusto de control es **después del export final**.

### Flujo recomendado

```text
FIGMA FINAL
↓
EXPORT
↓
_staging_exports
↓
Metadata2Go Remove Metadata
↓
QA visual
↓
(opcional/según riesgo) View Metadata
↓
FINAL OUTPUT
```

### Excepción

Si una imagen aprobada de Higgsfield se publica directamente, sin Figma, sanitizar esa copia final antes de publicación.

### Herramienta

Usar `skills/metadata-clean-final/SKILL.md`.

---

## 11. Outputs

- `media/` = punteros, IDs, colecciones y reglas de Jockey.
- Jockey = originals, references, generated, final assets y video.
- `outputs/_staging_exports/` = archivos temporales previos a sanitización.
- `outputs/ads/`, `organic/`, `campaigns/`, `video/` = entregables finales según función.

No confundir “aprobado para diseño” con “publicable final”.

---

## 12. Checklist de arranque de cliente

### Repo/contexto
- [ ] Crear repo desde plantilla.
- [ ] Mantener núcleo `context/` intacto.
- [ ] Cargar brand world maestro.
- [ ] Poblar `brand_context/`.
- [ ] Completar adaptación, design system y photography system.
- [ ] Configurar `media/` y Jockey con Store ID/link/colecciones.

### Conexiones
- [ ] GitHub clone/update probado.
- [ ] Figma Desktop probado.
- [ ] Figwright MCP + plugin probados.
- [ ] Jockey MCP probado y knowledge store/folder validado.
- [ ] Higgsfield proyecto/folder/preset probados si aplica.
- [ ] Apify plugin/MCP autenticado y Actor+dataset de prueba si habrá research scraping.
- [ ] Metadata2Go Remove Metadata probado para publish-ready.
- [ ] Registrar estados reales en `CONNECTIONS.md`.

### Readiness
- [ ] Pasar `PROJECT_READINESS.md`.
- [ ] Marcar `STATUS.md = READY_FOR_PRODUCTION`.
- [ ] Confirmar remoto actualizado.
- [ ] Clonar/actualizar local.
- [ ] Abrir Claude Code en raíz.

### Producción
- [ ] Research/hipótesis aprobadas cuando aplique.
- [ ] Calendario define assets necesarios.
- [ ] Higgsfield genera solo faltantes.
- [ ] Human review antes de registrar approved en Jockey.
- [ ] Figwright compone en Figma.
- [ ] Export a staging.
- [ ] Metadata2Go limpia archivo publicable.
- [ ] Mover a output final.
