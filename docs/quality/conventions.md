# Convenciones de desarrollo

## Idioma

- Documentación, requisitos, decisiones y comunicación con el usuario: español.
- Código, identificadores, nombres de paquetes, rutas técnicas y claves estructuradas: inglés.
- El idioma inicial de la interfaz no está decidido; consultar OQ-05.

## TypeScript

- Mantener TypeScript en modo estricto.
- Evitar `any`; preferir tipos explícitos y `unknown` en límites de confianza.
- Validar datos externos con Zod.
- No duplicar contratos entre frontend y backend cuando puedan compartirse de forma coherente.

## Frontend

- Una sola SPA para ambos roles.
- Seguir la estructura modular descrita en [arquitectura frontend](../architecture/frontend.md).
- TanStack Query para datos remotos.
- React Hook Form para formularios.
- No añadir estado global de cliente sin una necesidad demostrada.
- Mantener componentes de presentación separados de la lógica de negocio.

## Backend

- Hono para HTTP.
- Separar handlers, casos de uso y persistencia según la complejidad real.
- Validar autorización en el servidor.
- No confiar en precios, totales ni permisos enviados por el cliente.
- Utilizar transacciones para operaciones que deban mantener consistencia.

## Persistencia

- PostgreSQL con Drizzle.
- Añadir migraciones versionadas cuando se implemente el esquema.
- Proteger las invariantes del negocio en servidor y base de datos cuando sea posible.
- Guardar snapshots históricos en las líneas de pedido.

## Dependencias

- Usar pnpm.
- Mantener versiones fijadas en los manifiestos.
- Añadir solo dependencias necesarias para una funcionalidad aprobada.
- No añadir herramientas de monorepo u orquestación sin necesidad.

## Alcance

No introducir WhatsApp, IA, pagos, suscripciones, logística avanzada o funcionalidades fuera del roadmap sin un requisito y una decisión explícitos.
