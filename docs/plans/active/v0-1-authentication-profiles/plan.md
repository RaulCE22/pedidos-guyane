# Plan de implementación: V0.1 — Autenticación y perfiles

- Estado: Pendiente
- Requisitos: REQ-001
- ADR relacionados: ADR-0001
- Riesgo: Medio
- Aprobación: Pendiente

## Objetivo

Permitir que comerciantes y compradores dispongan de una identidad en la aplicación y que cada comerciante tenga asociado un único comercio.

## Alcance

### Incluye

- Registro e inicio de sesión.
- Identificación de los perfiles de comerciante y comprador.
- Perfil básico.
- Asociación de un usuario comerciante con su único comercio.

### No incluye

- Acceso público final a campañas, pendiente de OQ-03.
- Gestión de empleados.
- Roles administrativos adicionales.

## Tareas

| Tarea | Estado | Criterios relacionados |
|---|---|---|
| Definir el flujo de registro e inicio de sesión | Pendiente | REQ-001-AC-01 |
| Implementar perfiles de comerciante y comprador | Pendiente | REQ-001-AC-01, REQ-001-AC-04 |
| Implementar la asociación única entre comerciante y comercio | Pendiente | REQ-001-AC-02 |
| Verificar el aislamiento de los datos privados del comercio | Pendiente | REQ-001-AC-03 |

## Criterios de aceptación y relación con pruebas

| Criterio de aceptación | Verificación |
|---|---|
| REQ-001-AC-01 | Pruebas de autenticación y perfiles |
| REQ-001-AC-02 | Pruebas de unicidad de asociación |
| REQ-001-AC-03 | Pruebas de autorización |
| REQ-001-AC-04 | Pruebas de identidad del comprador |

## Decisiones que requieren aprobación

Resolver OQ-03 antes de cerrar el diseño del acceso público y del registro previo a una compra.
