<p align="center">
  <a href="https://github.com/DenverCoder1/readme-typing-svg"><img src="https://readme-typing-svg.herokuapp.com?font=Fira+Code&pause=1000&color=F70000&width=470&lines=Cracking+WPS+PIN+-+Ataque+Pixie+Dust"></a>
</p>

<h1 align="center"></h1>

<h3 align="center"><ins>SISTEMA WPS PIN</ins></h3>

WPS (_Wifi Protected Setup_) es un estándar de red lanzado en el año 2007 cuyo objetivo es facilitar la conexión inalámbrica con tan solo pulsar un botón proveniente del router. De este modo, se evita introducir la contraseña del Wi-Fi (sobre todo si es larga y difícil de recordar) reemplazandola con un PIN de 8 dígito para su fácil acceso. El cifrado WEP no es compatible con WPS, sino con WPA/WPA2. Esto no quiere decir que este basado en brindar seguridad, sino simplemente simplificar el acceso, de hecho, mantenerlo activado puede presentar alto riesgo para los dispositivos que se encuentren conectados a la misma red.

La conexión de WPS es muy sencilla, una de las más comunes es pulsar el botón detrás del router y el emparejamiento con los dispositivos se hará automático. Algunos dispositivos como impresoras, adaptadores Wi-Fi poseen su propio botón WPS, por lo que primero se debe pulsar el del router y luego el del aparato para establecer la conexión. Algunos routers con botón WPS ofrecen un PIN de ocho cifras para simplificar la conexión con dispositivos que no tengan dicho botón, está se debe copiar e introducir manualmente como si fuera la contraseña de la red, que por lo general es más compleja. En caso de no contar con dicho PIN se debe acceder al panel de control del router desde el navegador (http://192.168.1.1) **>** Seguridad WPS y copiar el PIN (también se puede generar uno nuevo).

WPS contempla cuatro tipo de configuraciones diferentes para el intercambio de credenciales:

- **PIN** (Número de identificación personal): Al usuario se le ofrece un PIN de 8 dígitos para que ingrese manualmente en sus dispositivos y establezca conexión sin otorgar la contraseña real del Wi-Fi.

- **PBC** (Configuración del botón pulsador): El usuario presionar el botón WPS del punto de acceso (AP) y seguidamente el botón WPS del dispositivo para establecer la autenticación. Cualquier otra estación cercana no autorizada puede ganar acceso.

- **NFC** (Comunicaciones de campo cercano): Es una tecnología inalámbrica que permite la comunicación e intercambio de datos entre dos dispositivos sin interrupciones a corta distancia. El dispositivo debe ser colocado cerca del router para intercambiar información

- **USB** (Bus Universal en Serie): Es un método de forma física, las credenciales se guardan en una memoria flash USB que luego es introducido en el dispositivo que se desee autenticar a la red.

<p align="center">
  <img src="https://github.com/R3LI4NT/articulos/blob/main/Redes/GNU-Linux/img/WPS_PIN.png">
</p>

### Riesgos

En primer lugar, al presionar el botón WPS se esta inhabilitando todas las medidas de seguridad configuradas en la conexión, incluyendo el cifrado WPA/WPA2 será de poca utilidad. El PIN consta de 8 dígitos, lo que quiere decir que un ataque de fuerza bruta es más que suficiente para adivinarlo y acceder a la red. Mientras que eataque <a href="https://www.wifi-libre.com/topic-57-pixie-dust-ataque-de-fuerza-bruta-offline-para-generar-el-pin-valido.html">**WPS Pixie Dust**</a> se centra en capturar el intercambio de paquetes entre el router víctima y el atacante, para posteriormente intentar crackear el PIN sin necesidad de conexión (offline) en tan solo un par de segundos. El PIN es dividido por dos claves precompartidas por cada PSK (mitad y mitad), las solicitudes del **AP** funcionan de la siguiente manera:

- _Envíos informáticos - EAPOL Start_: El cliente y el dispositivo de acceso utilizan paquetes EAP para transportar información de autenticación. El cliente envía un mensaje EAPOL-Start para iniciar la autenticación 802.1X en el dispositivo de acceso.

- _Envíos del enrutador: solicitud EAP para la identidad_: El autenticador envía una solicitud EAP para la identidad del solicitante de conexión (dispositivo cliente). El solicitante responde al autenticador con una Respuesta de identidad EAP que contiene la identidad (nombre de usuario) utilizada para la autenticación.

- _Envíos del enrutador: solicitud EAP_ / _Envíos por computadora: respuesta EAP_: Los marcos de solicitud EAP y los marcos de respuesta EAP se transmiten de un lado a otro hasta que el servidor de autenticación envía un mensaje EAP-Success al switch. El autenticador envía solicitudes al sistema en busca de acceso y las respuestas otorgan o niegan el acceso.

Estas solicitudes son repetidas continuamente antes de que se llegue a enviar las credenciales, durante el proceso se captura la clave pública de Diffie Hellman del miembro y del registrador, y dos hashes del PIN WPS (PSK1, PSK2). Luego se realiza la fuerza bruta contra los hashes y como resultado se agrupan los 4 dígitos de cada clave.

- <a href="https://forums.kali.org/showthread.php?24286-WPS-Pixie-Dust-Attack-(Offline-WPS-Attack)">WPS Pixie Dust Attack (Offline WPS Attack)</a>

<h1 align="center"></h1>

#### Identificar puntos de accesos habilitados para WPS

Con el comando `wash` **+** `-i` **+** `interfaz` podemos identificar aquellos puntos de acceso de nuestro alrededor que tienen habilitado el sistema WPS.

![0](https://user-images.githubusercontent.com/75953873/191641965-ea94c4ba-630e-4a06-8220-c763a8497888.png)

</br>

### ONESHOT | Cracking WPS PIN - Pixie Dust

OneShot es un script hecho en Python para realizar ataque de Pixie Dust sin necesidad de cambiar el adaptador de red a modo monitor. Se utiliza **wpa_supplicant** para obtener los datos requeridos.

**_Instalar en Debian:_**
```
> sudo apt install -y python3 wpasupplicant iw wget

> sudo apt install -y pixiewps

> git clone --depth 1 https://github.com/drygdryg/OneShot && cd OneShot
```

**-i:** Nombre de la interfaz a utilizar (Ej: wlan0).

**-b:** Dirección MAC del punto de acceso (AP).

**-K:** Modo de ataque Pixie Dust

Ejecutamos el script y esperamos que capture las claves y realice el crackeo automático:
```
python3 oneshot.py -i wlan0 -b XX:XX:XX:XX:XX:XX -K
```
![1](https://user-images.githubusercontent.com/75953873/191641118-616f58c7-b60c-4f2a-9d7a-68009df2172d.png)

<h4 align="center">PIN crackeado con éxito = 49011838</h4>

![2](https://user-images.githubusercontent.com/75953873/191642529-e21dbec8-434c-472d-b8d2-f28c5e6c40be.png)
