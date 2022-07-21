<p align="center">
  <a href="https://github.com/DenverCoder1/readme-typing-svg"><img src="https://readme-typing-svg.herokuapp.com?color=F70000&width=401&lines=Ataque+de+desautenticaci%C3%B3n+Wi-Fi"></a>
</p>

<h1 align="center"></h1>

Un ataque de desautenticación Wi-Fi, también conocido como denegación de servicio a nivel red, consiste en inundar de solicitudes al punto de acceso o estación para saturar el ancho de banda con el objetivo de desconectar a todos los clientes de la red por un tiempo definido. Las tramas de desautenticación se realizan normalmente para determinar una conexión entre un cliente y un punto de acceso (AP) sin necesidad de ir cifrado. Por lo tanto, cualquier persona dentro de la red local (LAN) puede falsificar la dirección MAC de la víctima o AP.


En el siguiente esquema se observa como el `Atacante` envía solicitudes masivas al `Punto de Acceso`, haciendo que el/los clientes u otros equipos que estén conectados a la red LAN se vean afectados.

![esquema_desautenticacion](https://user-images.githubusercontent.com/75953873/180201683-5b0b1d4d-154d-4f3e-91a0-ecec5e35e4c1.png)

<h1 align="center"></h1>

Existen infinidades de herramientas para realizar este ataque, una de las más conocidas es la suite de Aircrack-ng, ya viene incorporada en distribuciones basadas en Debian como lo es Kali Linux y Parrot OS.

**Instalar en Debian:**
```
sudo apt-get install aircrack-ng
```
