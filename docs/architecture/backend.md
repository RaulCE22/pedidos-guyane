# Arquitectura del backend

## Stack

- Node.js 24.
- Hono.
- TypeScript.
- PostgreSQL.
- Drizzle ORM y Drizzle Kit.
- Better Auth.
- Zod.

## Organización por módulos

Los módulos iniciales previstos son:

- `auth`: autenticación y sesión.
- `merchants`: comercio y perfil del comerciante.
- `products`: catálogo permanente.
- `campaigns`: campañas y productos publicados.
- `orders`: pedidos y líneas históricas.

## Responsabilidades

- La capa HTTP define rutas, valida peticiones y transforma respuestas.
- Los casos de uso coordinan acciones y transacciones.
- Las reglas de dominio expresan restricciones del producto.
- La infraestructura contiene las implementaciones de persistencia, autenticación y acceso externo.
- Los contratos Zod compartidos se ubican en `packages/contracts` cuando frontend y backend necesiten la misma definición.

No es obligatorio crear subcarpetas `domain`, `application`, `infrastructure` en cada módulo desde el primer día. Añade separación interna cuando exista lógica suficiente para justificarla.

## Persistencia

PostgreSQL será la fuente de datos de usuarios, comercios, catálogo, campañas y pedidos. Drizzle proporcionará el acceso tipado y las migraciones.

La regla de campaña activa única debe estar protegida en el servidor y en la persistencia, evitando depender exclusivamente del estado de la interfaz.

La creación del pedido debe validar campaña y precio en el servidor y guardar las líneas históricas en una misma operación transaccional.

## Seguridad

- Verificar la sesión y autorización en todas las operaciones privadas.
- Verificar que el comerciante es propietario del comercio consultado o modificado.
- Verificar que el comprador accede únicamente a sus pedidos.
- Validar datos y cantidades en el servidor.
- No confiar en precios, totales, roles o identificadores enviados por el navegador sin comprobarlos.
