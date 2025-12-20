## 📊 Resumen de Actividad
El equipo ha mantenido un flujo de trabajo constante siguiendo la metodología Gitflow.

- **Total de PRs mergeados:** +135
- **Commits totales:** +205

## 🏆 Hitos Técnicos Principales (Highlights)

A continuación, los cambios más significativos del desarrollo:

### 🚀 Nuevas Funcionalidades (Features)
- Implementar Interfaz del Panel de Administración ([PR #52](https://github.com/upskill-team/Front-End-DSW/pull/52))
- **Panel de Administración:** Implementación de la interfaz principal para la gestión de la plataforma ([PR #52](https://github.com/upskill-team/Front-End-DSW/pull/52))
- **Dashboard de Profesores:** Espacio de trabajo dedicado para que los docentes gestionen sus cursos y métricas ([PR #58](https://github.com/upskill-team/Front-End-DSW/pull/58))
- **Gestión de Contenidos (ABM):** Sistema para administrar los "Tipos de Curso" y categorías desde el panel administrativo ([PR #60](https://github.com/upskill-team/Front-End-DSW/pull/60))
- **Visor de Documentos Integrado:** Herramienta interna para visualizar y validar las solicitudes/credenciales de los profesores sin salir de la app ([PR #54](https://github.com/upskill-team/Front-End-DSW/pull/54))
- **Adaptabilidad (Responsive Design):** Implementación de diseño responsivo en las vistas principales para garantizar la accesibilidad móvil ([PR #44](https://github.com/upskill-team/Front-End-DSW/pull/44))
- **Sistema de Pagos y Checkout:** Implementación del flujo completo de compra, integración con pasarela de pago y experiencia de usuario post-compra ([PR #134](https://github.com/upskill-team/Front-End-DSW/pull/134))
- **Módulo de Evaluaciones:** Desarrollo del sistema integral de exámenes, incluyendo la interfaz de resolución para estudiantes y las herramientas de creación/calificación para profesores ([PR #135](https://github.com/upskill-team/Front-End-DSW/pull/135))
- **Gestión de Cursos (LMS):** Creación de los flujos para la creación, edición y gestión de contenido educativo, así como la vista de detalle del curso ([PR #101](https://github.com/upskill-team/Front-End-DSW/pull/101))
- **Gestión Institucional:** Implementación de interfaces para la administración de instituciones y el manejo de solicitudes de vinculación ([PR #129](https://github.com/upskill-team/Front-End-DSW/pull/129))
- **Perfil de Usuario:** Vista completa para la visualización y edición de datos personales y configuración de cuenta ([PR #121](https://github.com/upskill-team/Front-End-DSW/pull/121))
- **Seguridad y Recuperación:** Implementación del flujo seguro para el restablecimiento de contraseñas y protección de rutas ([PR #70](https://github.com/upskill-team/Front-End-DSW/pull/70))
- **Gestión Avanzada de Sesiones:** Implementación de seguridad robusta mediante *Refresh Tokens* y funcionalidad de persistencia de sesión ("Recordarme") ([PR #156](https://github.com/upskill-team/Front-End-DSW/pull/156), [PR #174](https://github.com/upskill-team/Front-End-DSW/pull/174))
- **Sistema de Comunicación:** Infraestructura completa para el envío de correos transaccionales y centro de notificaciones en la plataforma ([PR #152](https://github.com/upskill-team/Front-End-DSW/pull/152), [PR #150](https://github.com/upskill-team/Front-End-DSW/pull/150))
- **Aseguramiento de Calidad (QA):** Integración de suite de pruebas automatizadas, incluyendo tests unitarios con **Vitest** y pruebas de extremo a extremo (E2E) con **Cypress** ([PR #148](https://github.com/upskill-team/Front-End-DSW/pull/148))
- **Gestión de Datos y Apelaciones:** Implementación de filtrado y paginación avanzada para listados, y visualización del historial de apelaciones en el perfil ([PR #142](https://github.com/upskill-team/Front-End-DSW/pull/142), [PR #147](https://github.com/upskill-team/Front-End-DSW/pull/147))
- **Feedback de Usuario (UX):** Sistema de notificaciones visuales (*Toasts*) para mejorar la retroalimentación de acciones en la interfaz ([PR #149](https://github.com/upskill-team/Front-End-DSW/pull/149))

### 🐛 Corrección de Errores (Bug Fixes)
- **UI/UX y Navegación:** Solución a problemas de redirección en solicitudes de profesor y desbordamiento de texto en modales ([PR #151](https://github.com/upskill-team/Front-End-DSW/pull/151))
- **Layout y Responsividad:** Corrección de superposición del formulario de autenticación sobre el header en pantallas pequeñas ([PR #42](https://github.com/upskill-team/Front-End-DSW/pull/42))
- **Manejo de Errores:** Corrección en el manejo de excepciones y referencias a instituciones en los cursos ([PR #157](https://github.com/upskill-team/Front-End-DSW/pull/157))
- **Panel de Administración:** Corrección de problemas de responsividad y consistencia visual en layouts administrativos ([PR #69](https://github.com/upskill-team/Front-End-DSW/pull/69))
- **Componentes:** Solución a bugs lógicos y de vinculación en las tarjetas de cursos ([PR #136](https://github.com/upskill-team/Front-End-DSW/pull/136))
- **Lógica de Evaluaciones y Persistencia:** Solución a bucles infinitos en el flujo de evaluaciones y mejoras en el guardado de datos del editor ([PR #180](https://github.com/upskill-team/Front-End-DSW/pull/180))
- **Infraestructura y Routing:** Configuración de reglas de reescritura (rewrites) para garantizar el correcto enrutamiento de la SPA en producción ([PR #168](https://github.com/upskill-team/Front-End-DSW/pull/168))
- **Lógica de Negocio (Intentos):** Corrección en el sistema de registro y validación de intentos en las unidades de aprendizaje ([PR #185](https://github.com/upskill-team/Front-End-DSW/pull/185))
- **Componentes y Gráficos:** Arreglos en el visor de documentos y en la renderización de gráficos del panel administrativo ([PR #199](https://github.com/upskill-team/Front-End-DSW/pull/199))
- **CI/CD y Despliegue:** Resolución de conflictos críticos en el proceso de construcción (build) para el despliegue ([PR #161](https://github.com/upskill-team/Front-End-DSW/pull/161))

### 🛠 Mantenimiento y Otros (Chores/Refactors)

- **Gestión de Estado y Formularios:** Migración completa de la gestión del estado del servidor a **TanStack Query** y de los formularios a **React Hook Form + Valibot** para mejorar rendimiento y validación ([PR #74](https://github.com/upskill-team/Front-End-DSW/pull/74), [PR #75](https://github.com/upskill-team/Front-End-DSW/pull/75))
- **Seguridad:** Fortalecimiento de la seguridad en enlaces externos y en el visor de documentos ([PR #196](https://github.com/upskill-team/Front-End-DSW/pull/196))
- **Rendimiento (Lazy Loading):** Implementación de carga diferida (Lazy Loading) en el enrutador principal y secciones críticas para mejorar el tiempo de carga inicial ([PR #155](https://github.com/upskill-team/Front-End-DSW/pull/155))
- **Arquitectura de Componentes:** Estandarización y mejora del sistema de componentes UI (Input, Button, Card, Select, Textarea) utilizando utilidades de composición de clases (`cn`) ([PR #92](https://github.com/upskill-team/Front-End-DSW/pull/92), [PR #112](https://github.com/upskill-team/Front-End-DSW/pull/112))
- **Autenticación (Token-Only):** Unificación y estabilización del sistema de autenticación adoptando un flujo basado exclusivamente en tokens ([PR #29](https://github.com/upskill-team/Front-End-DSW/pull/29))
- **Estructura del Proyecto:** Estandarización de la arquitectura de carpetas y organización del código UI para facilitar la escalabilidad ([PR #91](https://github.com/upskill-team/Front-End-DSW/pull/91))


