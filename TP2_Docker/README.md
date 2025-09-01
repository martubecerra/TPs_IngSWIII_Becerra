# TP2 - Introducción a Docker

## Cómo construir las imágenes

1. Ve a la carpeta del microservicio:
   cd users-api
   docker build -t martubecerra/users-api:v1.0 .
   docker push martubecerra/users-api:v1.0
   docker tag martubecerra/users-api:v1.0 martubecerra/users-api:dev
   docker push martubecerra/users-api:dev

## Cómo ejecutar los contenedores

2. Ve a la carpeta del docker-compose:
   cd ..
   docker-compose up

## Cómo acceder a la aplicación

- QA: http://localhost:8086/users
- PROD: http://localhost:8087/users

## Cómo conectarse a la base de datos MySQL

- Host: localhost
- Puerto: 3307
- Usuario: root
- Contraseña: root

## Cómo verificar que todo funciona correctamente

- Accede a los endpoints /users en QA y PROD para ver los datos.
- Crea usuarios con un POST y verifica que persisten entre reinicios.
- Revisa los logs de los servicios para confirmar la conexión a la base y el entorno activo (QA/PROD).
- Reinicia los contenedores y verifica que los datos siguen presentes.
