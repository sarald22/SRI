
## Sara Lamas    ASIR2


4. Añade un Readme.md con la descripción de las opciones del docker-compose.yml


services es para crear nuestro servicio de DNS; dentro de él irán los demás elementos

            services:

en bind pondremos nuestra imagen a descargar y usar; en este caso la de bind9:9.16
            bind9:

                image: internetsystemsconsortium/bind9:9.16

aquí ponemos el nombre de nuestro contenedor a crear

                container_name: asir_bind9

esto es para que se reinicie cada vez que iniciemos docker

                restart: always

aquí ponemos los puertos a usar en neustro servidor y los protocolos a usar. En este caso es el puerto 53 y los protocolos tcp y udp

                ports:

                - 53:53/tcp

                - 53:53/udp

                networks:

                bind9_subnet:

                    ipv4_address: 172.28.5.1

                volumes:

                - ./conf:/etc/bind

                - ./lib:/var/lib/bind

                environment:

                - TZ=Europe/Paris

            networks:

            bind9_subnet: 

                external: true

