# 🚀 Documentación de la API de UpSkill

Bienvenido a la documentación técnica de la API de UpSkill. Esta guía está diseñada para desarrolladores que necesiten interactuar con nuestro backend, ya sea para consumir datos desde el frontend o para integraciones de terceros.

---

### 🏛️ Principios Clave

Nuestra API se adhiere a los siguientes estándares y principios de diseño para garantizar la consistencia, previsibilidad y seguridad:

- **Arquitectura RESTful:** Utilizamos los métodos HTTP estándar (`GET`, `POST`, `PATCH`, `DELETE`) para interactuar con los recursos de una manera predecible.
- **Formato JSON:** Todas las respuestas de la API, tanto para solicitudes exitosas como para errores, se devuelven en formato `application/json`.
- **Autenticación con JWT:** Las rutas protegidas requieren un JSON Web Token (JWT) válido en el encabezado `Authorization` para verificar la identidad y los permisos del usuario.

---

### 📦 Recursos Principales

La API proporciona operaciones CRUD (Crear, Leer, Actualizar, Eliminar) para gestionar las siguientes entidades de negocio:

- 📚 Cursos
- 👤 Usuarios (Alumnos e Instructores)
- 🎓 Tipos de Cursos
- 🏫 Instituciones
- ... y más.

---

### 🗺️ Navegación de la Documentación

Utiliza la siguiente tabla para navegar a las secciones específicas de la documentación de la API.

| Documento                                         | Descripción                                                                                        |
| :------------------------------------------------ | :------------------------------------------------------------------------------------------------- |
| **[Endpoints](./endPoints.md)**                   | Detalle de todos los endpoints disponibles, incluyendo métodos HTTP, parámetros y ejemplos de uso. |
| **[Formato de Respuesta](./formatoRespuesta.md)** | Explica la estructura estándar de las respuestas JSON para operaciones exitosas y de error.        |
| **[Seguridad y Autenticación](./seguridad.md)**   | Detalles sobre la implementación de la autenticación con JWT y la protección de rutas.             |
| **[Requisitos](./requisitos.md)**                 | Requisitos funcionales y técnicos que la API debe cumplir según las especificaciones del proyecto. |
