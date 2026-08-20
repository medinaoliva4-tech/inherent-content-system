---
name: metadata-clean-final
description: Sanitiza metadatos del archivo final que se va a publicar o entregar usando Metadata2Go Remove Metadata. Úsala después del export final de Figma, o sobre una imagen aprobada que vaya directo a publicación sin pasar por Figma. No la uses como paso rutinario sobre cada input si luego se volverá a exportar en Figma.
---

# Limpiar metadata del arte final

## Principio

Limpiar **el archivo que realmente saldrá al público**.

No asumir que una herramienta anterior ya eliminó metadatos. No asumir que Figma documenta una garantía de sanitización EXIF/IPTC.

## Entrada

Uno de estos casos:

### A. Arte final desde Figma
- exportar primero desde Figma;
- guardar temporalmente en `outputs/_staging_exports/`;
- sanitizar ese export.

### B. Imagen aprobada que se publica sola
- tomar la imagen aprobada;
- sanitizar antes de colocar la copia publicable en su destino final.

## Procedimiento

1. Abrir `https://www.metadata2go.com/delete-metadata`.
2. Subir el archivo final.
3. Ejecutar `Start`.
4. Descargar el resultado.
5. Verificar que dimensiones, formato y aspecto visual siguen correctos.
6. Cuando el nivel de riesgo lo requiera, revisar el archivo limpio con Metadata2Go View Metadata.
7. Mover la versión sanitizada al destino final en `outputs/`.
8. Eliminar el staging local cuando ya no sea necesario.

## Bloqueo

Si el archivo debe publicarse y este gate está requerido pero no puede completarse, marcar:

`FINAL_ASSET_STATUS: BLOCKED_METADATA_SANITIZATION`

No afirmar que la pieza está `PUBLISH_READY`.

## Privacidad

Metadata2Go es un tercero. Si el proyecto prohíbe subir archivos a servicios externos, detenerse y pedir/usar un método aprobado alternativo; no romper una restricción contractual para cumplir el gate.
