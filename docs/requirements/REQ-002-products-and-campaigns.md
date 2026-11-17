# REQ-002: Catálogo de productos y campañas

- Estado: Borrador
- Prioridad: Alta
- ADR relacionados: ADR-0001

## Propósito

Permitir que cada comerciante mantenga un catálogo de productos y publique campañas seleccionando qué productos ofrece en cada una.

## Alcance

### Incluye

- Catálogo permanente por comercio.
- Alta, edición y consulta de productos.
- Creación de campañas.
- Selección de productos del catálogo para cada campaña.
- Precio asociado al producto dentro de la campaña.
- Una única campaña activa por comercio.
- Consulta del historial de campañas.

### No incluye

- Inventario avanzado, reservas de stock o sincronización de existencias.
- Carrito que combine campañas o comercios.
- Programación de campañas con reglas complejas.
- Precios dinámicos o descuentos avanzados.

## Actores y permisos

El comerciante gestiona exclusivamente el catálogo y las campañas de su propio comercio. Los compradores consultan las campañas que el producto permita mostrar según las decisiones de acceso pendientes.

## Requisitos funcionales

### RF-01 — Catálogo permanente

El comerciante puede mantener una lista de productos de su comercio y actualizar sus datos.

### RF-02 — Crear campaña

El comerciante puede crear una campaña para su comercio.

### RF-03 — Publicar productos en campaña

El comerciante puede seleccionar productos de su catálogo e incluirlos en una campaña.

### RF-04 — Precio de campaña

El comerciante puede establecer el precio al que se ofrece cada producto en esa campaña, sin modificar necesariamente el precio base del catálogo.

### RF-05 — Campaña activa única

Un comercio solo puede tener una campaña activa a la vez.

### RF-06 — Historial

El comerciante puede consultar las campañas anteriores de su comercio.

### RF-07 — Pedidos solo en campañas activas

La creación de pedidos solo está permitida para una campaña activa. El detalle del flujo de compra se define en REQ-003.

## Reglas de negocio

- Los productos pertenecen al catálogo de un único comercio.
- Las campañas pertenecen a un único comercio.
- Los productos publicados en una campaña deben proceder del catálogo de ese mismo comercio.
- El precio publicado en campaña es propio de la relación entre campaña y producto.
- No puede haber dos campañas activas del mismo comercio.
- No se presupone gestión de existencias ni reserva de stock.

## Criterios de aceptación

### REQ-002-AC-01 — Mantener catálogo

Dado un comerciante, cuando accede a su catálogo, entonces puede consultar y actualizar los productos de su comercio.

### REQ-002-AC-02 — Crear campaña con productos

Dado un comerciante con productos en su catálogo, cuando crea una campaña, entonces puede seleccionar qué productos incluir.

### REQ-002-AC-03 — Precio específico

Dado un producto incluido en una campaña, cuando se consulta esa campaña, entonces se utiliza el precio establecido para esa campaña.

### REQ-002-AC-04 — Campaña activa única

Dado un comercio con una campaña activa, cuando intenta activar otra campaña, entonces el sistema impide que ambas permanezcan activas simultáneamente.

### REQ-002-AC-05 — Historial de campañas

Dado un comerciante con campañas anteriores, cuando consulta sus campañas, entonces puede distinguir la campaña activa de las campañas históricas.

### REQ-002-AC-06 — Campaña cerrada

Dada una campaña que no está activa, cuando un comprador intenta iniciar un pedido, entonces el sistema no permite crear ese pedido.

## Impacto en datos y API

Entidades principales: `products`, `campaigns` y `campaign_products`. Consultar [modelo de datos](../architecture/data-model.md).

## Dependencias y preguntas abiertas

Los estados concretos de campaña y las reglas de edición una vez activada se detallarán antes de implementar esos comportamientos si resultan necesarios.
