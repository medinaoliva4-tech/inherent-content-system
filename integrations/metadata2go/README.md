# Metadata2Go — limpieza de metadatos antes de publicación

## Rol

Metadata2Go se usa como **gate de sanitización del archivo final que realmente se va a publicar o entregar**.

Herramienta principal:
- `https://www.metadata2go.com/delete-metadata`

La página `edit-metadata` sirve para editar campos. Para la regla de privacidad de este sistema, el default es **Remove Metadata**, no editar manualmente los campos.

## Cuándo limpiar

### Arte final exportado desde Figma

No limpiar cada fotografía fuente antes de componer solo por rutina.

Flujo preferido:

```text
Jockey assets aprobados
        ↓
FIGMA
        ↓
EXPORT FINAL
        ↓
outputs/_staging_exports/
        ↓
Metadata2Go — Remove Metadata
        ↓
verificación
        ↓
destino final en outputs/
```

La razón operativa: el archivo que importa para privacidad/publicación es el **export final**. No asumir que Figma garantiza por documentación que el export queda sin metadata; verificar y sanitizar el archivo final.

### Imagen de Higgsfield que se publica sola

Si una imagen aprobada de Higgsfield se va a publicar o entregar directamente sin pasar por Figma, sanitizar esa imagen final antes de moverla a su destino publicable.

### Imagen que solo será input de Figma

Puede permanecer como master aprobado en Jockey. No necesita pasar por Metadata2Go antes de Figma únicamente por rutina, porque luego se genera otro archivo final.

## Proceso

1. Subir el export final a Metadata2Go Remove Metadata.
2. Ejecutar la eliminación.
3. Descargar el archivo procesado.
4. Verificar visualmente que no cambió la pieza.
5. Verificar metadata con el viewer cuando el nivel de riesgo lo requiera.
6. Mover el archivo limpio al folder final de `outputs/`.
7. No considerar una pieza `PUBLISH_READY` antes de este gate cuando aplique.

## Privacidad

Metadata2Go es un servicio externo. No subir material sujeto a restricciones contractuales que prohíban procesamiento por terceros sin autorización. Documentar cualquier excepción.

## Automatización

Este template no asume que Metadata2Go exponga API/MCP. Tratarlo como paso web/browser. Si el entorno no puede operar el navegador, el gate permanece manual y debe registrarse como pendiente; no saltarlo silenciosamente.

## Skill

Usar `skills/metadata-clean-final/SKILL.md`.
