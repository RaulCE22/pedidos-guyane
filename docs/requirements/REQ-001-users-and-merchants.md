# REQ-001: Usuarios y comercios

- Estado: Borrador
- Prioridad: Alta
- ADR relacionados: ADR-0001
- Cuestiones abiertas relacionadas: OQ-03

## Propósito

Permitir que comerciantes y compradores utilicen la aplicación con una identidad propia y que cada comerciante gestione un único comercio.

## Alcance

### Incluye

- Dos tipos de usuario: comerciante y comprador.
- Registro e inicio de sesión.
- Perfil básico.
- Asociación de un usuario comerciante con un único comercio.
- Acceso del comerciante a la gestión de su comercio.

### No incluye

- Empleados o subusuarios de un comercio.
- Roles administrativos avanzados.
- Multi-tenancy configurable por organizaciones.
- Membresías o planes de suscripción.

## Actores y permisos

- Comerciante: administra su propio comercio.
- Comprador: utiliza la aplicación para consultar campañas y realizar pedidos.
- Cada comerciante tiene un único comercio.

## Requisitos funcionales

### RF-01 — Identidad de usuario

La aplicación debe permitir identificar a sus usuarios y distinguir los perfiles de comerciante y comprador.

### RF-02 — Perfil del comerciante

Un usuario con perfil de comerciante puede consultar y gestionar la información básica de su único comercio.

### RF-03 — Aislamiento entre comercios

Un comerciante no puede gestionar ni consultar los datos privados de otro comercio.

### RF-04 — Perfil del comprador

Un comprador dispone de una identidad asociada a sus pedidos y a su historial.

## Reglas de negocio

- Un comerciante está asociado a un único comercio.
- El sistema contempla únicamente los roles de comerciante y comprador en el alcance inicial.
- No se incorporan empleados ni permisos configurables.
- Las condiciones exactas de acceso público y registro previo a la compra permanecen pendientes de OQ-03.

## Criterios de aceptación

### REQ-001-AC-01 — Distinguir los perfiles

Dado un usuario autenticado, cuando utiliza la aplicación, entonces el sistema reconoce si su perfil corresponde a un comerciante o a un comprador.

### REQ-001-AC-02 — Un comercio por comerciante

Dado un usuario con perfil de comerciante, cuando consulta su comercio, entonces existe una única asociación entre ese usuario y su comercio.

### REQ-001-AC-03 — Separación de comercios

Dado un comerciante, cuando intenta consultar o modificar información privada de otro comercio, entonces la operación no está autorizada.

### REQ-001-AC-04 — Historial asociado al comprador

Dado un comprador, cuando consulta sus datos, entonces sus pedidos pueden identificarse como pertenecientes a ese usuario.

## Impacto en datos y API

Entidades principales: `users` y `merchants`. La relación conceptual se describe en [modelo de datos](../architecture/data-model.md).

La estrategia concreta de registro y el acceso de compradores sin cuenta dependen de OQ-03 y no se consideran cerrados por este requisito.

## Requisitos no funcionales

- Las credenciales y sesiones deben gestionarse mediante una solución de autenticación mantenida.
- Las operaciones privadas deben verificar el usuario y el recurso al que accede.

## Dependencias y preguntas abiertas

- OQ-03: consulta pública y necesidad de cuenta para confirmar pedidos.
- OQ-06: nombre comercial del producto, sin impacto en el modelo de identidad.
