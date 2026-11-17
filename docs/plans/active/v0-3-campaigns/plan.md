# Plan de implementación: V0.3 — Campañas

- Estado: Pendiente
- Requisitos: REQ-002
- ADR relacionados: ADR-0001
- Riesgo: Medio
- Aprobación: Pendiente

## Objetivo

Permitir que los comerciantes publiquen campañas con productos del catálogo y precios propios, manteniendo una sola campaña activa por comercio.

## Alcance

### Incluye

- Creación y consulta de campañas.
- Selección de productos del catálogo del mismo comercio.
- Precio por producto y campaña.
- Activación, cierre e historial.
- Protección de la regla de campaña activa única.

### No incluye

- Inventario avanzado.
- Programación compleja de campañas.
- Descuentos y precios dinámicos.

## Tareas

| Tarea | Estado | Criterios relacionados |
|---|---|---|
| Definir los datos y ciclo de vida mínimo de campaña | Pendiente | REQ-002-AC-02, REQ-002-AC-05 |
| Crear campañas para el comercio propio | Pendiente | REQ-002-AC-02 |
| Añadir productos del catálogo con precio de campaña | Pendiente | REQ-002-AC-02, REQ-002-AC-03 |
| Impedir dos campañas activas en un comercio | Pendiente | REQ-002-AC-04 |
| Consultar campañas históricas | Pendiente | REQ-002-AC-05 |
| Impedir pedidos en campañas no activas | Pendiente | REQ-002-AC-06 |

## Criterios de aceptación y relación con pruebas

| Criterio de aceptación | Verificación |
|---|---|
| REQ-002-AC-01 a REQ-002-AC-06 | Pruebas de dominio, persistencia y API |

## Decisiones que requieren aprobación

Definir los estados concretos de campaña y las reglas de edición una vez activada antes de implementarlos.
