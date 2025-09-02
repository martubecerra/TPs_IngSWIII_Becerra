# TP3 - DevOps y Azure Pipelines

## Proyecto de Ingeniería de Software III - UCC

Este repositorio contiene la configuración y evidencias del trabajo práctico TP3, integrando Azure DevOps para gestión ágil, control de versiones y automatización de builds.

---

## 1. Acceder al proyecto de Azure DevOps

- Ingresa a [Azure DevOps](https://dev.azure.com/martubecerra/TP3_DevOps_Agile)
- Accede con tu cuenta institucional o la cuenta invitada por el equipo.
- Navega por los Boards, Repos, Pipelines y Pull Requests para ver la configuración y el estado del proyecto.

---

## 2. Clonar y trabajar con el repositorio

```bash
git clone https://github.com/martubecerra/TPs_IngSWIII_Becerra.git
cd TPs_IngSWIII_Becerra
```

- Crea una rama de feature para tus cambios:
  ```bash
  git checkout -b feature/nombre-de-tu-feature
  ```
- Realiza tus cambios y haz commit:
  ```bash
  git add .
  git commit -m "Descripción de tu cambio"
  git push origin feature/nombre-de-tu-feature
  ```
- Solicita un Pull Request en Azure DevOps para fusionar tu rama con `main`.

---

## 3. Ejecutar los pipelines

- Los pipelines están configurados en Azure DevOps bajo la sección **Pipelines**.
- Cada push a la rama `main` dispara automáticamente el pipeline definido en `azure-pipelines.yml`.
- Si el pipeline no corre por falta de paralelismo, revisa el estado y espera la aprobación del grant gratuito solicitado en https://aka.ms/azpipelines-parallelism-request.
- Para ejecutar manualmente, ve a **Pipelines > TP3_DevOps_Agile > Run Pipeline** y selecciona la rama `main`.

---

## 4. Estructura del proyecto en Azure DevOps

- **Boards:**  
  - Epics: Agrupan funcionalidades principales.
  - User Stories: Requisitos funcionales del usuario.
  - Tasks: Actividades técnicas asociadas a cada User Story.
  - Bugs: Registro y seguimiento de errores.

- **Repos:**  
  - Código fuente y archivos de configuración.
  - Ramas principales: `main`, `feature/crear-tarea`, `feature/editar-tarea`.

- **Branches:**  
  - `main`: Rama principal y estable.
  - `feature/crear-tarea`: Desarrollo de la funcionalidad de creación de tareas.
  - `feature/editar-tarea`: Desarrollo de la funcionalidad de edición de tareas.

- **Pull Requests:**  
  - Solicitudes de integración de cambios desde ramas de feature a `main`.
  - Revisión y aprobación según políticas configuradas.

- **Pipelines:**  
  - Automatización de builds y CI/CD.
  - Pipeline configurado en `azure-pipelines.yml` para ejecutar en cada push a `main`.

---

Esta estructura permite gestionar el ciclo de vida del desarrollo, la colaboración y la automatización en

---
