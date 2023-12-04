#### Configura un servidor de DHCP, en la máquina virtual de linux.

#### El DHCP, servirá la ip a otra máquina que estén en la misma red (red interna de VirtualBox); para probarlo tendras que levantar otra máquina virtual.

#### Pasos:

1. **Instalar paquete isc-dhcp-server**

Abrimos el servidor y ponemos
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

Accedemos al documento con
            nano /etc/default/isc-dhcp-server
y ponemos de qué adaptador queremos que coja la red el servidor, para realizar las conexiones cliente-servidor

![iscdhcp](https://github.com/sarald22/SRI/blob/main/tareas/Tarea8DHCP/imagenes/iscdhcp.png)


#
4. **Declarar una subnet 172.16.0.0/16**

![subnet](https://github.com/sarald22/SRI/blob/main/tareas/Tarea8DHCP/imagenes/subnet.png)


#
5. **Arranca el servicio con systemctl**

![start](https://github.com/sarald22/SRI/blob/main/tareas/Tarea8DHCP/imagenes/subnet.png)


#
6. **Comprueba el servicio con "systemctl status"**

![restart](https://github.com/sarald22/SRI/blob/main/tareas/Tarea8DHCP/imagenes/subnet.png)


#
7. **Prueba con el cliente que se le asigna un ip en el rango**

![ipacliente](https://github.com/sarald22/SRI/blob/main/tareas/Tarea8DHCP/imagenes/ipacliente.png)


#
8. **Declarar una asignación por mac fija a 172.16.0.5**

![mac](https://github.com/sarald22/SRI/blob/main/tareas/Tarea8DHCP/imagenes/mac.png)
#
![macrestart](https://github.com/sarald22/SRI/blob/main/tareas/Tarea8DHCP/imagenes/macrestart.png)
#
![clienteinterfaces](https://github.com/sarald22/SRI/blob/main/tareas/Tarea8DHCP/imagenes/clienteinterfaces.png)
#
![ipaddrshow](https://github.com/sarald22/SRI/blob/main/tareas/Tarea8DHCP/imagenes/ipaddrshow.png)



#
9. **Prueba con otro cliente que se le asigna la ip fija**

![host2](https://github.com/sarald22/SRI/blob/main/tareas/Tarea8DHCP/imagenes/host2.png)
#
![restart2](https://github.com/sarald22/SRI/blob/main/tareas/Tarea8DHCP/imagenes/restart2.png)
#
![ipaddrshow2](https://github.com/sarald22/SRI/blob/main/tareas/Tarea8DHCP/imagenes/ipaddrshow2.png)

