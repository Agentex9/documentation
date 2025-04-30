# Database Documentation

## 📄 Overview
Este documento describe la estructura de la base de datos utilizada tanto para el panel de administración como para el juego **TecniGame**. La base de datos ha sido diseñada para garantizar un manejo eficiente de usuarios, progreso dentro del juego, niveles y otros componentes relacionados.

## 🗺️ Diagrama Físico
A continuación se presenta el diagrama físico de la base de datos:

![Diagrama de la base de datos](/img/Diagrama.png)

## 🧰 Tecnologías Utilizadas
- **MySQL**: Sistema de gestión de bases de datos relacional.
- **Django ORM**: Herramienta de mapeo objeto-relacional integrada en el framework Django, utilizada para definir y manipular modelos de datos desde Python.

## ⚙️ Implementación
La base de datos se implementa mediante modelos definidos en el ORM de Django, lo que permite generar y gestionar las tablas de manera automática a través de migraciones. Este enfoque facilita la mantenibilidad, escalabilidad y coherencia del esquema de datos con la lógica de negocio del sistema.

---