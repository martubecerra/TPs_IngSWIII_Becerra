# Decisiones Técnicas - TP1

## Organización del repositorio
- Se decidió un repositorio general con carpetas por TP para mantener todo el trabajo organizado y accesible.
- Se trabajó con las siguientes ramas:
  - `main`: rama principal del repositorio
  - `tp1`: rama específica para el desarrollo del TP1
  - `feature/funcionalidad`: rama para desarrollar la nueva funcionalidad de input
  - `hotfix/fix-error`: rama para corregir el error simulado
  - `rama-conflicto`: rama creada para practicar la resolución de conflictos

## Estrategia de commits
- Se implementaron commits atómicos y descriptivos para mantener una clara trazabilidad de los cambios.
- Se siguió un formato consistente en los mensajes:
  - Prefijo "TP1:" para identificar el trabajo práctico
  - Verbo en presente indicando la acción
  - Descripción concisa del cambio
- Ejemplos de commits:
  - "TP1: agrego script inicial de ejemplo"
  - "TP1: implemento funcionalidad de input"
  - "TP1: corrijo error en la función principal"

## Manejo de errores
- Se simuló un error en la rama `tp1` para practicar el flujo de corrección.
- Se creó la rama `hotfix/fix-error` desde `tp1` para implementar la solución.
- Se realizó el merge del hotfix en:
  - Rama `tp1` para corregir el error en desarrollo
  - Rama `feature/funcionalidad` para mantener la consistencia
- Se documentó el proceso para futura referencia.

## Resolución de conflictos
- Se creó una situación controlada de conflicto usando `rama-conflicto`.
- Se modificó el mismo archivo (`conflicto.txt`) en diferentes ramas.
- Se resolvió el conflicto manualmente, manteniendo los cambios relevantes de ambas ramas.
- Se verificó la integridad del código después de la resolución.

## Gestión de cambios temporales
- Se utilizó `git stash` para guardar cambios temporales sin commit.
- Se creó el archivo `stash.txt` para demostrar el uso de esta funcionalidad.
- Se aplicaron los cambios guardados usando `git stash pop`.
- Se documentó el proceso en el commit final.

## Versionado
- Se implementó versionado semántico para el control de versiones.
- Se creó el tag `v1.0-tp1` para marcar la primera versión estable:
  - 1: versión mayor (major)
  - 0: versión menor (minor)
  - tp1: identificador del trabajo práctico
- Se utilizó `git tag -a` para crear un tag anotado con descripción.

## Integración y Pull Requests
- Se utilizaron Pull Requests para integrar cambios entre ramas.
- Se siguió un proceso de revisión antes de aprobar los merges.
- Se mantuvieron las ramas sincronizadas para evitar conflictos mayores.

## Herramientas y comandos utilizados
- Git básico: `init`, `add`, `commit`, `push`, `pull`
- Gestión de ramas: `branch`, `checkout`, `merge`
- Manejo de cambios: `stash`, `pop`
- Etiquetado: `tag`
- Resolución de conflictos: edición manual y `merge`

## Aprendizajes y mejores prácticas
- Importancia de commits atómicos y mensajes descriptivos
- Valor de la organización en ramas para diferentes propósitos
- Proceso efectivo de resolución de conflictos
- Uso apropiado de tags para versionado
- Gestión eficiente de cambios temporales con stash

## Evidencia de trabajo
- Repositorio organizado con múltiples ramas
- Historial de commits coherente y bien documentado
- Tags para control de versiones
- Archivos de ejemplo funcionales:
  - `app.py`: aplicación principal con funcionalidad de input
  - `conflicto.txt`: ejemplo de resolución de conflictos
  - `stash.txt`: demostración de gestión de cambios temporales
