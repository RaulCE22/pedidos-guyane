# Arquitectura del frontend

## Aplicación única

El producto tendrá una sola SPA React + Vite. Las experiencias de comerciante y comprador se organizan mediante rutas y permisos dentro de la misma aplicación.

No se crean dos aplicaciones frontend independientes.

## Stack

- React y TypeScript.
- Vite.
- React Router.
- TanStack Query para estado remoto.
- React Hook Form para formularios.
- Zod mediante contratos compartidos y resolvers.
- Tailwind CSS.
- shadcn/ui como componentes incorporados al código del proyecto.
- Vitest para pruebas.

Zustand no se incorpora inicialmente: se añadirá solo cuando exista una necesidad concreta de estado de cliente compartido que no corresponda a TanStack Query.

## Organización

Se adopta una organización ligera inspirada en Feature-Sliced Design:

- `app/`: composición global, proveedores, router y estilos.
- `pages/`: páginas vinculadas a rutas.
- `widgets/`: bloques compuestos de interfaz con responsabilidad propia.
- `features/`: acciones y casos de uso del usuario.
- `entities/`: modelos y componentes de conceptos del dominio.
- `shared/`: componentes, hooks y utilidades genéricas.

## Dependencias entre capas

La dirección general es desde las capas superiores hacia las inferiores:

`app → pages → widgets → features → entities → shared`

Las capas no deben importar desde capas superiores. Evita ciclos y no crees una capa si no aporta una separación real.

## Experiencias

- Comerciante: gestión de comercio, catálogo, campañas y pedidos.
- Comprador: consulta de comercios/campañas, creación de pedidos e historial.

La visibilidad pública, los idiomas iniciales y algunos detalles de autenticación permanecen pendientes de decisión.
