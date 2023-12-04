#### Configura un servidor de DHCP, en la máquina virtual de linux.

#### El DHCP, servirá la ip a otra máquina que estén en la misma red (red interna de VirtualBox); para probarlo tendras que levantar otra máquina virtual.

#### Pasos:

1. **Instalar paquete isc-dhcp-server**

![instalacion](https://github.com/sarald22/SRI/blob/main/tareas/Tarea8DHCP/imagenes/instalacion.png)


#
2. **Editar para una configuración básica /etc/dhcp/dhcpd.conf**

![dhcpd1](https://github.com/sarald22/SRI/blob/main/tareas/Tarea8DHCP/imagenes/dhcpd1.png)
![dhcpd2](https://github.com/sarald22/SRI/blob/main/tareas/Tarea8DHCP/imagenes/dhcpd2.png)


#
3. **Editar para configurar la interfaz de red /etc/default/isc-dchp-server**

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

![macrestart](https://github.com/sarald22/SRI/blob/main/tareas/Tarea8DHCP/imagenes/macrestart.png)

![clienteinterfaces](https://github.com/sarald22/SRI/blob/main/tareas/Tarea8DHCP/imagenes/clienteinterfaces.png)

![ipaddrshow](https://github.com/sarald22/SRI/blob/main/tareas/Tarea8DHCP/imagenes/ipaddrshow.png)





#
9. **Prueba con otro cliente que se le asigna la ip fija**



