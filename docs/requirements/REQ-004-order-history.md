# REQ-004: Historial de pedidos

- Estado: Borrador
- Prioridad: Media
- ADR relacionados: ADR-0002

## Propósito

Permitir que el comprador consulte los pedidos que ha realizado en distintos comercios y campañas.

## Alcance

### Incluye

- Listado de pedidos propios del comprador.
- Identificación del comercio y de la campaña a los que pertenece cada pedido.
- Consulta de las líneas y los importes históricos guardados en el pedido.

### No incluye

- Analítica de compras.
- Exportación contable.
- Repetición automática de pedidos.
- Historial compartido entre compradores.

## Actores y permisos

El comprador consulta únicamente sus propios pedidos. El comerciante consulta los pedidos de su comercio mediante las capacidades descritas en REQ-003.

## Requisitos funcionales

### RF-01 — Listar pedidos propios

El comprador puede consultar los pedidos que ha realizado.

### RF-02 — Consultar detalle

El comprador puede abrir un pedido y consultar sus productos, cantidades, precios y comercio.

### RF-03 — Histórico estable

El historial muestra los datos conservados al confirmar el pedido y no valores recalculados a partir del catálogo actual.

## Reglas de negocio

- El historial pertenece al comprador autenticado.
- Un pedido conserva su asociación a una campaña y comercio.
- Los importes históricos se obtienen de los snapshots almacenados en las líneas del pedido.

## Criterios de aceptación

### REQ-004-AC-01 — Listado de pedidos

Dado un comprador con pedidos realizados, cuando accede a su historial, entonces puede consultar únicamente sus propios pedidos.

### REQ-004-AC-02 — Detalle histórico

Dado un pedido del comprador, cuando consulta su detalle, entonces ve los productos y precios guardados al confirmar el pedido.

### REQ-004-AC-03 — Separación entre compradores

Dado un comprador, cuando intenta consultar el pedido de otro comprador, entonces la operación no está autorizada.

## Impacto en datos y API

Se apoya en `orders` y `order_items`. No requiere una entidad adicional para el historial.

## Dependencias y preguntas abiertas

La consulta del historial requiere identidad de comprador. La política de sesión y acceso previo a la confirmación está pendiente de OQ-03.
