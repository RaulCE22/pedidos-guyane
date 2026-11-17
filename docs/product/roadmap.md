# Hoja de ruta

La hoja de ruta describe entregas funcionales incrementales. No establece fechas ni compromisos de calendario. Cada hito declara su objetivo y enlaza los requisitos y el plan que lo organiza. El estado de cada hito se deriva de sus planes; no se mantiene un estado manual duplicado.

## V0.1 — Autenticación y perfiles

**Objetivo:** permitir que comerciantes y compradores dispongan de una identidad en la aplicación y que cada comerciante tenga asociado su único comercio.

- Registro e inicio de sesión.
- Roles de comerciante y comprador.
- Perfil básico del usuario.
- Asociación de un comerciante con su único comercio.

Requisitos: [REQ-001](../requirements/REQ-001-users-and-merchants.md)

Planes: [Plan V0.1](../plans/active/v0-1-authentication-profiles/plan.md)

## V0.2 — Comercios y catálogo

**Objetivo:** permitir que cada comerciante gestione la información básica de su comercio y mantenga un catálogo permanente de productos.

- Consulta de comercios.
- Gestión del comercio propio.
- Alta, edición y consulta del catálogo permanente de productos.

Requisitos: [REQ-001](../requirements/REQ-001-users-and-merchants.md), [REQ-002](../requirements/REQ-002-products-and-campaigns.md)

Planes: [Plan V0.2](../plans/active/v0-2-merchants-catalog/plan.md)

## V0.3 — Campañas

**Objetivo:** permitir que los comerciantes publiquen campañas con productos de su catálogo y precios propios de cada campaña, manteniendo una única campaña activa por comercio.

- Crear campañas.
- Seleccionar productos del catálogo.
- Establecer precios propios de cada campaña.
- Activar y cerrar campañas.
- Garantizar que solo exista una campaña activa por comercio.
- Consultar campañas anteriores.

Requisitos: [REQ-002](../requirements/REQ-002-products-and-campaigns.md)

Planes: [Plan V0.3](../plans/active/v0-3-campaigns/plan.md)

## V0.4 — Pedidos

**Objetivo:** permitir que los compradores realicen pedidos estructurados en campañas activas y que los comerciantes consulten y gestionen los pedidos de su comercio.

- Consultar campañas activas.
- Seleccionar productos y cantidades.
- Crear un pedido asociado a una sola campaña y comercio.
- Consultar pedidos del comerciante.
- Actualizar estados una vez definido su ciclo de vida.

Requisitos: [REQ-003](../requirements/REQ-003-orders.md)

Planes: [Plan V0.4](../plans/active/v0-4-orders/plan.md)

## V0.5 — Historial y piloto

**Objetivo:** completar la consulta del historial del comprador y validar el flujo de campañas y pedidos con comercios reales.

- Consultar el historial de pedidos del comprador.
- Resolver las decisiones pendientes sobre recogida, cancelación, acceso y estados.
- Probar el flujo completo con comercios reales.
- Recoger feedback de compradores y comerciantes.
- Evaluar el valor del producto y la posible disposición a pagar en el futuro.

Requisitos: [REQ-003](../requirements/REQ-003-orders.md), [REQ-004](../requirements/REQ-004-order-history.md)

Planes: [Plan V0.5](../plans/active/v0-5-history-pilot/plan.md)

## Condiciones para ampliar el alcance

- El flujo anterior debe funcionar y estar verificado.
- Las decisiones de producto abiertas deben resolverse antes de implementar comportamientos dependientes de ellas.
- Se prioriza completar un flujo vertical pequeño frente a crear funcionalidades parciales o sistemas generales.
