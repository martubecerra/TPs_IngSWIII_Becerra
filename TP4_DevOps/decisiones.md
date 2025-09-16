# Decisiones Técnicas - TP4 DevOps

## Stack Elegido y Estructura del Repo

### Stack Tecnológico

- **Frontend**: React
  - Elegido por su popularidad y facilidad de uso
  - Permite crear interfaces de usuario interactivas
  - Gran ecosistema de npm packages

- **Backend**: Node.js con Express
  - JavaScript en todo el stack (frontend y backend)
  - Express para crear APIs REST simples
  - Fácil configuración y testing

### Estructura del Repositorio

Se ha optado por un enfoque de mono-repo con la siguiente estructura:

```
/
├── front/              # Frontend en React
├── back/               # Backend en Node.js
└── azure-pipelines.yml # Configuración del pipeline
```

Ventajas de esta estructura:
- Gestión centralizada del código
- Configuración simple del pipeline CI
- Fácil mantenimiento y coordinación de cambios

## Diseño del Pipeline

### Stages y Jobs

El pipeline se ha diseñado con un enfoque multi-stage:

```yaml
stages:
- stage: CI
  jobs:
  - job: BuildBackend
    steps:
    - Build y test de Node.js
    - Publicación de artefactos
  
  - job: BuildFrontend
    steps:
    - Build de React
    - Publicación de artefactos
```

### Artefactos

Se publican dos artefactos principales:

1. **frontend-dist**: Contiene los archivos estáticos compilados del frontend.
2. **backend-dist**: Contiene el código del backend listo para ser desplegado.

La publicación de artefactos permite:
- Conservar los resultados de la compilación para su uso posterior.
- Facilitar el despliegue en diferentes entornos.
- Mantener un historial de versiones compiladas.

## Evidencias

### Creación del Pool y Agente Self-Hosted

<img width="866" height="568" alt="image" src="https://github.com/user-attachments/assets/f2e2ef78-bec6-4342-a42e-1ba1dd86f01c" />
<img width="1138" height="486" alt="image" src="https://github.com/user-attachments/assets/88152555-a930-4ace-808b-e0f1faad8447" />
<img width="2352" height="434" alt="image" src="https://github.com/user-attachments/assets/fc676573-1e5c-494f-8e7b-c2f6151035fe" />

### Ejecuciones de CI

<img width="1210" height="274" alt="image" src="https://github.com/user-attachments/assets/98fe368d-e115-4191-a31d-f1bddc8e783d" />
<img width="1190" height="68" alt="image" src="https://github.com/user-attachments/assets/68f773bb-b434-4585-a55b-2aa60c6e7e8e" />
<img width="1194" height="182" alt="image" src="https://github.com/user-attachments/assets/58c4692f-6def-40b5-8bef-027778a3a4c1" />

### Artefactos Publicados

<img width="1215" height="234" alt="image" src="https://github.com/user-attachments/assets/e1878265-12d8-4f5b-8e6f-3ffc1384ca95" />
<img width="1213" height="537" alt="image" src="https://github.com/user-attachments/assets/2ed5cdc1-4d4a-4d07-a1c9-5728586960f5" />

## Consideraciones Adicionales

### Uso de YAML vs Classic

Se prefiere YAML para definir el pipeline por las siguientes razones:

1. **Versionamiento**: La definición del pipeline se almacena junto con el código fuente.
2. **Revisión de cambios**: Los cambios en el pipeline pueden ser revisados mediante pull requests.
3. **Reutilización**: Facilita la reutilización de configuraciones mediante templates.
4. **Transparencia**: Proporciona una visión clara de cómo se ejecuta el pipeline.

### Ventajas del Agente Self-Hosted en este Escenario

1. **Personalización**: Permite instalar exactamente las versiones de Node.js y otras herramientas necesarias.
2. **Velocidad**: Reduce el tiempo de ejecución al no tener que instalar dependencias en cada ejecución.
3. **Consistencia**: Garantiza que el entorno de build sea consistente en todas las ejecuciones.
4. **Acceso a recursos locales**: Facilita pruebas con recursos que podrían no estar accesibles desde agentes hospedados en Microsoft.

### Estructura del Pipeline para Independencia de Builds

Se ha diseñado el pipeline para que los builds de frontend y backend sean independientes pero parte de la misma integración continua mediante:

1. **Jobs paralelos**: Los jobs de frontend y backend se ejecutan en paralelo.
2. **Artefactos separados**: Cada parte genera su propio artefacto.
3. **Etapas compartidas**: Ambos jobs forman parte de la misma etapa de CI.

Esto permite que un fallo en una parte no afecte necesariamente a la otra, pero mantiene la cohesión del proceso de integración continua.
