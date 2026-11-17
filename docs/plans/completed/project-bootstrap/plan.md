# Plan de implementación: Bootstrap documental y estructura inicial

- Estado: Completado
- Requisitos: preparación inicial del repositorio
- ADR relacionados: ADR-0001, ADR-0002
- Riesgo: Bajo
- Aprobación: No necesaria para el bootstrap documental

## Objetivo

Preparar un repositorio independiente, con estructura documental y manifiestos pnpm, que Agentic Workbench pueda consultar como proyecto.

## Alcance

### Incluye

- Estructura inicial de monorepo.
- Manifiestos de los tres workspaces.
- Documentación de visión, roadmap, requisitos, arquitectura, datos y decisiones.
- Registro de cuestiones abiertas.
- Convenciones iniciales para agentes.

### No incluye

- Instalación de dependencias ni lockfile.
- Implementación funcional del frontend o la API.
- Esquema Drizzle o migraciones.
- Configuración de despliegue o infraestructura.
- Resolución de cuestiones de producto pendientes.

## Situación actual

Repositorio inicialmente vacío. Se crea la base del proyecto en una rama dedicada.

## Diseño propuesto

Monorepo pnpm con `apps/web`, `apps/api` y `packages/contracts`. La documentación del proyecto queda bajo `docs/`.

## Tareas

| Tarea | Estado | Criterios relacionados |
|---|---|---|
| Crear estructura de workspaces | Completada | Estructura independiente y manifiestos |
| Documentar visión y roadmap | Completada | Alcance y cinco versiones |
| Crear requisitos iniciales | Completada | REQ-001 a REQ-004 |
| Documentar arquitectura y modelo conceptual | Completada | SPA única, API modular y siete entidades |
| Registrar decisiones y preguntas abiertas | Completada | ADR-0001, ADR-0002 y OQ-01 a OQ-06 |
| Verificar el contenido y los límites del cambio | Completada | Sin instalación ni implementación funcional |

## Riesgos y reversión

El principal riesgo es que los requisitos iniciales se interpreten como aprobados cuando todavía hay cuestiones de producto abiertas. Los cuatro requisitos se mantienen en estado Borrador.

La rama puede revisarse o descartarse sin afectar a la rama principal.

## Comandos de verificación

No se ejecutan comandos locales porque la modificación se realiza directamente mediante la API de GitHub. Se comprueba el árbol remoto, la presencia de los archivos y la coherencia de las referencias documentales.

## Condiciones de entrega

- Base documental presente.
- Manifiestos preparados.
- Sin dependencias instaladas, lockfile, funcionalidades ni migraciones.
