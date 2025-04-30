# Product Backlog
Requerimientos Funcionales, No Funcionales y de Proyecto

| #    | Descripción                                                                                                                                                                          | Prioridad |
| :--- | :----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :-------- |
| RF-1 | Acceso a vista de estudiante desde el dashboard: lograr que el supervisor tenga acceso a la vista de estudiante del juego.                                                            | MEDIA     |
| RF-2 | Sistema de notificaciones: manejo de alertas por correo electrónico cuando se agreguen nuevos cursos y de contenidos pendientes. Alertas para evaluaciones pendientes.                    | MEDIA     |
| RF-3 | Manejo de evaluaciones temporales: lograr la asignación de cursos y evaluaciones que con limites de tiempo para completar.                                                              | MEDIA     |
| RNF-1| Mejoras de seguridad: implementación de autenticación de dos factores. Registro detallado de actividades (audit log)                                                                 | BAJA      |
| RNF-2| Escalabilidad: mejoras en la contenerización para un mejor despliegue.                                                                                                                   | ALTA      |
| RNF-3| Optimización para múltiples dispositivos: manejo de distintas resoluciones y medidas para los distintos dispositivos utilizados en el videojuego (bloquear rotación).                    | MEDIA     |

Información de Accesos

| Rol          | Descripción                                                                               | Permisos                                                                                                                                                                                                                                                                                                                           |
| :----------- | :-------------------------------------------------------------------------------------- | :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Administrador| Persona que utiliza la aplicación para fines de asignación, creación y manipulación de cursos, técnicos y regiones. | Iniciar Sesión (Dashboard web), CRUD de técnicos, CRUD de regiones, CRUD de cursos, CRUD de instructores, Acceso y visualización de metricas de desempeño, Acceso a dashboard web                                                                                                                    |
| Técnicos     | Persona que hace uso de la aplicación para fines de entrenamiento                         | Iniciar Sesión (Videojuego), Acceso a cursos                                                                                                                                                                                                                                                                                     |

---