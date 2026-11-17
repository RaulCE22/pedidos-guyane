# REQ-003: Creación y gestión de pedidos

- Estado: Borrador
- Prioridad: Alta
- ADR relacionados: ADR-0002
- Cuestiones abiertas relacionadas: OQ-01, OQ-02, OQ-03, OQ-04

## Propósito

Permitir que un comprador envíe un pedido estructurado a un comercio a través de una campaña activa y que el comerciante consulte los pedidos recibidos.

## Alcance

### Incluye

- Selección de productos y cantidades de una campaña activa.
- Creación de un pedido perteneciente a una sola campaña y comercio.
- Conservación de nombre y precio de cada producto en el momento de confirmar el pedido.
- Consulta de los pedidos de la campaña por el comerciante propietario.

### No incluye

- Carrito multidistribuidor.
- Pago en línea.
- Gestión avanzada de inventario.
- Automatizaciones de preparación o transporte.
- Integración con mensajes de WhatsApp.

## Actores y permisos

- Comprador: crea un pedido en una campaña activa.
- Comerciante: consulta los pedidos de su comercio.
- Un usuario no puede consultar pedidos privados de otro usuario o comercio.

## Requisitos funcionales

### RF-01 — Seleccionar productos

El comprador puede seleccionar productos y cantidades que estén publicados en una campaña activa.

### RF-02 — Crear pedido

El comprador puede confirmar un pedido asociado a una única campaña.

### RF-03 — Límite por comercio

Un pedido contiene productos de una sola campaña y de un solo comercio. Para comprar en dos comercios distintos se crean dos pedidos independientes.

### RF-04 — Snapshot histórico

Al confirmar un pedido, el sistema conserva el nombre del producto y el precio unitario aplicado en ese momento en cada línea del pedido.

### RF-05 — Consulta del comerciante

El comerciante puede consultar los pedidos recibidos en las campañas de su comercio.

### RF-06 — Campaña activa

El servidor debe comprobar que la campaña continúa activa al confirmar el pedido. No basta con comprobarlo únicamente en el frontend.

### RF-07 — Estado del pedido

El sistema permitirá gestionar el estado de los pedidos. El conjunto exacto de estados y las transiciones permitidas quedan pendientes de OQ-04.

## Reglas de negocio

- Un pedido pertenece a un comprador y a una campaña.
- La campaña determina el único comercio al que pertenece el pedido.
- No hay carrito multidistribuidor.
- El pedido conserva una instantánea del nombre y el precio unitario de cada producto.
- Las modificaciones posteriores del catálogo o de los precios de campaña no alteran los pedidos históricos.
- La creación debe validar en el servidor la campaña y los precios aplicables en el momento de confirmar.
- La posibilidad de modificar o cancelar pedidos queda pendiente de OQ-01.
- La modalidad de recogida queda pendiente de OQ-02.
- El ciclo de vida y sus transiciones quedan pendientes de OQ-04.

## Criterios de aceptación

### REQ-003-AC-01 — Pedido de campaña activa

Dada una campaña activa, cuando un comprador confirma los productos seleccionados, entonces se crea un pedido asociado a esa campaña.

### REQ-003-AC-02 — Rechazar campaña no activa

Dada una campaña que ya no está activa, cuando un comprador intenta confirmar un pedido, entonces el servidor rechaza la operación.

### REQ-003-AC-03 — Un solo comercio por pedido

Dado un pedido, cuando se consultan sus líneas, entonces todas pertenecen a la misma campaña y al mismo comercio.

### REQ-003-AC-04 — Conservar nombre y precio

Dado un pedido confirmado, cuando posteriormente se modifica el catálogo o el precio del producto, entonces las líneas del pedido mantienen el nombre y el precio que tenían al confirmar.

### REQ-003-AC-05 — Aislamiento del comerciante

Dado un comerciante, cuando consulta los pedidos, entonces solo obtiene pedidos pertenecientes a su comercio.

## Impacto en datos y API

Entidades principales: `orders` y `order_items`, relacionadas con `campaigns` y `campaign_products`. Consultar [modelo de datos](../architecture/data-model.md).

## Dependencias y preguntas abiertas

- OQ-01: modificación y cancelación.
- OQ-02: recogida.
- OQ-03: necesidad de cuenta para confirmar pedido.
- OQ-04: estados y transiciones.
