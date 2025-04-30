---
id: intro
title: Introducción al Proyecto Whirlpool
sidebar_position: 1
---

# 🌀 Proyecto Whirlpool – Descripción General

Este proyecto fue desarrollado para Whirlpool y tiene como objetivo mejorar la capacitación de técnicos a través de una plataforma de cursos conectada a un juego.

## 🔹 ¿Cómo funciona?

- Se creó una **página de administrador** donde se pueden **subir cursos** usando un panel sencillo.
- Estos cursos incluyen:
  - Secciones de contenido informativo.
  - Preguntas de verdadero/falso.
  - Preguntas de opción múltiple.
- Una vez cargados, los cursos quedan disponibles a través de una **API**.

- Por otro lado, existe un **juego interactivo** donde los técnicos:
  - Inician sesión.
  - Ven los cursos que les corresponden.
  - Avanzan completando el contenido que se subió desde la página de administración.

## 🔹 Tecnologías principales

- **Frontend administrador:** Bootstrap
- **Backend:** Django (API para cursos)
- **Juego:** Unity (consume la API)
- **Documentación:** Docusaurus

## 🔹 Flujo general

1. El administrador sube y edita cursos desde la plataforma.
2. El backend (Django) guarda los datos y los expone mediante una API.
3. El juego consulta la API y muestra los cursos a los técnicos.

---

