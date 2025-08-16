# Formato de la Respuesta de la API

Todas las respuestas de la API, sin importar el endpoint o el método HTTP, seguirán un formato JSON consistente para facilitar su integración y manejo de errores por parte del cliente.

La estructura se divide en dos tipos principales: respuestas exitosas y respuestas de error.

## Respuesta Exitosa (Código de Estado 2xx)

Cuando una solicitud se procesa correctamente (por ejemplo, con códigos de estado `200 OK`, `201 Created`), la respuesta siempre contendrá un objeto JSON con dos claves principales: `message` y `data`.

```json
{
  "message": "Descripción de la operación realizada.",
  "data": { ... } //  o null
}
```

- message (string): Un mensaje legible por humanos que confirma que la operación fue exitosa.
- data (object | array | null): El contenido o payload solicitado.

Será un objeto si se solicita un único recurso. Será un array de objetos si se solicita una lista de recursos.
Puede ser null o un objeto vacío {} en operaciones que no devuelven contenido, como algunas peticiones DELETE o PATCH.

## Respuesta de Error (Códigos de Estado 4xx y 5xx)

Cuando una solicitud falla por cualquier motivo (datos inválidos, recurso no encontrado, falta de permisos, error del servidor, etc.), la respuesta contendrá un único objeto JSON con la clave `message`. La clave data no estará presente.

```json
{
  "message": "Descripción específica del error."
}
```

- message (string): Un mensaje claro y conciso que explica por qué falló la solicitud. Esto ayuda al desarrollador del cliente a depurar el problema.
