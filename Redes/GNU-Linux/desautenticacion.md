<p align="center">
  <a href="https://github.com/DenverCoder1/readme-typing-svg"><img src="https://readme-typing-svg.herokuapp.com?color=F70000&width=401&lines=Ataque+de+desautenticaci%C3%B3n+Wi-Fi"></a>
</p>

<h1 align="center"></h1>

Un ataque de desautenticación Wi-Fi, también conocido como denegación de servicio a nivel red, consiste en inundar de solicitudes al punto de acceso o estación para saturar el ancho de banda con el objetivo de desconectar a todos los clientes de la red por un tiempo definido. Las tramas de desautenticación se realizan normalmente para determinar una conexión entre un cliente y un punto de acceso (AP) sin necesidad de ir cifrado. Por lo tanto, cualquier persona dentro de la red local (LAN) puede falsificar la dirección MAC de la víctima o AP.


En el siguiente esquema se observa como el `Atacante` envía solicitudes masivas al `Punto de Acceso`, haciendo que el/los clientes u otros equipos que estén conectados a la red LAN se vean afectados.

![esquema_desautenticacion](https://user-images.githubusercontent.com/75953873/180201683-5b0b1d4d-154d-4f3e-91a0-ecec5e35e4c1.png)

<h1 align="center"></h1>

### AIRCRACK-NG

Existen infinidades de herramientas para realizar este ataque, una de las más conocidas es la suite de Aircrack-ng, ya viene incorporada en distribuciones basadas en Debian como lo es Kali Linux y Parrot OS.

**Instalar en Debian:**
```
sudo apt-get install aircrack-ng
```

Pero antes que nada hay que reconocer la dirección MAC del objetivo (AP) y para ello es necesario poner nuestra tarjeta de red en modo monitor. Esto permitirá escuchar y capturar todos los paquetes que viajan en el aire.
```
ifconfig <INTERFAZ> down
iwconfig <INTERFAZ> mode monitor
ifconfig <INTERFAZ> up
```
![1](https://user-images.githubusercontent.com/75953873/180204632-77b2796f-52ba-4f03-8749-f3ce83a16a47.png)

Si lo prefieren automatizado:
```
airmon-ng start <INTERFAZ>
```
![2](https://user-images.githubusercontent.com/75953873/180204828-ea12756e-4daf-4041-95e7-337f19969bd7.png)

Lo siguiente será matar los procesos PID para no presentar ningún error al momento de auditar la red. Cada PID es único y se puede matar de forma manual según su ID:
```
pkill <nombre-del-proceso>
```
![3](https://user-images.githubusercontent.com/75953873/180205864-5c1debac-deed-4bb2-8146-58f864389591.png)

Pero si lo preferimos, aircrack lo hace automatizado por nosotros:
```
airmon-ng check kill
```
![4](https://user-images.githubusercontent.com/75953873/180206365-5a57d41b-26a8-40aa-bac1-1b2ad1b80d39.png)

A continuación, es momento de reconocer las redes de nuestro alrededor:
```
airodump-ng wlan0
```
![5](https://user-images.githubusercontent.com/75953873/180207009-d32f3206-8a73-41b7-b389-466aa8ac67a3.png)

**BSSID:** Dirección MAC del punto de acceso.

**PWR:** Rango en el que se encuentra el AP.

**Beacons:** Número de paquetes envíado por el AP.

**#Data:** Número de paquetes capturados.

**CH:** Número de canal donde opera el AP.

**MB:** Velocidad máxima soportada por el AP. MB = 11 es 802.11b, si MB = 22 es 802.11b+ y hasta 54 son 802.11g.

**ENC:** Tipo de algoritmo de cifrado, generalmente las redes privadas utilizan WPA/WPA2 y WEP. En caso de ser una red pública, el algoritmo que utilizará es OPN = sin encriptación.

**AUTH:** Protocolo de autenticación utilizado.

**ESSID:** Nombre de la red inalámbrica.

Luego de reconocer el BSSID y el canal, quedaría capturar los paquetes del AP objetivo:
```
airodump-ng -c <N-CHANNEL> --bssid <MAC-AP> <INTERFAZ>
```
![6](https://user-images.githubusercontent.com/75953873/180209382-2b325c19-3b9c-4fc9-8395-91d46da5fb16.png)

La `STATION` son los clientes que están conectados la red (BSSID). En otra terminal proseguiremos a lanzar el ataque de desautenticación para desconectarlos:
```
aireplay-ng --deauth <SEGUNDOS> -a <MAC-AP> <INTERFAZ>
```
![7](https://user-images.githubusercontent.com/75953873/180210826-d42ea7a3-8a7a-49aa-9f9a-bedbcc510d1c.png)

Al específicar el tiempo en `0` el ataque será ilimitado, el párametro `a` es el BSSID del punto de acceso que atacará, permitiendo así que todos los clientes no puedan conectarse a dicha red.

El ejemplo anterior desconectará a todos los dispositivos de la red. Ahora, si quisieramos desautenticar a un dispositivo en específico utilizamos el parámetro `-c` **+** la dirección `MAC` del dispositivo (**STATION**).
```
aireplay-ng --deauth <SEGUNDOS> -a <MAC-AP> -c <MAC> <INTERFAZ>
```
![8](https://user-images.githubusercontent.com/75953873/180893744-86724669-affe-45b6-a424-9e0d77e0315e.png)

<h1 align="center"></h1>

### MDK3

Mdk4 es la nueva actualización de Mdk3. Es una herramienta para pruebas de de Wi-Fi desarrollada por el propio proyecto de aircrack-ng.

**Instalar en Debian:**
```
sudo apt install mdk4
```

Mdk4 contiene distintos parámetros con subparámetros de ataques, entre ellos, desautenticación:

**d:** Modo desautenticación

**-c:** Salto de canal.

**-E:** Nombre del punto de acceso (ESSID).

**-B:** Dirección MAC del punto de acceso (BSSID).

**-S:** Dirección MAC del cliente (STATION).

Expulsar a todos los clientes de la red:
```
mdk4 <INTERFAZ> d -c 1,6,10 -E <ESSID>
```
![9](https://user-images.githubusercontent.com/75953873/181661574-1a550111-38a0-4d4f-bed4-753d690892d7.png)



#### ~R3LI4NT~
