# Guía: Manejo de Batches en Figwright (MCP de Figma)

## Qué pasó
En un proyecto grande, el `batch` de Figwright se quedó a medio camino. Causas probables:
- El mensaje entre el plugin de Figwright y el sandbox de Figma tiene un límite de tamaño de payload — un batch con demasiadas operaciones o nodos pesados puede truncarse o fallar por timeout.
- Figma también tiene un tope práctico de nodos/complejidad por archivo o página — con muchos nodos ya cargados, cada operación se vuelve más costosa y aumenta el riesgo de fallo.
- Ambos factores se agravan entre sí: archivo pesado + batch grande = más probabilidad de romperse.

## Regla base para cuidar el batch

### Tamaño del batch
- Máximo ~15-20 operaciones por llamada a `batch`.
- Si el proyecto necesita más, se divide en varias llamadas secuenciales, nunca una sola gigante.
- Operaciones pesadas (frames con auto-layout, texto con estilos, imágenes) van en batches más chicos: 5-10.

### Antes de empezar algo grande
1. `get_document` o `scan_components` para ver cuántos nodos ya existen en la página.
2. Planear el trabajo en secciones lógicas (ej: Header, Cards, Footer) y tratar cada sección como su propio grupo de batches.

### Durante el trabajo
3. Después de cada batch grande, correr `ping` para confirmar que el plugin sigue respondiendo antes de mandar el siguiente.
4. Si algo falla a medio camino, revisar el estado con `get_document` / `get_selection` antes de reintentar — nunca reintentar a ciegas, porque puede quedar un estado mixto.

### Organización del archivo
5. Usar `create_section` para dividir el canvas por bloques del proyecto — si algo falla, se sabe exactamente qué sección quedó incompleta.
6. Para componentes repetidos (botones, cards), crear el componente base una vez con `create_component` y reutilizar con `create_instance` en vez de recrear la estructura completa cada vez — reduce drásticamente el número total de operaciones.

---
*Guardado también como memoria persistente para futuras sesiones (feedback-figwright-batch-size).*
