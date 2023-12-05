para crear iamgen de un dockerfile
docker build -t nombre_imagen [ruta dockerfile]


subir a dockerhub

docker login
docker tag dockerfile sarald22/cliente_ubuntu
docker push sarald22/[nombre repositorio]

#### 1. Realiza una imagen personalizada de un ubuntu 22.04 que contenga:
- El comando "ip"
- El comando "ping"
- El comando "dig"




#### Una vez realizada crea un repositorio en docker hub y súbela.

#### Comandos para etiquetar y subir imagen al repositorio.

#### Pruébala con docker run.



#### 2. Realiza una segunda imagen con el servidor de apache, pero esta vez que incluya una página web personalizada. Utiliza COPY.