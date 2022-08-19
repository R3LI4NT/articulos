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

Completan todos los pasos de instalación.

![1](https://user-images.githubusercontent.com/75953873/185271646-7d8db132-da76-4d75-bd27-a4e5a5cc7db1.png)


Luego de la instalación, deben posicionarse en el adaptador de red que deseen cambiar su MAC:

![2](https://user-images.githubusercontent.com/75953873/185272082-8997647b-ccb2-4f9b-b55f-fd5e06a0719b.png)

Así como MacChanger para Linux, TMAC también trae incorporado una lista de direcciones junto con su fabricador para suplantar:

![3](https://user-images.githubusercontent.com/75953873/185272465-217cd7af-0396-435f-ad10-484006589e4d.png)

Una vez elegido el fabricante, clic en "**_Change Now_**:"

![4](https://user-images.githubusercontent.com/75953873/185273325-6bd6d038-9416-4524-8aa9-bdb097c12724.png)

Si realizamos un escaneo desde ArpScan podemos observar como reconoce la MAC suplantada en la interfaz de red de Windows:

![5](https://user-images.githubusercontent.com/75953873/185273793-8ed99f24-06a6-400a-b6d4-1849a547f30e.png)

Lo mismo si mapeamos nuestra red local con Nmap:

![6](https://user-images.githubusercontent.com/75953873/185274372-7e070e09-0b9b-4b03-a3de-b973bc9eddbc.png)

Ahora probaré cambiar la dirección MAC del adaptador de VMware por una Samsung:

![7](https://user-images.githubusercontent.com/75953873/185276995-093531a9-4250-4a5c-964d-db14021c4424.png)

Ahora supongamos que el atacante utiliza una herramienta de reconocimiento de direcciones como lo es Netdiscover o ArpScan:

![8](https://user-images.githubusercontent.com/75953873/185277866-85aabb31-28c2-45c2-baef-c36a7d696799.png)

![9](https://user-images.githubusercontent.com/75953873/185278045-24d91bfc-a538-4306-bcd3-60c2b4d4602e.png)

Luego intentará obtener más información de dicha MAC, así que recurre a fuentes públicas para obtener más información (Ej. <a href="https://macaddress.io/">macaddress.io</a>):

![10](https://user-images.githubusercontent.com/75953873/185278290-e02b62aa-7bce-4f38-8513-d58208009119.png)

Recuerden que pueden volver a su dirección MAC original del adaptador con clic en "**_Restore Original_**."

![11](https://user-images.githubusercontent.com/75953873/185278665-c8848b39-852c-4b02-8646-e0dced1059c3.png)

<h1 align="center"></h1>

</br>

### CAMBIAR DIRECCIÓN MAC | NMAC
NoVirusThanks MAC Address Changer es un software gratuito que permite suplantar la dirección MAC de sus adaptadores de red, así como restaurar la dirección MAC original.

**Descargar:** https://novirusthanks-mac-address-changer.software.informer.com/1.0/

Eligen la interfaz de red y clic en "**_Change MAC_**:

![1](https://user-images.githubusercontent.com/75953873/185519830-cc994b22-24c9-4354-80dd-263b252de78e.png)

Al hacer un reconocimiento de direcciones dentro de nuestra red local, observamos como nuestra MAC fue suplantada con éxito:

![2](https://user-images.githubusercontent.com/75953873/185520177-798407b9-84ad-49ec-96eb-e59a7107f44b.png)

Para cambiar a otra dirección MAC deben de hacer clic en "**_Randomize_**" y para restaurar la dirección de fabrica en "**_Restore MAC_**".

<h1 align="center"></h1>

</br>

### CAMBIAR DIRECCIÓN MAC | SMAC
SMAC es un cambiador de direcciones MAC (Spoofer) potente pero fácil de usar para sistemas Windows 10, 8, 7, VISTA, 2008, 2003, XP y 2000, independientemente de si los fabricantes de tarjetas de red permiten esta opción o no. 

**Descagar:** https://smac-tool.com/

Contiene una lista de fabricante a seleccionar, así como también una opción de **random** para elegir una dirección aleatorio, eliminar MAC y restablecer de fabrica. En "**_Update MAC_** establecemos la dirección a suplantar una vez seleccionada:

![1](https://user-images.githubusercontent.com/75953873/185522708-4bf55922-d43a-4908-a046-50c3e1938508.png)

![2](https://user-images.githubusercontent.com/75953873/185522882-b5d03b34-62b4-48f0-83e3-634f15c70dfd.png)

<h1 align="center"></h1>

</br>

### CAMBIAR DIRECCIÓN MAC | Smart MAC
Smart Changer es un software que no solo permite suplantar una dirección MAC, sino también cambiar la configuración de los DNS para acceder a sitios web bloqueados por el ISP, así como también un proxy gratuito.

**Descargar:** https://download.cnet.com/Smart-DNS-Changer/3000-2381_4-76158452.html

Primeramente seleccionan el adaptador de red:

![3](https://user-images.githubusercontent.com/75953873/185525412-fe3f4305-fa5f-4561-903e-48e334d286fc.png)

En el apartado de **MAC Changer** le dan clic en "**Generate random MAC Address** y luego en "**Apply MAC Address**":

![2](https://user-images.githubusercontent.com/75953873/185524943-a4283071-e829-4dc7-aebb-5151bc12a86c.png)

![1](https://user-images.githubusercontent.com/75953873/185525160-3f77fa20-6814-453a-a1a4-a0f39ab3a6e0.png)

<h1 align="center"></h1>

</br>

### CAMBIAR DIRECCIÓN MAC | Manual
Otra forma de cambiar la dirección MAC en Windows es accediendo a **Administrador de dispositivos** en inicio de Windows **->** **Adaptadores de red** **->** Eligen la **interfaz de red** y luego clic en "Propiedades":

![12](https://user-images.githubusercontent.com/75953873/185280198-3c579dd0-0373-4b51-a2ae-8efb21bb94b2.png)

**Opciones avanzadas** **->** **Network Address** **->** Activan **valores** e ingresan la dirección falsa:

![13](https://user-images.githubusercontent.com/75953873/185280599-5eb0f56d-9647-49f2-b29f-181a69f2a39a.png)



#### ~R3LI4NT~
