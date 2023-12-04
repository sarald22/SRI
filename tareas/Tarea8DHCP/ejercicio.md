#### Configura un servidor de DHCP, en la máquina virtual de linux.

#### El DHCP, servirá la ip a otra máquina que estén en la misma red (red interna de VirtualBox); para probarlo tendras que levantar otra máquina virtual.

#### Pasos:

1. **Instalar paquete isc-dhcp-server**

Abrimos el servidor y ponemos:

            apt install isc-dhcp-server 

de esta manera instalaremos el dhcp en nuestroo servidor

![instalacion](https://github.com/sarald22/SRI/blob/main/tareas/Tarea8DHCP/imagenes/instalacion.png)



#
2. **Editar para una configuración básica /etc/dhcp/dhcpd.conf**

Accedemos a la configuración con:

            nano /etc/dhcp/dhcp:conf

y modificamos las lineas mostradas a continuación:

![dhcpd1](https://github.com/sarald22/SRI/blob/main/tareas/Tarea8DHCP/imagenes/dhcpd1.png)
#

aquí configuramos la red del servidor y del cliente

![dhcpd2](https://github.com/sarald22/SRI/blob/main/tareas/Tarea8DHCP/imagenes/dhcpd2.png)



#
3. **Editar para configurar la interfaz de red /etc/default/isc-dchp-server**

Accedemos al documento con:

            nano /etc/default/isc-dhcp-server

y ponemos de qué interfaz queremos que coja la red el servidor, para realizar las conexiones cliente-servidor

![iscdhcp](https://github.com/sarald22/SRI/blob/main/tareas/Tarea8DHCP/imagenes/iscdhcp.png)


Guardamos los cambios y hacemos un restart del servidor DHCP con:

            sudo systemctl restart isc-dhcp-server

Miramos su estado con:

            sudo systemctl status isc-dhcp-server



#
4. **Declarar una subnet 172.16.0.0/16**ç

Entramos de nuevo a /etc/dhcp/dhcpd.conf y añadimos una subnet:

![subnet](https://github.com/sarald22/SRI/blob/main/tareas/Tarea8DHCP/imagenes/subnet.png)

cerramos y hacemos restart del dhcp de nuevo (sudo systemctl restart isc-dhcp-server)


#
5. **Arranca el servicio con systemctl**

Arrancamos el servidor DHCP con:

            sudo systemctl restart isc-dhcp-server

![start](https://github.com/sarald22/SRI/blob/main/tareas/Tarea8DHCP/imagenes/start.png)




#
6. **Comprueba el servicio con "systemctl status"**

Miramos su estado con:

            sudo systemctl status isc-dhcp-server

![restart](https://github.com/sarald22/SRI/blob/main/tareas/Tarea8DHCP/imagenes/restart.png)




#
7. **Prueba con el cliente que se le asigna un ip en el rango**

Vamos al cliente y miramos su ip con el comando "ip a". Se mostará algo así:

![ipacliente](https://github.com/sarald22/SRI/blob/main/tareas/Tarea8DHCP/imagenes/ipacliente.png)

El adaptador que debemos mirar es el enp0s8, en el que podemos ver que si se le asigna una ip dentro del rango : 192.168.0.23/24



#
8. **Declarar una asignación por mac fija a 172.16.0.5**

En el servidor, accedemos al archivo del dhcpd.conf y añadimos estas lineas:

![mac](https://github.com/sarald22/SRI/blob/main/tareas/Tarea8DHCP/imagenes/mac.png)

De esta manera se le asignará al cliente esa subred indicada, en función de su mac.

#

Ahora hacemos restart del dhcp:

![macrestart](https://github.com/sarald22/SRI/blob/main/tareas/Tarea8DHCP/imagenes/macrestart.png)


#

Vamos al cliente y entramos al archivo de interfaces:

            sudo nano /etc/network/interfaces

y añadimos las siguientes lineas:

![clienteinterfaces](https://github.com/sarald22/SRI/blob/main/tareas/Tarea8DHCP/imagenes/clienteinterfaces.png)

Hacemos un restart para aplicar los cambios:
            sudo systemctl restart networking

#

Luego hacemos un "ip addr show", para verificar las ip que tiene el cliente:

![ipaddrshow](https://github.com/sarald22/SRI/blob/main/tareas/Tarea8DHCP/imagenes/ipaddrshow.png)





#
9. **Prueba con otro cliente que se le asigna la ip fija**

Volvemos a editar "dhcpd.conf" y añadimos otra entrada de host para otra subnet. Ponemos de nuevo la mac del cliente y le asignamos la subred:

![host2](https://github.com/sarald22/SRI/blob/main/tareas/Tarea8DHCP/imagenes/host2.png)

#
Guardamos los cambios y reiniciamos el dhcp:

![restart2](https://github.com/sarald22/SRI/blob/main/tareas/Tarea8DHCP/imagenes/restart2.png)


#
Ahora vamos al cliente y hacemos "ip addr show" para ver que ip tiene:

![ipaddrshow2](https://github.com/sarald22/SRI/blob/main/tareas/Tarea8DHCP/imagenes/ipaddrshow2.png)

