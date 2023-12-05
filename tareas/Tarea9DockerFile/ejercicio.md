para crear iamgen de un dockerfile
docker build -t nombre_imagen [ruta dockerfile]


subir a dockerhub

docker login
docker tag dockerfile sarald22/cliente_ubuntu
docker push sarald22/[nombre repositorio]
