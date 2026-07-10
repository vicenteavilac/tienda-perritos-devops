
# Tienda de Alimentos para Perritos 🐶

Este es un proyecto de una aplicación web de **3 capas** diseñada para demostrar la implementación de flujos de trabajo modernos de **DevOps**, incluyendo containerización, orquestación y despliegue continuo.

## 🏗️ Arquitectura del Proyecto

La aplicación se divide en tres componentes principales:

*   **Frontend:** Interfaz de usuario construida con **HTML5 y JavaScript**, servida mediante un servidor **Nginx**.
*   **Backend:** API REST desarrollada en **Node.js con Express**, que gestiona la lógica de negocio y la comunicación con la base de datos.
*   **Base de Datos:** Instancia de **MySQL** para el almacenamiento persistente de los productos y datos de la tienda.

## 🚀 Tecnologías y Herramientas

*   **Lenguajes:** JavaScript (71.4%), HTML (26.5%).
*   **Containerización:** Docker con **Dockerfiles multietapa** para optimizar el tamaño de las imágenes.
*   **Orquestación Local:** Docker Compose para levantar el stack completo de forma sencilla.
*   **Orquestación de Producción:** Manifiestos de **Kubernetes (K8s)**, incluyendo configuraciones de autoescalado (**HPA**).
*   **CI/CD:** Pipelines automatizados mediante **GitHub Actions** que gestionan el despliegue al clúster (`tienda-cluster-v2`).

## 📂 Estructura del Repositorio

El repositorio está organizado de la siguiente manera:

*   `/.github/workflows`: Definiciones de los flujos de CI/CD para GitHub Actions.
*   `/backend`: Código fuente, dependencias y Dockerfile del servidor Node.js.
*   `/frontend`: Archivos estáticos y configuración de Nginx.
*   `/db`: Scripts de inicialización SQL (`init.sql`) para la base de datos.
*   `/k8s`: Manifiestos de Kubernetes (Deployments, Services, HPA).
*   `docker-compose.yml`: Archivo de orquestación para entornos de desarrollo.

## 🛠️ Instalación y Ejecución Local

### Requisitos Previos
*   Tener instalado **Docker Desktop**.

### Pasos para ejecutar
1.  Clona este repositorio.
2.  Abre una terminal en la carpeta raíz del proyecto.
3.  Ejecuta el siguiente comando para levantar los servicios:
    ```bash
    docker-compose up -d
    ```
4.  Accede a la aplicación en tu navegador:
    *   **Frontend:** [http://localhost:8080](http://localhost:8080).
    *   **Backend (API):** [http://localhost:3001/api/productos](http://localhost:3001/api/productos).

## ⚙️ Características de DevOps Implementadas

*   **Pipeline de CI/CD Completo:** El proyecto cuenta con un flujo automatizado que integra los cambios desde el repositorio hasta el despliegue.
*   **Escalabilidad:** Se incluye un archivo `hpa.yaml` en la carpeta `k8s` para configurar el **Horizontal Pod Autoscaler**, permitiendo que la aplicación escale según la demanda.
*   **Inicialización Automática:** La base de datos se configura automáticamente al arrancar por primera vez gracias al script `db/init.sql`.

## 📝 Notas Adicionales
*   Es posible modificar el código del frontend o backend y reconstruir las imágenes para ver los cambios reflejados en los contenedores.
*   Las imágenes de Docker están configuradas para apuntar a un registro específico (vavila999) según las últimas actualizaciones del despliegue.

---
*Este proyecto fue desarrollado como parte de una evaluación técnica (EFT).*
