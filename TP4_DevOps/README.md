# TP4 DevOps - Azure Pipelines

Este proyecto implementa un pipeline CI/CD en Azure DevOps utilizando un agente Self-Hosted para una aplicación con frontend (React) y backend (Node.js).

## Estructura del Proyecto

```
/
├── front/              # Frontend en React
├── back/               # Backend en Node.js
└── azure-pipelines.yml # Configuración del pipeline
```

## Requisitos Previos

- Node.js 18.x o superior
- NPM 8.x o superior
- Cuenta en Azure DevOps
- Agente Self-Hosted configurado en Azure DevOps

## Ejecución Local

### Frontend

```bash
cd front
npm install
npm start
```

El frontend estará disponible en http://localhost:3000

### Backend

```bash
cd back
npm install
npm start
```

El backend estará disponible en http://localhost:3001

## Endpoints API

- `GET /api/message`: Devuelve un mensaje de prueba
- `GET /api/health`: Endpoint de verificación de estado

## Configuración del Agente Self-Hosted

1. En Azure DevOps, ir a Project Settings > Agent pools
2. Crear un nuevo pool llamado "SelfHosted"
3. Agregar un nuevo agente
4. Seguir las instrucciones para descargar e instalar el agente en tu máquina local
5. Configurar el agente como servicio

## Pipeline CI/CD

El pipeline está configurado para ejecutarse automáticamente cuando se realiza un push a la rama `main`. Incluye:

- **Stage CI**:
  - Build del frontend (React)
  - Build del backend (Node.js)
  - Ejecución de tests
  - Publicación de artefactos

## Puertos

- Frontend: 3000
- Backend: 3001

## Notas Adicionales

- El agente Self-Hosted debe tener instalado Node.js y NPM
- El pipeline está configurado para usar Node.js 18.x