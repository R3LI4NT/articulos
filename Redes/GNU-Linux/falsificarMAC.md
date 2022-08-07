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
**Ej:** sudo ifconfig eth0 hw ether 08:00:46:ba:2b:1b

Activamos el adaptador de red:
```
sudo ifconfig <INTERFAZ> up
```
![3](https://user-images.githubusercontent.com/75953873/183269940-caf02f43-c38b-4d73-8cb9-dcd9dca88b57.png)

Ejecutamos `ifconfig` para comprobar el cambio:
```
ifconfig <INTERFAZ> 
```
![4](https://user-images.githubusercontent.com/75953873/183269978-6b07a03a-e065-4ea8-b893-250fa2399519.png)

Al hacer un mapeo con Nmap a nuestra red local podemos observar que nuestra MAC cambio y es legible para cualquiera que esté conectado a la misma red.
```
sudo nmap -sP 192.168.1.0/24
```
![5](https://user-images.githubusercontent.com/75953873/183270094-8638c053-a42e-4c5c-8ee0-7b65109141c8.png)

<h1 align="center"></h1>

</br>

### CAMBIAR DIRECCIÓN MAC | Automatizado
