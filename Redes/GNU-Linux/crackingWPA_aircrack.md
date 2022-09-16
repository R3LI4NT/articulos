<p align="center">
  <a href="https://github.com/DenverCoder1/readme-typing-svg"><img src="https://readme-typing-svg.herokuapp.com?font=Fira+Code&pause=1000&color=F70000&width=409&lines=Cracking+WPA%2FWPA2+con+Aircrack-ng"></a>
</p>

<h1 align="center"></h1>

<h3 align="center"><ins>CIFRADO WPA/WPA2</ins></h3>

Actualmente, la mayor parte de los usuarios tiene un router / módem Wi-Fi para conectarse a Internet de forma inalámbrica desde varios dispositivos. Éstos están diseñados con algoritmos de cifrados para evitar que usuarios no autorizados puedan conectarse de forma inalámbrica a nuestro router, robar conexión e incluso sniffear todo el tráfico de nuestros dispositivos en la red local. Los routers ofrecen varios tipos de cifrados y contraseñas de datos diferentes, sin embargo, no todos son iguales. 

El cifrado WPA fue diseñado en el año 2003, cuyo propósito es autenticar al usuario a través del protocolo 802.1x con claves precompartida. Utiliza el algoritmo RC4 para fortalecer el cifrado WEP con una clave de 128 bits y un vector de inicialización de 48 bits para cada vector transmitido, lo que le permite ser menos vulnerable que WEP. Este sistema ofrece una serie de variantes:

- **WPA-Personal:** Utiliza un sistema de claves PSK donde el administrador debe especificar su propia contraseña para que los usuarios puedan conectarse a la red, simplificando el acceso.

- **RADIUS:** Utiliza un sistema de seguridad basado en un servidor en el que los usuarios deben autenticarse con un usuario y una contraseña diferente. Esta enfocado para empresas.

WPA tiene un método de encriptación menos seguro y requiere de una contraseña más corta, al igual que WPA2, puede ser violentado al realizar un ataque de fuerza bruta para penetrar la red.

El cifrado WPA2 fue diseñado en el año 2004 y es la versión certificada del 802.11i. Tiene mayor seguridad y es más simple de configurar, utiliza el estándar de cifrado avanzado (AES) en lugar de TKIP. AES es utilizado por la NSA para proteger información gubernamental de alto secreto, lo que fue útil para proteger dispositivos que estén conectados al Wi-Fi. Este sistema ofrece una serie de variantes:

- **WPA2-Personal:** Otogra seguridad a través de contraseña compleja, ideal para uso doméstico o pequeñas empresas.

- **WPA2-Enterprise:** Utiliza un servidor para autenticar a los usuarios, ideal para grandes empresas.

<p align="center">
  <img src="https://github.com/R3LI4NT/articulos/blob/main/Redes/GNU-Linux/img/wpa_wpa2.png">
</p>

### Ataque de Fuerza Bruta

En el campo de la criptografía, la fuerza bruta es descrita como un método para recuperar claves, nombres de usuarios o directorios de un servidor web probando todas las combinaciones posibles. Para llevar a cabo el ataque, el atacante hace uso de un diccionario (documento de texto con salto de línea) en donde registra las posibles contraseñas débiles para descifrarla y ganar acceso. Dependiendo la herramienta, el procesador del equipo y el diccionario a utilizar, adivinar la contraseña requiere de mucho tiempo si no se cuenta con una enumeración detallada (palabras claves, caracteres especiales, números, símbolos, etc) que pueda dar con la misma.
