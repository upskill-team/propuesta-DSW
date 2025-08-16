# EndPoints

Nuestra API utiliza los principales métodos HTTP para interactuar con los recursos: GET, POST, PATCH y DELETE.
Las rutas están organizadas por entidades (por ejemplo, Course, User), y cada una implementa los métodos que corresponden a las operaciones permitidas sobre dicha entidad.

## Convenciones generales

Todas las rutas siguen el formato:`/api/nombre-entidad`

- Los métodos HTTP se usan según su propósito semántico:

  - GET → Obtener datos del servidor.

  - POST → Enviar nuevos datos al servidor.

  - PATCH → Actualizar parcialmente un recurso existente.

  - DELETE → Eliminar un recurso existente.

## Rutas que envían datos al cliente (GET)

Se utilizan para recuperar información.

`GET /api/courses`

Retorna el listado de cursos disponibles.

## Rutas que reciben datos del cliente (POST)

Se usan para crear nuevos registros.

`POST /api/courses`

Crea un nuevo curso con los datos enviados en el cuerpo de la solicitud.

## Rutas que modifican entidades (PATCH)

Permiten actualizar parcialmente un recurso.

`PATCH /api/courses/{id}`

Actualiza los campos enviados para el curso con el ID especificado.

## Rutas que eliminan registros (DELETE)

`DELETE /api/courses/{id}`

Elimina el curso con el ID especificado.

## Rutas para Querys o busquedas

Coming soon....
