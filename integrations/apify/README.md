# Apify — research de señales de contenido

## Rol

Apify se usa para recolectar evidencia externa y reciente que ayude a formular **hipótesis de contenido con mayor probabilidad de captar atención**.

No reemplaza:
- `context/`;
- estrategia de marca;
- ICP;
- posicionamiento;
- promesa;
- criterio creativo.

No existe un scraper que garantice alcance. Los datos de Apify deben convertirse en señales y patrones, y luego filtrarse por la estrategia de la marca.

## Setup preferido en Claude Code

Apify ofrece integración oficial para Claude Code mediante su plugin/MCP.

1. Abrir `/mcp` en Claude Code.
2. Localizar `plugin:apify:apify`.
3. Habilitarlo.
4. Autenticar mediante OAuth cuando se vaya a ejecutar Actors o leer datos privados.
5. Probar búsqueda de Actors.
6. Probar una ejecución pequeña.
7. Recuperar el dataset resultante.
8. Registrar `READY` en `CONNECTIONS.md` solo después de la prueba completa.

Alternativa documentada por Apify: instalar su MCP server mediante CLI o conectar `https://mcp.apify.com`, según el cliente compatible.

## Qué guardar en el repo

No es necesario versionar datasets gigantes.

Guardar en:

`brand_context/research/apify/`

- fuente/plataforma;
- Actor usado;
- fecha;
- query/criterio;
- dataset/run ID o URL cuando corresponda;
- muestra analizada;
- señales encontradas;
- patrones;
- implicaciones;
- hipótesis de formato/mensaje;
- decisión final.

## Regla anti-copia

Scrapear para entender patrones, no para clonar piezas ajenas.

Extraer, por ejemplo:
- estructura de hooks;
- formatos;
- duración;
- secuencia narrativa;
- temas recurrentes;
- tipo de visual;
- relación entre interacción visible y propuesta;
- frecuencia de patrones.

Luego adaptar a:
- ICP;
- posicionamiento;
- promesa;
- pilares;
- design system;
- calendario.

## Skill

Usar `skills/research-with-apify/SKILL.md`.
