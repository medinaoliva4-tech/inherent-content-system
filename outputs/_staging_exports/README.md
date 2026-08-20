# _staging_exports

Zona temporal para exports finales recién salidos de Figma **antes** del gate de sanitización de metadatos.

Flujo:

```text
Figma export
↓
_staging_exports/
↓
Metadata2Go Remove Metadata
↓
QA visual/metadata
↓
outputs/organic | ads | campaigns | otro destino final
```

No tratar archivos de este folder como `PUBLISH_READY`.

El README sí se versiona; los archivos temporales pueden limpiarse después de completar el gate.
