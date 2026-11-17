# ADR-0001: Monolito modular y monorepo

- Estado: Aceptado
- Fecha: 2026-11-17

## Contexto

El producto necesita una aplicación web para comerciantes y compradores y una API central. El piloto debe ser sencillo de desarrollar, mantener y operar. No existe una necesidad actual que justifique servicios independientes.

## Decisión

- Utilizar un monorepo administrado con pnpm workspaces.
- Mantener una única SPA React para ambos roles.
- Mantener una única API Node.js + Hono organizada por módulos de dominio.
- Utilizar PostgreSQL y Drizzle ORM para persistencia.
- Utilizar Better Auth para autenticación.
- Compartir esquemas y tipos mediante un paquete de contratos cuando sea necesario.
- Mantener frontend y backend como aplicaciones separadas dentro del mismo repositorio, sin convertirlos en microservicios.

## Opciones consideradas

1. Microservicios: descartados por añadir despliegue, comunicación y operación innecesarios para el alcance inicial.
2. Dos aplicaciones frontend independientes: descartadas porque comerciantes y compradores forman parte del mismo producto y pueden compartir entidades, rutas y componentes.
3. Monolito modular en monorepo: elegido por mantener límites claros sin multiplicar infraestructura.

## Consecuencias

- El desarrollo y el despliegue iniciales son más sencillos.
- Los módulos deben mantener responsabilidades y dependencias claras.
- La separación futura de componentes seguirá siendo posible si aparece una necesidad real.
- No se introduce una plataforma de orquestación ni servicios adicionales en el bootstrap.
