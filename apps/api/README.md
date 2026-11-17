# API

API única basada en Node.js, Hono y TypeScript. Organiza la lógica por módulos de dominio:

- `auth`: autenticación y sesión.
- `merchants`: comercio y perfil del comerciante.
- `products`: catálogo permanente.
- `campaigns`: campañas y productos publicados.
- `orders`: pedidos y líneas históricas.

La infraestructura de PostgreSQL y Drizzle se mantiene separada de las reglas de negocio. Los handlers HTTP validan entradas y delegan en los casos de uso correspondientes. No crees módulos vacíos ni capas teóricas que no tengan una responsabilidad implementada.
