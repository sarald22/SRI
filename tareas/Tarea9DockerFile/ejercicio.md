

### 1. Realiza una imagen personalizada de un ubuntu 22.04 que contenga:
- El comando "ip"
- El comando "ping"
- El comando "dig"

![dockerfile](https://github.com/sarald22/SRI/blob/main/tareas/Tarea9DockerFile/imagenes/dockerfile.png)

![dockerfilecreandose](https://github.com/sarald22/SRI/blob/main/tareas/Tarea9DockerFile/imagenes/dockerfilecreandose.png)

docker build -t dockerfile /home/asir2/dockerfile


#

- **Una vez realizada crea un repositorio en docker hub y súbela.**

docker login
docker tag dockerfile sarald22/cliente_ubuntu
docker push sarald22/cliente_ubuntu


![dockerhub](https://github.com/sarald22/SRI/blob/main/tareas/Tarea9DockerFile/imagenes/dockerhub.png)

![dockerhub2](https://github.com/sarald22/SRI/blob/main/tareas/Tarea9DockerFile/imagenes/dockerhub2.png)



#
- **Pruébala con docker run**


#
#
### 2. Realiza una segunda imagen con el servidor de apache, pero esta vez que incluya una página web personalizada. Utiliza COPY.