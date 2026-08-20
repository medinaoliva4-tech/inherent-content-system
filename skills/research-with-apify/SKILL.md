---
name: research-with-apify
description: Usa Apify para recolectar señales externas de contenido, formatos, competidores o tendencias y convertirlas en hipótesis de contenido alineadas a ICP, posicionamiento, promesa y calendario. Úsala antes de ideación/calendario cuando se necesite evidencia reciente de qué está captando atención. No promete ni garantiza alcance y no debe copiar contenido ajeno.
---

# Research de contenido con Apify

## Propósito

Reducir ideación ciega mediante evidencia reciente, sin convertir el sistema en una fábrica de tendencias desconectadas de la marca.

## Gate 0 — conexión

1. Leer `CONNECTIONS.md`.
2. Confirmar `Apify: READY`.
3. Si no está listo, seguir el setup de `integrations/apify/README.md` y `OPERATIONS.md`.
4. No fingir que se ejecutó scraping si no existe conexión y una corrida real.

## Gate 1 — pregunta estratégica

Definir antes de scrapear:

```text
OBJETIVO:
PLATAFORMA/S:
ICP/SEGMENTO:
PILAR/PROBLEMA:
QUÉ QUEREMOS APRENDER:
VENTANA TEMPORAL:
MERCADO/IDIOMA:
SEÑALES A OBSERVAR:
```

## Seleccionar Actor

Usar Apify para buscar el Actor más adecuado a la plataforma/superficie y revisar su input/output antes de ejecutarlo.

No fijar un Actor universal en esta plantilla; la Store y las necesidades cambian.

## Ejecutar pequeño antes de escalar

1. hacer una muestra pequeña;
2. validar que los campos sirven;
3. solo después ampliar la corrida;
4. registrar Actor, fecha, input y dataset/run ID en `brand_context/research/apify/RUN_LOG.md`.

## Analizar

Separar:
- alcance/engagement visible;
- estructura del hook;
- formato;
- tema;
- ritmo/narrativa;
- visual;
- CTA;
- señales de comentarios;
- relación aparente con la audiencia.

No atribuir causalidad que los datos no demuestran.

## Convertir en hipótesis

Cada hallazgo útil debe responder:

1. ¿qué mecanismo parece estar funcionando?
2. ¿por qué podría importar a nuestro ICP?
3. ¿refuerza nuestro posicionamiento/promesa?
4. ¿qué principio podemos adaptar sin copiar?
5. ¿qué prueba concreta haremos?
6. ¿qué métrica de media y de negocio observaremos?

Guardar conclusiones en `CONTENT_SIGNAL_LOG.md` y, si se aprueban, trasladarlas al `CONTENT_SYSTEM.md` o al calendario.

## Regla de alcance

Apify aporta señales, no garantías. Nunca escribir “esto garantiza alcance”. Usar formulaciones como:
- señal fuerte;
- formato observado repetidamente;
- hipótesis con evidencia reciente;
- candidato a prueba.

## Salida

El research termina cuando existe una decisión operable:

```text
SEÑAL
↓
EXPLICACIÓN
↓
ENCAJE ESTRATÉGICO
↓
HIPÓTESIS
↓
PIEZA/CALENDARIO DE PRUEBA
↓
MEDICIÓN
```
