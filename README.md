# Interceptor de Horario de Atención en Spring Boot

Este proyecto es una implementación de un interceptor HTTP en Spring Boot para manejar horarios de atención de una tienda. El interceptor compara la hora local de la solicitud con el horario de atención configurado en el archivo `application.properties` y envía un JSON con un mensaje correspondiente según el estado del horario.

## Características
- **Intercepción HTTP:** Controla el acceso a rutas específicas en función del horario de atención.
- **Comparación de Hora Local:** El interceptor compara la hora local del servidor con el horario de atención configurado.
- **Configuración Flexible:** Los horarios de apertura y cierre se configuran fácilmente en el archivo `application.properties`.
- **Mensajes Personalizados:** Respuestas personalizadas en función del estado del horario (abierto/cerrado).

## Lógica de Respuesta
- Si la hora local en la que se realiza la solicitud está dentro del horario de atención configurado: El sistema responderá con un JSON indicando que la tienda está abierta y proporcionando un mensaje de bienvenida.<br>
![image](https://github.com/user-attachments/assets/dbbe8311-1672-456b-8fa6-e614c2d301d4)

- Caso contrario: El sistema responderá con un JSON indicando que la tienda está cerrada y proporcionando un mensaje sobre el horario de atención.
![image](https://github.com/user-attachments/assets/b7996539-727e-499e-811c-105e22931bdc)

## Configuración

En el archivo `application.properties`, puedes configurar facilmente el horario de atención de la tienda: <br>
Ej: Una tienda que trabaja desde las 10 de la mañana a las 5 de la tarde tendría una configuración así:

```properties
config.calendar.open=10
config.calendar.close=17
