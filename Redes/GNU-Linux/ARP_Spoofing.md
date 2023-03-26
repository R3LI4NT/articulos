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
