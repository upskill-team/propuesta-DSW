# Seguridad

La seguridad de nuestra aplicación se basa en tres pilares fundamentales: autenticación robusta, protección de endpoints y validación estricta de las peticiones.

## Autenticación

Para la gestión de sesiones de usuario, implementamos un sistema de autenticación basado en **JSON Web Tokens (JWT)**. Cuando un usuario inicia sesión correctamente, el servidor genera un token firmado que contiene la información esencial del usuario y una fecha de expiración. Este token debe ser incluido en el encabezado `Authorization` de todas las peticiones posteriores a rutas protegidas.

## Protección de Endpoints

El acceso a los endpoints de nuestra API está estrictamente controlado. Implementamos un _middleware_ en el backend que intercepta cada solicitud dirigida a rutas protegidas. Este _middleware_ se encarga de:

1.  Verificar la presencia de un JWT válido.
2.  Validar la firma y la vigencia del token.
3.  Asegurar que el usuario tiene los permisos necesarios para acceder al recurso solicitado.

Las solicitudes sin un token válido o con permisos insuficientes son rechazadas con un código de estado `401 Unauthorized` o `403 Forbidden`.

## Validación de Peticiones

Toda la información que llega a nuestro backend pasa por un proceso de validación riguroso antes de ser procesada. Este proceso se divide en dos fases:

1.  **Validación de Autorización**: Se confirma que el JWT del usuario es válido y le concede acceso al endpoint, como se mencionó en el punto anterior.
2.  **Validación de Datos (Payload)**: Se analiza el cuerpo (`body`), los parámetros (`params`) y las consultas (`query`) de la petición para asegurar que los datos cumplen con el formato, tipo y estructura esperados. Esto previene datos corruptos y ataques como la inyección de código.