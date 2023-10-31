configurar un DNS en Docker Compose

Para incluir el contenido del archivo "/etc/bind/named.conf.options" en la configuración principal del servidor dns. Permite dividir la configuración en varios archivos:

include "/etc/bind/named.conf.options"; include "/etc/bind/named.conf.local";


___________
apuntamps con dos noseque a un servidor dns para que nos dé la misma IP

objetivo: configurar servidor de DNS con contenedor


Práctica DNS
Configuración de la red
Crearemos una red para hacer nuestras pruebas de DNS

Comando básico:

$ docker network create bind9_subnet
Para darle los parámetros personalizados:

$ docker network create \
  --driver=bridge \
  --subnet=172.28.0.0/16 \
  --ip-range=172.28.5.0/24 \
  --gateway=172.28.5.254 \
  bind9_subnet



