<p align="center">
  <a href="https://github.com/DenverCoder1/readme-typing-svg"><img src="https://readme-typing-svg.herokuapp.com?color=F70000&width=460&lines=Falsificar+direcci%C3%B3n+MAC+en+Windows"></a>
</p>

<h1 align="center"></h1>

<h3 align="center">¿Qué es una dirección 'MAC'?</h3>

Una dirección MAC (Media Access Control) es un identificador único que se le asigna a la tarjeta de red del dispositivo que ha sido fabricado, desde routers hasta impresoras y otros dispositivos. Las direcciones MAC están compuestas por 48 bits que son representados en dígitos hexadecimales, cada hexadecimal equivale a 4 binarios (48:4 = 12). Por lo tanto, es formada por 12 dígitos agrupados en seis parejas separadas por dos puntos (:); por ejemplo: `0a:2b:c4:ee:a2:bc`. Los primeros 24 bits (6 dígitos) son configurados por el fabricante de la tarjeta y los últimos 24 bits que restan identifican la tarjeta de ese fabricante.

<p align="center">
  <img src="https://github.com/R3LI4NT/articulos/blob/main/Redes/GNU-Linux/img/direccionMAC.png">
</p>

Al ser identificadores únicos, un administrador de red puede crear listas para denegar o permitir el acceso a uno o varios clientes en la red.

**Lista BLANCA:** Identificadores que tienen `permitido` acceder a la red.

**Lista NEGRA:** Identificadores que tienen `prohibido` acceder a la red.

El filtrado por MAC es útil para expulsar intrusos de la red pero es fácil burlarse de su seguridad con un cambio de MAC. Primeramente, el atacante pone su tarjeta en modo monitor y luego captura los paquetes de la red objetivo (sin estar conectado a dicha red) con `airodump`, lo que le permitirá ver los clientes (STATIONS) conectados a la red y suplantar su dirección MAC aceptada.

<h1 align="center"></h1>

### CAMBIAR DIRECCIÓN MAC | TMAC
Technitium MAC Address Changer es un software gratuito que permite cambiar la dirección MAC única de los adaptadores de red Wi-Fi y LAN. Esta diseñado para Windows, la herramienta cuenta con varas características de uso práctico para usuarios inexpertos, ofrece una interfaz simple e intuitiva.

**Descargar:** https://technitium.com/tmac/

Complentan todos los pasos de instalación.

![1](https://user-images.githubusercontent.com/75953873/185271646-7d8db132-da76-4d75-bd27-a4e5a5cc7db1.png)


Luego de la instalación, deben posicionarse en el adaptador de red que deseen cambiar su MAC:

![2](https://user-images.githubusercontent.com/75953873/185272082-8997647b-ccb2-4f9b-b55f-fd5e06a0719b.png)

Así como MacChanger para Linux, TMAC también trae incorporado una lista de direcciones junto con su fabricador para suplantar:

![3](https://user-images.githubusercontent.com/75953873/185272465-217cd7af-0396-435f-ad10-484006589e4d.png)

Una vez elegido el fabricante, clic en "**_Change Now_**:"

![4](https://user-images.githubusercontent.com/75953873/185273325-6bd6d038-9416-4524-8aa9-bdb097c12724.png)

Si realizamos un escaneo desde ArpScan podemos observar como reconoce la MAC suplantada en la interfaz de red de Windows:

![5](https://user-images.githubusercontent.com/75953873/185273793-8ed99f24-06a6-400a-b6d4-1849a547f30e.png)
