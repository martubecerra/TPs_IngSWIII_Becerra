# Decisiones Técnicas - TP2

## Elección de la aplicación y tecnología utilizada
Elegí mi propio microservicio en Go porque ya lo tenía desarrollado, es eficiente en consumo de recursos y muy fácil de containerizar. Go permite crear binarios pequeños y portables, lo que simplifica la construcción de imágenes Docker y el despliegue en cualquier entorno.

## Elección de imagen base y justificación
Usé `golang:1.23-alpine` como imagen base porque es una versión oficial, liviana y segura. Alpine reduce el tamaño de la imagen y mejora la velocidad de descarga y despliegue. Además, la comunidad de Go recomienda Alpine para producción.

## Elección de base de datos y justificación
Opté por MySQL en contenedor porque es ampliamente utilizada, tiene buen soporte en Go y permite persistencia de datos mediante volúmenes. La integración con Docker es sencilla y la configuración de credenciales y volúmenes es directa.

## Estructura y justificación del Dockerfile
El Dockerfile primero instala dependencias, luego copia el código y compila el binario. Expone el puerto 8083 y usa `CMD` para ejecutar la app. Esta estructura permite reproducir la imagen en cualquier entorno y facilita el versionado y despliegue.

## Configuración de QA y PROD (variables de entorno)
En `docker-compose.yml` definí dos servicios (`users-api-qa` y `users-api-prod`) usando la misma imagen pero con la variable de entorno `ENV` diferente. Esto permite que el mismo código se adapte a distintos entornos sin duplicar imágenes ni modificar el código fuente. El microservicio lee `ENV` y ajusta su comportamiento/logs según el entorno.

## Estrategia de persistencia de datos (volúmenes)
Configuré volúmenes en MySQL para asegurar que los datos persistan entre reinicios de contenedor. Esto es fundamental para mantener la integridad de la información y simular un entorno real de producción/desarrollo.

## Estrategia de versionado y publicación
Publiqué la imagen en Docker Hub con los tags `v1.0` (estable) y `dev` (desarrollo). Esto permite identificar versiones estables y de desarrollo, facilitando el despliegue y la trazabilidad de cambios. El `docker-compose.yml` usa el tag estable para producción.

## Evidencia de funcionamiento

<img width="704" height="535" alt="image" src="https://github.com/user-attachments/assets/69d9ea17-b84e-4ab4-9a77-9925fa5f94c0" />
<img width="1237" height="97" alt="image" src="https://github.com/user-attachments/assets/5c53c140-a8ee-468e-b1cd-2e912551071b" />
<img width="398" height="652" alt="image" src="https://github.com/user-attachments/assets/47ea7067-1c3e-4ebd-a906-05423389da0c" />
<img width="570" height="93" alt="image" src="https://github.com/user-attachments/assets/a2234558-c0ed-4cf2-8f62-95e2b502974f" />
<img width="1155" height="42" alt="image" src="https://github.com/user-attachments/assets/2ddd403a-c01e-449d-bdca-47554b09f569" />
<img width="692" height="219" alt="image" src="https://github.com/user-attachments/assets/ef7d0ec7-b4a6-4bbb-873d-b9bf1eb529b3" />
<img width="701" height="368" alt="image" src="https://github.com/user-attachments/assets/8e1cf908-4b1d-469d-a10f-653216b7f897" />

- Logs y capturas muestran la app corriendo en QA y PROD, con endpoints accesibles y diferenciados.
- Conexión exitosa a MySQL, con datos persistiendo entre reinicios.
- Pruebas con curl y navegador confirman el funcionamiento de los endpoints y la persistencia.

## Problemas y soluciones
- Eliminé el submódulo git para que todo el código quede en el repositorio principal y sea accesible para la corrección.

## Declaración de uso de IA
Parte de la documentación y ejemplos fueron generados con GitHub Copilot y verificados manualmente. Todas las decisiones técnicas fueron probadas y justificadas en el entorno real.
