# BITÁCORA DE CAMBIOS

## TABLA DE CONTENIDO

1. [Introducción](#introducción)  
2. [Entregables](#entregables)  
3. [Características a ser probadas](#características-a-ser-probadas)  
4. [Características a no ser probadas](#características-a-no-ser-probadas)  
5. [Necesidades ambientales](#necesidades-ambientales)  
6. [Capacitaciones](#capacitaciones)  
7. [Riesgos](#riesgos)

---

## PLAN DE PRUEBAS Whirlpool Training

*Eslogan y/o lema de la empresa.*

Monterrey, Nuevo León, octubre 2024

---

### BITÁCORA DE CAMBIOS

| Fecha     | Modificado por     | Versión | Descripción                        |
|----------|--------------------|---------|------------------------------------|
| 13/03/25 | Pitufos limited Co | 1.1     | Se llenó la información del documento |

---

## INTRODUCCIÓN

### ESTRATEGIA DE PRUEBAS

Hacer uso de pruebas Unitarias y Funcionales para la página web, al igual que pruebas de integración en sprints posteriores para asegurar la comunicación entre los diversos módulos.

### ALCANCE

Este plan de pruebas tiene como objetivo evaluar la funcionalidad, estabilidad y seguridad del sistema en desarrollo, garantizando que cumple con los requerimientos establecidos.

---

## ENTREGABLES

### DOCUMENTACIÓN PARA ENTREGAR

| DOCUMENTO | PERSONA QUIEN ENTREGA | PERSONA QUIEN RECIBE |
|-----------|------------------------|------------------------|
|           |                        |                        |

---

## CARACTERÍSTICAS A SER PROBADAS

| SPRINT # | CARACTERISTICA                       | DESCRIPCIÓN                                                                                                                                              | MÓDULO             |
|----------|--------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------|
| 1        | Log In                               | Verificar que el usuario pueda iniciar sesión con credenciales correctas y que, en caso de error, se muestre un mensaje adecuado.                         | Front end/Back end |
| 1        | Sign Out                             | Asegurar el correcto funcionamiento del botón de 'Sign Out' y la correcta ejecución de las acciones al presionarlo.                                       | Front end/Back end |
| 1        | Manejo de Preguntas y Respuestas en BD | Verificar que la solución tenga acceso completo a los datos almacenados para preguntas y respuestas. CRUD funcional.                                      | Back-end           |
| 1        | Responsividad web                    | El sistema debe adaptarse a distintas resoluciones en pantallas, tanto escritorio como móvil.                                                             | Front-end          |

---

## CARACTERÍSTICAS A NO SER PROBADAS

| SPRINT # | CARACTERISTICA               | DESCRIPCIÓN                                                                                                            | JUSTIFICACIÓN | RIESGO |
|----------|------------------------------|------------------------------------------------------------------------------------------------------------------------|---------------|--------|
| 1        | Funcionamiento del videojuego | Verificar correcto funcionamiento del videojuego y generación de niveles en base a BD                                 | Se probará en sprint posterior | Alto |
| 1        | Comunicación de la base       | Verificar comunicación entre BD y videojuego                                                                          | Se probará en sprint posterior | Alto |
| 1        | Notificaciones de cursos      | Alertas y notificaciones sobre cursos, entregas, etc.                                                                 | No es prioridad inicial         | Bajo |
| 1        | Modificación de cursos        | Modificar un curso creado                                                                                             | Depende de la creación del curso | Medio |

---

## NECESIDADES AMBIENTALES

### HARDWARE

| SPRINT # | DISPOSITIVO                 | MARCA   | CARACTERISTICAS                                                      | ¿TENEMOS EL EQUIPO? |
|----------|-----------------------------|---------|----------------------------------------------------------------------|----------------------|
| 1        | Computadora de escritorio o Laptop | -       | SO Windows o MacOS, acceso a red Wi-Fi estable                        | Sí                   |
| 1        | Teléfono Móvil              | iPhone  | Teléfono con acceso a internet                                        | Sí                   |

---

## CAPACITACIONES

| INSTRUCTOR       | PERSONA A CAPACITAR | CAPACITACIÓN                                      | FECHA INICIO | FECHA FIN | DURACIÓN HRS     | COSTO |
|------------------|---------------------|---------------------------------------------------|--------------|-----------|------------------|-------|
| Homero Garza      | Administrador        | Breve capacitación sobre funcionamiento de la web | -            | -         | 30 min - 1 hora  | 0     |
| Javier Luis Castillo | Administrador     | Manejo del Dashboard y herramientas de análisis   | -            | -         | 20 - 30 min      | 0     |
| Diego Lumbreras   | Administrador        | Qué hacer al encontrar errores y cómo reportarlos | -            | -         | 5 - 10 min       | 0     |

---

## RIESGOS

| ID  | RIESGO                                     | PROBABILIDAD | IMPACTO | ACCIONES PREVENTIVAS / CORRECTIVAS                                                                                              |
|-----|--------------------------------------------|--------------|---------|-----------------------------------------------------------------------------------------------------------------------------------|
| R1  | Fallo en el manejo de la función 'Sign Out' | Media        | Alto    | Preventiva: Pruebas exhaustivas. Correctiva: Parche o actualización.                                                             |
| R2  | Fallo en la autenticación de usuario        | Media        | Alta    | Preventiva: Pruebas con múltiples credenciales. Correctiva: Método de recuperación de credenciales.                              |
| R3  | Fallo en recopilación de datos              | Baja         | Alto    | Preventiva: Progreso local tipo caché. Correctiva: Manejo correcto de POST y PATCH en JSON.                                      |
| R4  | Fallo en la responsividad web               | Media        | Medio   | Preventiva: Revisar vista móvil durante desarrollo. Correctiva: Ajustes con Bootstrap o Tailwind para escritorio y móvil.         |