# Plan de implementación: V0.2 — Comercios y catálogo

- Estado: Pendiente
- Requisitos: REQ-001, REQ-002
- ADR relacionados: ADR-0001
- Riesgo: Medio
- Aprobación: Pendiente

## Objetivo

Permitir que cada comerciante gestione la información básica de su comercio y mantenga un catálogo permanente de productos.

## Alcance

### Incluye

- Consulta de comercios.
- Gestión del comercio propio.
- Alta, edición y consulta de productos del catálogo.

### No incluye

- Inventario avanzado ni reservas de stock.
- Campañas comerciales, que corresponden a V0.3.

## Tareas

| Tarea | Estado | Criterios relacionados |
|---|---|---|
| Definir los datos básicos del comercio | Pendiente | REQ-001-AC-02 |
| Implementar consulta y edición del comercio propio | Pendiente | REQ-001-AC-02, REQ-001-AC-03 |
| Implementar el catálogo permanente de productos | Pendiente | REQ-002-AC-01 |
| Verificar separación de datos entre comercios | Pendiente | REQ-001-AC-03 |

## Criterios de aceptación y relación con pruebas

| Criterio de aceptación | Verificación |
|---|---|
| REQ-001-AC-02 | Pruebas de propiedad del comercio |
| REQ-001-AC-03 | Pruebas de autorización |
| REQ-002-AC-01 | Pruebas CRUD del catálogo |

## Decisiones que requieren aprobación

No se añaden campos de producto ni de comercio que no sean necesarios para el flujo acordado.
