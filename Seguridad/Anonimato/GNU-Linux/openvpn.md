<p align="center">
  <a href="https://github.com/DenverCoder1/readme-typing-svg"><img src="https://readme-typing-svg.herokuapp.com?color=13F700&lines=Configurar+una+VPN+con+OpenVPN"></a>
</p>

<h1 align="center"></h1>

<h3 align="center">¿Qué es un VPN y cómo funciona?</h3>

Una VPN (Virtual Private Network | Red Privada Virtual) es un servicio que funciona como "puente" intermediario entre el cliente y el servidor destino. El objetivo fundamental es cifrar todo el tráfico generado de la red por medio del puente y que esté sea redireccionado al servidor, de esta manera, estaría enmascarando nuestra dirección IP real y encriptando todos los datos envíados y recibidos a través de internet.

Una VPN no solamente es útil para cifrar nuestra conexión, tiene otras utilidades como: acceder a sitios restringidos por nuestro ISP (proveedor de servicios), saltar baneo por IP de un videojuego o canal, cuando nuestra IP es estática (no cambia) y necesitamos asignar otra dirección IP pública (dinámica), descargar archivos ílimitados (como en el caso de MEGA), quitar censura digital, entre otras. 

Es recomendado siempre leer las políticas del servicio VPN, no todas prometen seguridad a un 100%, también influye lo que haga el usuario. En caso de un delito, la polícia con una orden judicial puede pedirle a la empresa o a quién te ofrezca el servicio todo el tráfico de tu IP. Los servicios gratuitos, en su mayoría, la conexión es más lenta por ofrecer servidores lejanos a nuestra ubicación, otros hacen usos de nuestro datos para ganar dinero; es por ello que es preciso leer las normas antes de elegir un plan.

</br>

<a href="#" align="center"><img src="https://github.com/R3LI4NT/articulos/blob/main/Seguridad/Anonimato/GNU-Linux/img/procesoVPN.png"></a>

</br>

<h3 align="center">¿Qué diferencia hay entre un VPN y un servidor Proxy?</h3>

Un servidor proxy solo opera mediante aplicaciones, es decir, corre detrás de ellas. Mientras que un VPN opera desde todo el sistema operativo y redirige el tráfico en su totalidad. Los servidores VPN tienen mayor superioridad a la de un proxy.

<h1 align="center"></h1>


### OPENVPN
OpenVPN es una software libre que permite levantar una red privada virtual (VPN). Está basado en SSL/TLS, por lo tanto, permite crear certificados digitales de autenticación de clientes, así como autenticarnos con usuarios y contraseñas. Todo el tráfico es cifrado sin importar si la red es cableada (**Ethernet**) o inalámbrica (**802.11**), con cifrado WEP/WPA/WPA2 o sin cifrar.

**Instalar herramienta en Debian:**
```
sudo apt-get install openvpn 
```

Existen infinidades de servidores gratuitos con soporte OpenVPN de diferentes países, tales como:

- **FreeOpenVPN:** https://www.freeopenvpn.org/

- **VPNbook:** https://www.vpnbook.com/

- **FreeVPN4You:** https://www.vpnbook.com/

- **VPNgate:** https://www.vpngate.net/en/

- **FreeVPN:** http://freevpn.me/accounts

De preferencia, optaré por descargar un servidor gratuito de FreeOpenVPN y anoté las credenciales que necesitaré para establecer la conexión.

![4](https://user-images.githubusercontent.com/75953873/182973920-8c49bb84-9c27-41a4-9d91-d0c30afddb67.png)

Usuario: `freeopenvpn`

Contraseña: `186543146`

Conectarse al servidor:
```
sudo openvpn <SERVIDOR.ovpn>
```
![5](https://user-images.githubusercontent.com/75953873/182974041-a0351940-58b5-48c3-824e-2a2559c65885.png)

</br>

<h3 align="center">¡CONEXIÓN ESTABLECIDA CON ÉXITO!</h3>

<p align="center">
  <img src="https://user-images.githubusercontent.com/75953873/182974290-5698df85-8844-4a2a-89f9-3f5bbfd63880.png">
</p>

</br>

Ahora solo quedaría chequear nuestra dirección IP en el navegador:

![6](https://user-images.githubusercontent.com/75953873/182974522-e8f17bb2-9890-4fd4-9795-8af308800837.png)

Otra forma para reconocer nuestra dirección IP pero desde la terminal:
```
curl ifconfig.me && curl checkip.dyndns.org
```
![10](https://user-images.githubusercontent.com/75953873/182976217-8cb1eece-e822-4acf-821b-31eee69cb547.png)

<h1 alig="center"></h1>

</br>

#### ⚠️ CONSECUENCIAS AL USAR SERVICIOS VPN'S GRATUITOS ⚠️

Lo más probable es que tu ancho de banda sea compartido con el resto de usuarios en internet para contribuir en el anonimato de estos, algunos servicios poco "confiables" se aprovechan de la ténica **Browser Hijacking** (secuestro del navegador) para redirigirte a sitios webs sin que tú lo hayas proporcionado (comparte similitud a DNS Spoofing). Otros servicios monitorean al tráfico del usuario y esté es guardado en sus servidores con la finalidad de vender la información personal de esté y ganar dinero sucio. Dependiendo del equipo de mantenimiento detrás del servicio, una mala configuración por parte de estos puede exponer la dirección IP pública del usuario, poniendo en riesgo su seguridad y privacidad. Es por eso que se recomienda leer las políticas de seguridad, centrarse en la reputación y comentarios de clientes, sí es de paga mucho mejor.

</br>

<h1 align="center"></h1>

<h3 align="center"><ins>ADVERTENCIA<ins></h3>

<h4 align="center">Esto es con fines de aprendizaje, no nos hacemos responsables ni el fundador, ni el creador del tema del mal uso de esta herramienta u información.</h4>



#### ~R3LI4NT~
