

### 1. Realiza una imagen personalizada de un ubuntu 22.04 que contenga:
- El comando "ip"
- El comando "ping"
- El comando "dig"

Creamos un archivo dockerfile y le añadimos las siguientes lineas:

![dockerfile](https://github.com/sarald22/SRI/blob/main/tareas/Tarea9DockerFile/imagenes/dockerfile.png)


Para construir la imagen, ponemos el siguiente comando:
            docker build -t dockerfile /home/asir2/dockerfile

![dockerfilecreandose](https://github.com/sarald22/SRI/blob/main/tareas/Tarea9DockerFile/imagenes/dockerfilecreandose.png)



#

- **Una vez realizada crea un repositorio en docker hub y súbela.**

Para subirla a dockerhub, nos creamos una cuenta y un repositorio en ella, llamado cliente_ubuntu. Para subir el archivo ponemos los siguientes comandos:

            docker login

            docker tag dockerfile sarald22/cliente_ubuntu

            docker push sarald22/cliente_ubuntu


![dockerhub](https://github.com/sarald22/SRI/blob/main/tareas/Tarea9DockerFile/imagenes/dockerhub.png)

Aquí podemos observar que está subido

![dockerhub2](https://github.com/sarald22/SRI/blob/main/tareas/Tarea9DockerFile/imagenes/dockerhub2.png)



#
- **Pruébala con docker run**

![dockerrun](https://github.com/sarald22/SRI/blob/main/tareas/Tarea9DockerFile/imagenes/dockerrun.png)

![contenedor](https://github.com/sarald22/SRI/blob/main/tareas/Tarea9DockerFile/imagenes/contenedor.png)


#
#
### 2. Realiza una segunda imagen con el servidor de apache, pero esta vez que incluya una página web personalizada. Utiliza COPY.

![docker](https://github.com/sarald22/SRI/blob/main/tareas/Tarea9DockerFile/imagenes/docker.png)

![dockerapache](https://github.com/sarald22/SRI/blob/main/tareas/Tarea9DockerFile/imagenes/dockerapache.png)

![html](https://github.com/sarald22/SRI/blob/main/tareas/Tarea9DockerFile/imagenes/html.png)

![imagenapache](https://github.com/sarald22/SRI/blob/main/tareas/Tarea9DockerFile/imagenes/imagenapache.png)

![dockerrunapache](https://github.com/sarald22/SRI/blob/main/tareas/Tarea9DockerFile/imagenes/dockerrunapache.png)

![contenedorapache](https://github.com/sarald22/SRI/blob/main/tareas/Tarea9DockerFile/imagenes/contenedorapache.png)


