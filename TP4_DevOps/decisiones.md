# Decisiones Técnicas - TP4 DevOps

## Stack Elegido y Estructura del Repo

### Stack Tecnológico

- **Frontend**: React
  - Elegido por su popularidad, facilidad de uso y amplia adopción en la industria.
  - Permite crear interfaces de usuario interactivas de forma eficiente.
  - Facilita la creación de componentes reutilizables.

- **Backend**: Node.js con Express
  - Proporciona un entorno de ejecución JavaScript del lado del servidor.
  - Express ofrece un framework minimalista pero potente para crear APIs REST.
  - Mantiene la coherencia al usar JavaScript tanto en frontend como backend.

### Estructura del Repositorio

Se ha optado por un enfoque de mono-repo con la siguiente estructura:

```
/
├── front/              # Frontend en React
├── back/               # Backend en Node.js
└── azure-pipelines.yml # Configuración del pipeline
```

Ventajas de esta estructura:
- Facilita la gestión de dependencias entre frontend y backend.
- Simplifica la configuración del pipeline CI/CD.
- Permite una visión unificada del proyecto.
- Facilita la coordinación de cambios que afectan a ambas partes.

## Diseño del Pipeline

### Stages y Jobs

El pipeline se ha diseñado con un enfoque multi-stage:

- **Stage CI (Continuous Integration)**:
  - **Job: BuildFrontend**: Compila y empaqueta la aplicación React.
  - **Job: BuildBackend**: Compila y prueba la API Node.js.

Los jobs se ejecutan en paralelo para optimizar el tiempo de ejecución del pipeline.

### Artefactos

Se publican dos artefactos principales:

1. **frontend-build**: Contiene los archivos estáticos compilados del frontend.
2. **backend-build**: Contiene el código del backend listo para ser desplegado.

La publicación de artefactos permite:
- Conservar los resultados de la compilación para su uso posterior.
- Facilitar el despliegue en diferentes entornos.
- Mantener un historial de versiones compiladas.

## Agente Self-Hosted

Se ha elegido utilizar un agente Self-Hosted por las siguientes razones:

1. **Control total del entorno**: Permite personalizar completamente el entorno de ejecución.
2. **Rendimiento**: Elimina la latencia de red al acceder a recursos internos.
3. **Persistencia**: Permite mantener ciertas dependencias instaladas entre ejecuciones.
4. **Acceso a recursos locales**: Facilita el acceso a recursos que no están disponibles públicamente.
5. **Costo**: Reduce el consumo de minutos de ejecución en Azure DevOps.

## Evidencias

### Creación del Pool y Agente Self-Hosted

[Aquí se incluirán capturas de pantalla mostrando la creación del pool "SelfHosted" y la configuración del agente local]

### Ejecuciones de CI

[Aquí se incluirán capturas de pantalla mostrando ejecuciones exitosas del pipeline de CI]

### Artefactos Publicados

[Aquí se incluirán capturas de pantalla mostrando los artefactos publicados después de una ejecución exitosa]

## Consideraciones Adicionales

### Uso de YAML vs Classic

Se eligió YAML para definir el pipeline por las siguientes razones:

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