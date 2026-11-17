# Hoja de ruta

La hoja de ruta describe entregas funcionales incrementales. No establece fechas ni compromisos de calendario.

## V0.1 — Autenticación y perfiles

- Registro e inicio de sesión.
- Roles de comerciante y comprador.
- Perfil básico del usuario.
- Asociación de un comerciante con su único comercio.

## V0.2 — Comercios y catálogo

- Consulta de comercios.
- Gestión del comercio propio.
- Alta, edición y consulta del catálogo permanente de productos.

## V0.3 — Campañas

- Crear campañas.
- Seleccionar productos del catálogo.
- Establecer precios propios de cada campaña.
- Activar y cerrar campañas.
- Garantizar que solo exista una campaña activa por comercio.
- Consultar campañas anteriores.

## V0.4 — Pedidos

- Consultar campañas activas.
- Seleccionar productos y cantidades.
- Crear un pedido asociado a una sola campaña y comercio.
- Consultar pedidos del comerciante.
- Actualizar el estado de los pedidos una vez definido su ciclo de vida.

## V0.5 — Historial y piloto

- Consultar el historial de pedidos del comprador.
- Completar las decisiones pendientes sobre recogida, cancelación, acceso y estados.
- Probar el flujo completo con comercios reales.
- Recoger feedback de compradores y comerciantes.
- Evaluar el valor del producto y la posible disposición a pagar en el futuro.

## Condiciones para ampliar el alcance

- El flujo anterior debe funcionar y estar verificado.
- Las decisiones de producto abiertas deben resolverse antes de implementar comportamientos dependientes de ellas.
- Se prioriza completar un flujo vertical pequeño frente a crear funcionalidades parciales o sistemas generales.
