
TRABAJO DE REFORZAMIENTO CREADO POR RODRIGO FLORES ALVAREZ

SIGUE LO TRABAJADO EN EL LABORATORIO ANSIBLE+ NGINX

ESTE TRABAJO AGREGA UN API GATEWAY COMO IMPLEMENTACIÓN ADICIONAL AL TRABAJO 

Los servicios se agrupan en redes Docker específicas:

app_net: Conexión de aplicaciones Nginx

persistence_net: Conexión de Redis y PostgreSQL

monitor_net: Conexión de Grafana y monitorización

Flujo de Comunicación
Usuarios → Aplicaciones Nginx

Aplicaciones → Redis/PostgreSQL 
Aplicaciones → Grafana 

Requisitos Previos
Terraform instalado

Docker instalado y en ejecución

Acceso a internet para descargar imágenes de Docker Hub


## Despliegue 

COMANDOS:
Iniciar sesión de docker:
````````````
docker login
````````````
Para visualizar los contenedores en docker:
````````````
docker ps
````````````
Inicializar Terraform:
````````````
terraform init
````````````
Revisar el plan de ejecución:
````````````
terraform plan
````````````
Aplicar la configuración:
````````````
terraform apply 
````````````
Levantamiento del stack por Docker Compose:
````````````
docker compose up -d
````````````
En caso de error al levantamiento/ eliminar el docker compose:
````````````
docker compose down
````````````
Pruebas del health check del API GATEWAY:
````````````
curl http://localhost/health
````````````
Pruebas para probar los microservicios a traves del API GATEWAY:
````````````
curl http://localhost/api/app1
curl http://localhost/api/app2
curl http://localhost/api/app3
````````````
Prueba del grafana:
````````````
curl http://localhost/grafana/
````````````
Prueba de la red estatica:
````````````
curl http://localhost/web/
````````````


---
