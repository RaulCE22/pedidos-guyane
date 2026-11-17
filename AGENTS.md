# Instrucciones para agentes

## Primeros pasos

1. Lee este archivo.
2. Consulta `docs/README.md` y únicamente los documentos relevantes para la tarea.
3. Identifica el requisito `REQ`, sus criterios de aceptación y el plan asociado.
4. Inspecciona el código y los cambios existentes antes de editar.
5. Respeta las decisiones aceptadas en `docs/decisions/` y registra las nuevas decisiones duraderas mediante ADR.

## Principios del proyecto

- La documentación de producto e ingeniería y la comunicación con el usuario se mantienen en español.
- Los identificadores, nombres de paquetes, archivos técnicos y código se escriben en inglés.
- Mantén un monolito modular; no introduzcas microservicios.
- El frontend es una SPA React única con experiencias para comerciante y comprador.
- El backend es una API Hono única, organizada por módulos de dominio.
- Mantén la lógica de negocio fuera de componentes React y manejadores HTTP.
- Usa Zod en los límites de confianza y comparte contratos solo cuando frontend y backend realmente los necesiten.
- Usa TanStack Query para estado remoto. No añadas Zustand hasta que exista una necesidad real de estado de cliente compartido.
- Prefiere modificar una estructura existente antes que crear capas, carpetas o abstracciones nuevas.
- No añadas dependencias sin justificar su necesidad.
- No implementes comportamientos que estén marcados como cuestiones abiertas.

## Límites funcionales

- Un comerciante gestiona un único comercio.
- Un comercio solo puede tener una campaña activa a la vez.
- Un pedido pertenece a una sola campaña y a un solo comercio.
- No existe carrito multidistribuidor.
- Los pedidos conservan snapshots del nombre y precio de los productos al confirmarse.
- El piloto inicial es gratuito.

Quedan fuera del alcance actual las integraciones con WhatsApp, la IA dentro del producto, los pagos, las suscripciones, el inventario avanzado, el chat y las notificaciones complejas.

## Flujo de trabajo

- Antes de cambios no triviales, identifica requisitos, decisiones, módulos afectados y pruebas necesarias.
- Solicita aprobación cuando sea necesario decidir un comportamiento de producto todavía abierto o cambiar una decisión aceptada.
- Implementa solo el alcance aprobado.
- Añade pruebas junto al comportamiento que se implemente.
- Revisa el diff y comunica los comandos realmente ejecutados y sus resultados.
- No declares una verificación como superada si no se ha ejecutado.

## Fuente de verdad

Los requisitos, roadmap, planes, progreso y decisiones viven en `docs/`. El estado de implementación debe mantenerse en el plan correspondiente, no únicamente en el historial de conversación.
