# CONNECTIONS.md — Estado de integraciones y preflight

> Archivo variable por cliente/operador. La estructura del repo no basta: una integración crítica sin configurar puede bloquear producción. `OPERATIONS.md` define cómo conectar y verificar cada herramienta; aquí se registra el estado real.

## Regla

Estados permitidos:
- `READY`
- `NOT_CONFIGURED`
- `BLOCKED`
- `NOT_REQUIRED`

No marcar una conexión como `READY` solo porque exista un README. Debe haberse probado en el entorno que la va a usar.

## GitHub / repo
- Estado: NOT_CONFIGURED
- Repo remoto: POR DEFINIR
- Branch: main
- Lectura/clonado validado: POR DEFINIR
- Write-back disponible: POR DEFINIR
- Último commit remoto validado: POR DEFINIR

## Figma Desktop
- Estado: NOT_CONFIGURED
- Archivo/proyecto principal: POR DEFINIR
- Página/sistema base: POR DEFINIR
- Última prueba: POR DEFINIR

## Figwright MCP
- Estado: NOT_CONFIGURED
- Servidor MCP detectado por Claude Code: POR DEFINIR
- Plugin local conectado a Figma Desktop: POR DEFINIR
- Última prueba de lectura/escritura: POR DEFINIR

## Jockey MCP
- Estado: NOT_CONFIGURED
- Endpoint: `${JOCKEY_MCP_URL:-https://mcp.twelvelabs.io/jockey/mcp}`
- OAuth validado: POR DEFINIR
- Knowledge store/folder de marca: POR DEFINIR
- Store ID: POR DEFINIR
- Link directo documentado en `media/JOCKEY_LIBRARY.md`: POR DEFINIR
- Busqueda de prueba ejecutada: POR DEFINIR
- Consulta de colecciones/metadata validada: POR DEFINIR
- Alta/registro de media aprobada validado: POR DEFINIR

## Higgsfield Cinema Studio
- Estado: NOT_CONFIGURED
- Proyecto del cliente: POR DEFINIR
- Folder/categoría: POR DEFINIR
- Sesión accesible: POR DEFINIR
- Preset/cámara documentado: POR DEFINIR
- Última prueba de generación: POR DEFINIR

## Apify
- Estado: NOT_CONFIGURED
- Apify plugin/MCP habilitado en Claude Code: POR DEFINIR
- OAuth/token validado: POR DEFINIR
- Actor de prueba ejecutado: POR DEFINIR
- Dataset de prueba recuperado: POR DEFINIR
- Última prueba: POR DEFINIR

## Metadata2Go
- Estado: NOT_CONFIGURED
- Acceso web validado: POR DEFINIR
- Flujo `Remove Metadata` validado con export de prueba: POR DEFINIR
- Verificación posterior de metadatos: POR DEFINIR
- Última prueba: POR DEFINIR

## Publicación / distribución
- Herramienta: POR DEFINIR
- Estado: NOT_REQUIRED
- Última prueba: POR DEFINIR

## Bloqueos activos
POR DEFINIR
