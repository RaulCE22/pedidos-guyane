# Plan de implementación: V0.5 — Historial y piloto

- Estado: Pendiente
- Requisitos: REQ-003, REQ-004
- ADR relacionados: ADR-0002
- Riesgo: Medio
- Aprobación: Pendiente

## Objetivo

Completar la consulta del historial del comprador y validar el flujo de campañas y pedidos con comercios reales.

## Alcance

### Incluye

- Historial de pedidos del comprador.
- Detalle histórico de los pedidos.
- Resolución de decisiones pendientes necesarias para el piloto.
- Pruebas del flujo completo con comercios reales.

### No incluye

- Suscripciones, membresías ni facturación.
- Pagos en línea.
- Analítica avanzada o automatizaciones complejas.

## Tareas

| Tarea | Estado | Criterios relacionados |
|---|---|---|
| Implementar listado de pedidos propios | Pendiente | REQ-004-AC-01 |
| Implementar detalle histórico de pedido | Pendiente | REQ-004-AC-02 |
| Verificar separación de pedidos entre compradores | Pendiente | REQ-004-AC-03 |
| Resolver cuestiones abiertas necesarias para el piloto | Pendiente | REQ-003-AC-01 |
| Validar el flujo completo con comercios y compradores | Pendiente | REQ-003-AC-01, REQ-004-AC-01 |

## Criterios de aceptación y relación con pruebas

| Criterio de aceptación | Verificación |
|---|---|
| REQ-004-AC-01 a REQ-004-AC-03 | Pruebas de API y de interfaz |
| Flujo del piloto | Prueba guiada con comercios y compradores |

## Decisiones que requieren aprobación

Las cuestiones pendientes deben resolverse y documentarse antes de implementar los comportamientos afectados.
