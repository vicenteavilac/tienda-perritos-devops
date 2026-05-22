# 🐾 Tienda de Perritos - Arquitectura Multicapa & Pipeline CI/CD Automatizado

Este repositorio contiene la solución completa de ingeniería para la aplicación multicapa **"Tienda de Perritos"**, diseñada y desplegada bajo principios de la cultura **DevOps**. La arquitectura transiciona un entorno monolítico local tradicional hacia un ecosistema de microservicios inmutables, contenerizados y orquestados de manera automática en la nube utilizando **Amazon Web Services (AWS)**, **Docker**, **Docker Compose** y **GitHub Actions**.

---

## 🚀 Arquitectura del Sistema y Componentes

El ecosistema se encuentra desacoplado en tres capas lógicas totalmente aisladas e interconectadas mediante redes virtuales internas administradas por Docker:

1. **Frontend (Puerto 8080):** Interfaz de usuario responsiva desarrollada en JavaScript Vanilla, optimizada para el consumo asíncrono de la API REST mediante peticiones dinámicas basadas en el hostname de conexión.
2. **Backend (Puerto 3001):** API RESTful encargada de la lógica de negocio, enrutamiento, validación sintáctica de datos y persistencia intermedia, interactuando nativamente con el motor relacional.
3. **Database (Puerto 3306 - Interno):** Motor de base de datos relacional **MySQL 8**. Cuenta con aislamiento perimetral (no expuesto a Internet) para salvaguardar la integridad de los registros.
