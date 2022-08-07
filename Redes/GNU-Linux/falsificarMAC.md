<p align="center">
  <a href="https://github.com/DenverCoder1/readme-typing-svg"><img src="https://readme-typing-svg.herokuapp.com?color=F70000&width=377&lines=Falsificar+direcci%C3%B3n+MAC"></a>
</p>

<h1 align="center"></h1>

<h3 align="center">¿Qué es una dirección 'MAC'?</h3>

Una dirección MAC (Media Access Control) es un identificador único que se le asigna a la tarjeta de red del dispositivo que ha sido fabricado, desde routers hasta impresoras y otros dispositivos. Las direcciones MAC están compuestas por 48 bits que son representados en dígitos hexadecimales, cada hexadecimal equivale a 4 binarios (48:4 = 12). Por lo tanto, es formada por 12 dígitos agrupados en seis parejas separadas por dos puntos (:); por ejemplo: `0a:2b:c4:ee:a2:bc`. Los primeros 24 bits (6 dígitos) son configurados por el fabricante de la tarjeta y los últimos 24 bits que restan identifican la tarjeta de ese fabricante.

<p align="center">
  <img src="https://github.com/R3LI4NT/articulos/blob/main/Redes/GNU-Linux/img/direccionMAC.png">
</p>

Al ser identificadores únicos, un administrador de red puede crear listas para denegar a uno o varios dispositivos a la red.

**Lista BLANCA:** Identificadores que tienen `permitido` acceder a la red.

**Lista NEGRA:** Identificadores que tienen `prohibido` acceder a la red.

El filtrado por MAC es útil para expulsar intrusos de la red pero es fácil burlarse de su seguridad con un cambio de MAC. Primeramente, el atacante pone su tarjeta en modo monitor y luego captura los paquetes de la red objetivo (sin estar conectado a dicha red) con `airodump`, lo que le permitirá ver los clientes (STATIONS) conectados a la red y suplantar su dirección MAC aceptada.
<h1 align="center"></h1>

### CAMBIAR DIRECCIÓN MAC | Manual
Antes que nada, hay que identificar la dirección MAC de nuestra tarjeta de red. El comando "`ifconfig`" es muy útil ya que permite desplegar todas las interfaces de red conectadas a nuestro sistema, así como mostrar información de su IP y MAC, entre otras.

![2](https://user-images.githubusercontent.com/75953873/183269576-fd22db23-1d23-4498-8a94-3884045b0357.png)

Para falsificar la dirección manualmente, en primer lugar hay que deshabilitar el adaptador de red:
```
sudo ifconfig <INTERFAZ> down
```

Asignamos la dirección MAC usando con la orden:
```
sudo ifconfig <INTERFAZ> hw ether <MAC>
```
**Ej:** sudo ifconfig wlan0 hw ether 08:00:46:ba:2b:1b

Activamos el adaptador de red:
```
sudo ifconfig <INTERFAZ> up
```
![3](https://user-images.githubusercontent.com/75953873/183270251-56fd81bc-1bd0-482d-bd8f-bc9dfcd347c7.png)

Ejecutamos `ifconfig` para comprobar el cambio:
```
ifconfig <INTERFAZ> 
```
![4](https://user-images.githubusercontent.com/75953873/183270278-aefb06fa-b599-43eb-857c-fa88173ac43d.png)

Al enviar paquetes desde Kali hacia Windows se puede observar como lo hace desde la MAC falsificada:

![6](https://user-images.githubusercontent.com/75953873/183270490-5b7ccbf8-f131-4f65-821b-1af134110ce1.png)

Lo mismo si hicieramos un `arp -a` desde el CMD:

![7](https://user-images.githubusercontent.com/75953873/183270558-eddaf8e4-85fd-4872-822b-5b15194f898f.png)


<h1 align="center"></h1>

</br>

### CAMBIAR DIRECCIÓN MAC | Automatizado
Existen herramientas gratuitas para automatizar la tarea, como lo es MACchanger que ya viene incorporada en Kali.

**Instalar herramienta en Debian:**
```
sudo apt-get install macchanger
```

Desplegar la dirección MAC actual con el parámetro "`-s`":
```
macchanger -s <INTERFAZ>
```
![8](https://user-images.githubusercontent.com/75953873/183270712-b485940b-9a04-46ad-9c9c-31604c8d018f.png)

Cambiar la dirección MAC a una aleatoria con el parámetro "`-A`". Recuerden que primero deben deshabilitar la tarjeta de red y por último volvera activarla.
```
macchanger -A <INTERFAZ>
```
![9](https://user-images.githubusercontent.com/75953873/183270802-ce041169-c495-4514-a088-f72591bf4513.png)

![10](https://user-images.githubusercontent.com/75953873/183270900-1809a73f-00e7-4617-9231-26010d462944.png)

![11](https://user-images.githubusercontent.com/75953873/183270956-8cc65696-3e89-4ca6-82a8-53b1e3eeea39.png)

La herramienta contiene una lista de todas las direcciones MAC existentes según la empresa fabricante. Desplegar lista con el parámetro "`-l`":
```
macchanger -l
```
![12](https://user-images.githubusercontent.com/75953873/183270996-9d936419-9022-471e-9927-c79490d84c00.png)

Volviendo al principio, los primeros 6 dígitos identifican al fabricante. Por ejemplo, **d8:57:ef** corresponde a **Samsung Electronics** y así sucesivamente. En caso de querer utilizar una dirección MAC en específico acompañamos el parámetro "`-l`" + "`| grep "nombre-del-fabricante"`".

**Ej:** macchanger -l | grep "NATIONAL SECURITY AGENCY"

![13](https://user-images.githubusercontent.com/75953873/183271098-431b10e8-b9b6-4e5a-a2d2-00262a08f0a7.png)

**00:20:91** son los 6 dígitos correspondientes a la Agencia de Seguridad Nacional de los Estados Unidos, pero bien podría ser Samsung, Xiaomi, etc.

Al tener ya los 6 dígitos principales, los otros que restan pueden ser inventados:
```
macchanger --mac=<MAC> <INTERFAZ>
```
**Ej:** macchanger --mac=00:20:91:01:02:03 wlan0

![14](https://user-images.githubusercontent.com/75953873/183271166-60bb1023-9e3f-4991-8d5d-e9475502b87f.png)

![15](https://user-images.githubusercontent.com/75953873/183271297-4623c3d7-32cd-4461-81f5-902087d6e4a3.png)


Para resetear los cambios y volver a la dirección MAC original, entonces utilizan el parámetro "`-p`":
```
macchanger -p <INTERFAZ>
```
![16](https://user-images.githubusercontent.com/75953873/183271238-ec259078-bec2-49c2-93d8-22d62f4ade1c.png)

<h1 align="center"></h1>

</br>

La falsificación MAC es útil para saltarnos un filtrado de MAC o bien ya sean para realizar auditorías o pentesting Wi-Fi. Generalmente un atacante malicoso se aprovecha de esto para enmascarar su identidad y no ser localizado por medio de su MAC. Un administrador de redes puede lanzar un `traceroute mac` para rastrear los paquetes a través de la red local y obtener información detallada de la IP y MAC del dispositivo.
