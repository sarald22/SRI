
## Sara Lamas    ASIR2


4. Añade un Readme.md con la descripción de las opciones del docker-compose.yml

#services es para crear nuestro servicio de DNS, dentro de él irán los demás elementos
services:
  bind9:
    image: internetsystemsconsortium/bind9:9.16
    container_name: asir_bind9
    restart: always
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
