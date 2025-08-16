> **[Portal de Documentación](../README.md)** / 🎯 Propuesta del Proyecto

# Propuesta TP DSW

## Grupo

### Integrantes

- 52154 - Gugliermino Zuñiga, Carlos Ricardo
- 52451 - Pedemonte, Nicolás
- 52325 - Trincavelli, Luca
- 53110 - Zariaga, Franco

### Repositorios

- [frontend app](https://github.com/carlex74/Front-End-DSW)
- [backend app](https://github.com/carlex74/Back-End-DSW)

## Tema

### Descripción

Desarrollaremos una plataforma de aprendizaje virtual. La solución consistirá en una página web con acceso a cursos donde los estudiantes podrán acceder, examinar recursos y realizar actividades. Estos cursos podrán ser gratuitos o pagos, depende como lo prefiera el instructor.

### Modelo

![Proposal MD](https://github.com/user-attachments/assets/90899d01-8de4-4a2d-a44d-42ed2b67a1f7)

[link del modelo](https://drive.google.com/file/d/1le9JNA73D_ulgn7CgIJh6w_V4lcplNSn/view?usp=sharing)

## Alcance Funcional

### Alcance Mínimo

Regularidad:

| Req                     | Detalle                                                                                                                                                                                                                  |
| :---------------------- | :----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| CRUD simple             | 1. CRUD Alumnos<br>2. CRUD Instructores<br>3. CRUD Tipos de Cursos<br>4. CRUD Instituciones                                                                                                                              |
| CRUD dependiente        | 1. CRUD Cursos {depende de} CRUD Tipos de Cursos e Instructores<br>2. CRUD Solicitud {depende de} CRUD Instructor                                                                                                        |
| Listado<br>+<br>detalle | 1. Listado de cursos filtrado por nombre, institución, instructor y tipo de curso => detalle Información de los contenidos<br>2. Listado de solicitudes filtrado por fecha de solicitud => detalle Texto de la Solicitud |
| CUU/Epic                | 1. Crear un curso nuevo para ser publicado en la plataforma<br>2. Completar curso                                                                                                                                        |

Adicionales para Aprobación

| Req      | Detalle                                                                                                                                                                                                            |
| :------- | :----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| CRUD     | 1. CRUD Alumnos<br>2. CRUD Instructores<br>3. CRUD Tipos de Cursos<br>4. CRUD Instituciones<br>5. CRUD Cursos<br>6. CRUD Actividades<br>7. CRUD Material<br>8. CRUD Solicitudes<br>9. CRUD Unidad<br>10. CRUD Pago |
| CUU/Epic | 1. Matricularse a un nuevo curso<br>2. Publicar actividad en el curso para los alumnos<br>3. Completar actividad del curso<br>4. Dar de baja una unidad<br>5. Pagar curso                                          |

### Alcance Adicional Voluntario

| Req      | Detalle                                                                                                            |
| :------- | :----------------------------------------------------------------------------------------------------------------- |
| Listados | 1. Listado de instituciones<br>2. Listado de resoluciones de actividad                                             |
| CUU/Epic | 1. Dar de baja un curso<br>2. Publicar Material<br>3. Dar de baja un tipo de curso<br>4. Dar de baja un instructor |
| Otros    | 1. Envío de recordatorio de vencimiento de tareas por mail                                                         |
