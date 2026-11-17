# Plan de implementación: V0.4 — Pedidos

- Estado: Pendiente
- Requisitos: REQ-003
- ADR relacionados: ADR-0002
- Riesgo: Alto
- Aprobación: Pendiente

## Objetivo

Permitir que los compradores realicen pedidos estructurados en campañas activas y que los comerciantes consulten y gestionen los pedidos de su comercio.

## Alcance

### Incluye

- Selección de productos y cantidades.
- Creación de un pedido en una sola campaña.
- Snapshots del nombre y precio de cada producto.
- Consulta de pedidos por el comerciante propietario.
- Estados de pedido, una vez definidos.

### No incluye

- Carrito multidistribuidor.
- Pago en línea.
- Inventario avanzado.
- Flujos de recogida todavía no definidos.

## Tareas

| Tarea | Estado | Criterios relacionados |
|---|---|---|
| Definir estados y transiciones del pedido | Pendiente | REQ-003-AC-01 |
| Implementar creación de pedidos en campañas activas | Pendiente | REQ-003-AC-01, REQ-003-AC-02 |
| Aplicar el límite de un pedido por campaña y comercio | Pendiente | REQ-003-AC-03 |
| Guardar snapshots históricos de nombre y precio | Pendiente | REQ-003-AC-04 |
| Implementar consulta de pedidos del comerciante | Pendiente | REQ-003-AC-05 |
| Verificar autorización y transacciones | Pendiente | REQ-003-AC-02, REQ-003-AC-05 |

## Criterios de aceptación y relación con pruebas

| Criterio de aceptación | Verificación |
|---|---|
| REQ-003-AC-01 a REQ-003-AC-05 | Pruebas unitarias, integración de persistencia y API |

## Decisiones que requieren aprobación

Resolver OQ-01, OQ-02, OQ-03 y OQ-04 antes de cerrar los comportamientos de modificación/cancelación, recogida, acceso y estados.
