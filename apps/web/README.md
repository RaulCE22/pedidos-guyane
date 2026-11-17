# Aplicación web

SPA única construida con React, Vite y TypeScript. Las vistas y rutas ofrecerán las experiencias de comerciante y comprador dentro de la misma aplicación.

La organización prevista sigue una separación ligera inspirada en Feature-Sliced Design:

- `app/`: composición global, proveedores, router y estilos globales.
- `pages/`: páginas asociadas a rutas.
- `widgets/`: bloques de interfaz compuestos que aportan valor independiente.
- `features/`: acciones y casos de uso del usuario.
- `entities/`: conceptos de dominio representados en la interfaz.
- `shared/`: componentes y utilidades genéricas.

Mantén la dirección de dependencias entre capas. No crees carpetas o capas adicionales sin una responsabilidad concreta. shadcn/ui se utilizará como fuente de componentes incorporados al código, no como una dependencia monolítica.
