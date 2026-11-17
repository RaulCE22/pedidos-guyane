# ADR-0002: Un pedido pertenece a una campaña y conserva snapshots históricos

- Estado: Aceptado
- Fecha: 2026-11-17

## Contexto

El producto organiza la compra alrededor de campañas publicadas por comercios. Un comprador puede comprar en distintos comercios, pero la gestión de cada pedido debe quedar claramente separada. Además, los productos y sus precios pueden cambiar después de una compra.

## Decisión

- Cada pedido pertenece a una única campaña.
- Cada campaña pertenece a un único comercio; por tanto, cada pedido corresponde a un único comercio.
- No existe carrito multidistribuidor.
- Para comprar en dos comercios distintos, el comprador crea dos pedidos independientes.
- Cada línea del pedido conserva el nombre del producto y el precio unitario aplicados en el momento de confirmar el pedido.
- Los cambios posteriores del catálogo o de los precios de campaña no alteran pedidos existentes.

## Opciones consideradas

1. Carrito que agrupa comercios: descartado porque complica pagos, preparación, recogida y responsabilidades de cada comercio.
2. Pedidos separados por comercio: elegido porque mantiene un flujo sencillo y responsabilidades claras.
3. Recalcular el histórico desde el catálogo actual: descartado porque perdería la información exacta de lo que se compró y a qué precio.

## Consecuencias

- El modelo de pedidos queda ligado a una campaña.
- El servidor debe validar la campaña y los precios al confirmar el pedido.
- Las líneas deben almacenar snapshots y no depender del nombre o precio actual del catálogo para mostrar el historial.
- El comprador podrá consultar pedidos de diferentes comercios como registros separados.
