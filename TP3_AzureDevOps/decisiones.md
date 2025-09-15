# Decisiones Técnicas - TP3

## Metodología ágil elegida y justificación

Se eligió el **proceso Agile de Azure DevOps** por su flexibilidad y adaptación a equipos pequeños y proyectos académicos. Permite organizar el trabajo en ciclos cortos, priorizar tareas y gestionar cambios de manera eficiente, facilitando la colaboración y el seguimiento del avance.

## Estructura de work items y por qué

- **Epics:** Agrupan funcionalidades principales y objetivos generales del proyecto.
- **User Stories:** Representan necesidades y requisitos funcionales desde la perspectiva del usuario.
- **Tasks:** Descomponen las User Stories en actividades técnicas concretas, facilitando la asignación y el control de progreso.
- **Bugs:** Permiten registrar y gestionar errores detectados durante el desarrollo y pruebas.

Esta estructura asegura trazabilidad, claridad en la asignación de responsabilidades y seguimiento efectivo del avance del proyecto.

## Evidencia de funcionamiento

### Board con work items organizados

<img width="1280" height="547" alt="image" src="https://github.com/user-attachments/assets/94075b15-d814-454d-8782-7c438dfd575f" />

### Sprint con work items

<img width="1280" height="589" alt="image" src="https://github.com/user-attachments/assets/02d29788-1257-42fd-be86-ef80d401d9c2" />

### Pull Request aprobado y mergeado

<img width="1280" height="675" alt="image" src="https://github.com/user-attachments/assets/185da682-760a-4bad-83eb-d400b92462ec" />
<img width="1280" height="660" alt="image" src="https://github.com/user-attachments/assets/62c562e3-2b94-4450-b53c-acc7bada554c" />

### Pipeline

<img width="1211" height="543" alt="image" src="https://github.com/user-attachments/assets/b25e59df-c072-4cdd-9b75-8d5c32e9dd05" />
<img width="1184" height="68" alt="image" src="https://github.com/user-attachments/assets/fd428e80-dcad-4f96-8f01-ecf6ff1661c6" />

## Problemas encontrados y soluciones aplicadas

- **Problema:** No se pudo ejecutar el pipeline por falta de paralelismo gratuito en Azure DevOps.
  <img width="1280" height="287" alt="image" src="https://github.com/user-attachments/assets/9181850d-b64e-4313-bb67-75f857bbb69f" />
  - **Solución:** Se completó el formulario de solicitud de grant gratuito para estudiantes y se adjunta evidencia.
- **Problema:** Políticas de rama impedían aprobar PRs solo por el autor.
  <img width="1280" height="704" alt="image" src="https://github.com/user-attachments/assets/e3af3633-1dfe-4e57-b5b4-e1092bc3739d" />
  - **Solución:** Se ajustaron las políticas para permitir la aprobación por el autor en caso de trabajo individual.

---


