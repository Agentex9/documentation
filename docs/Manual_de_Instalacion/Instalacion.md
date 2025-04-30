# Manual de Instalación - Whirlpool Courses

## Índice
1. [Introducción](#introducción)
2. [Requisitos previos](#requisitos-previos)
3. [Instalación con Docker](#instalación-con-docker)
4. [Configuración inicial](#configuración-inicial)
5. [Acceso al sistema](#acceso-al-sistema)
6. [Solución de problemas comunes](#solución-de-problemas-comunes)
7. [Mantenimiento básico](#mantenimiento-básico)
8. [Recursos adicionales](#recursos-adicionales)

## Introducción

Whirlpool Courses es una plataforma de e-learning diseñada para gestionar y entregar cursos de capacitación a los técnicos de Whirlpool. Esta aplicación permite la administración de cursos, instructores, regiones y técnicos, así como el seguimiento de su progreso.

Este manual está dirigido a los técnicos de sistemas de Whirlpool encargados de la instalación y mantenimiento de la plataforma.

## Requisitos previos

Antes de comenzar la instalación, asegúrese de tener instalado lo siguiente:

- *Docker* (versión 20.10 o superior)
- *Docker Compose* (versión 2.0 o superior)
- Acceso a Internet para descargar las imágenes de Docker
- Un mínimo de 2GB de RAM y 10GB de espacio en disco para la aplicación

Para verificar la instalación de Docker y Docker Compose, ejecute los siguientes comandos:

bash
docker --version
docker-compose --version


## Instalación con Docker

### Paso 1: Clonar el repositorio

Primero, clone el repositorio del proyecto en su servidor:

bash
git clone https://github.com/whirlpool/whirlpool-courses.git
cd whirlpool-courses


### Paso 2: Configurar el archivo .env

Cree un archivo .env en la raíz del proyecto con las siguientes variables:


DEBUG=1
SECRET_KEY=your-secret-key
ALLOWED_HOSTS=localhost,127.0.0.1

# Database
DATABASE_URL=postgres://postgres:postgres@db:5432/whirlpool


> ⚠️ *Importante*: Para entornos de producción, cambie DEBUG=0, genere una clave secreta única y segura, y no use las contraseñas predeterminadas.

### Paso 3: Construir y levantar los contenedores

Utilice Docker Compose para construir y levantar los contenedores:

bash
docker-compose up --build


La primera vez que ejecute este comando, Docker descargará todas las imágenes necesarias y construirá los contenedores, lo que puede tomar varios minutos.

Para ejecutar los contenedores en segundo plano, utilice la opción -d:

bash
docker-compose up -d


### Paso 4: Verificar la instalación

Una vez que los contenedores estén en funcionamiento, verifique que la aplicación esté disponible accediendo a:


http://localhost:3000


Si todo está correcto, debería ver la página de inicio de sesión de Whirlpool Courses.

## Configuración inicial

### Crear un superusuario (administrador)

Para crear un usuario administrador, ejecute el siguiente comando:

bash
docker-compose exec web python manage.py createsuperuser


Siga las instrucciones para crear un nombre de usuario, dirección de correo electrónico y contraseña.

### Crear regiones iniciales

Las regiones son necesarias para asignar cursos y técnicos. Después de iniciar sesión en el sistema (http://localhost:3000/), navegue a la sección de Regiones desde el menú principal y cree las regiones necesarias (Norte, Sur, Este, Oeste, etc.).

### Crear instructores

Después de crear las regiones, puede crear instructores que serán responsables de los cursos:

1. Vaya a la sección de Instructores desde el menú principal
2. Complete el formulario con el nombre del instructor y seleccione la región a la que pertenece
3. Haga clic en "Guardar"

## Acceso al sistema

### Acceso a la plataforma

Para acceder a la plataforma, utilice la URL:


http://localhost:3000/


Inicie sesión con el nombre de usuario y contraseña del superusuario creado anteriormente.

> ⚠️ *Nota importante*: Esta plataforma está diseñada exclusivamente para administradores del sistema de capacitación. Los técnicos no acceden directamente a esta plataforma, sino que son gestionados a través de ella.

## Solución de problemas comunes

### Error de conexión a la base de datos

Si encuentra errores de conexión a la base de datos, verifique que:

1. El contenedor de PostgreSQL esté en ejecución:
   bash
   docker-compose ps
   

2. Las credenciales de la base de datos en el archivo .env sean correctas.

3. La base de datos haya sido inicializada correctamente. Si es necesario, reinicie el contenedor:
   bash
   docker-compose restart db
   

### Error "No se puede acceder al sitio"

Si no puede acceder a la aplicación en http://localhost:3000:

1. Verifique que los contenedores estén en ejecución:
   bash
   docker-compose ps
   

2. Revise los logs para identificar posibles errores:
   bash
   docker-compose logs web
   

3. Asegúrese de que el puerto 3000 no esté siendo utilizado por otra aplicación en su servidor.

### Problemas con las migraciones

Si encuentra errores relacionados con las migraciones de la base de datos:

bash
docker-compose exec web python manage.py migrate


### Archivos estáticos no se cargan correctamente

Si los estilos o imágenes no se cargan correctamente:

bash
docker-compose exec web python manage.py collectstatic --noinput


## Mantenimiento básico

### Respaldo de la base de datos

Para crear un respaldo de la base de datos:

bash
docker-compose exec db pg_dump -U postgres whirlpool > backup_$(date +%Y%m%d).sql


### Detener los contenedores

Para detener los contenedores sin eliminarlos:

bash
docker-compose stop


### Reiniciar los contenedores

Para reiniciar los contenedores:

bash
docker-compose restart


### Actualizar la aplicación

Para actualizar la aplicación a una nueva versión:

1. Detenga los contenedores:
   bash
   docker-compose down
   

2. Obtenga la última versión del código:
   bash
   git pull origin main
   

3. Reconstruya y levante los contenedores:
   bash
   docker-compose up --build -d
   

4. Aplique las migraciones si es necesario:
   bash
   docker-compose exec web python manage.py migrate
   

## Recursos adicionales

### Documentación de la API

La documentación de la API está disponible en:


http://localhost:3000/api/swagger/


### Estructura del proyecto

El proyecto está organizado en las siguientes aplicaciones principales:

- *courses*: Gestión de cursos, secciones, preguntas y respuestas
- *users*: Gestión de técnicos y autenticación
- *api*: Endpoints de la API para integración con otros sistemas

---
