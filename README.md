# Pedidos Guyane

Aplicación web para que pequeños comercios y productores locales publiquen campañas de productos y reciban pedidos estructurados de sus clientes.

El objetivo inicial es validar el flujo con comercios reales de Guayana Francesa. El piloto será gratuito; no se implementarán suscripciones ni pagos en esta primera etapa.

## Estado del proyecto

El repositorio contiene la base documental y la estructura inicial del monorepo. Todavía no hay funcionalidades de aplicación implementadas ni dependencias instaladas.

## Documentación

- [Visión del producto](docs/product/vision.md)
- [Hoja de ruta](docs/product/roadmap.md)
- [Cuestiones abiertas](docs/product/open-questions.md)
- [Índice documental](docs/README.md)
- [Arquitectura](docs/architecture/overview.md)

## Estructura

- `apps/web`: aplicación React para comerciantes y compradores.
- `apps/api`: API Node.js + Hono.
- `packages/contracts`: contratos y esquemas Zod compartidos.
- `docs`: documentación de producto e ingeniería.

## Entorno previsto

- Node.js `24.15.0`
- pnpm `10.28.2`

Las dependencias están declaradas en los manifiestos de cada workspace. Aún no se ha generado el lockfile. Cuando se vaya a iniciar el desarrollo y se revise esta base, ejecutar `pnpm install` desde la raíz.
