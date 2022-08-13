<p align="center">
  <a href="https://github.com/DenverCoder1/readme-typing-svg"><img src="https://readme-typing-svg.herokuapp.com?size=19&color=13F700&lines=Configuraci%C3%B3n+de+Proxychains+y+Tor"></a>
</p>

<h1 align="center"></h1>

<h3 align="center">¿Qué es un Proxy y cómo funciona?</h3>

Un proxy es un intermediario, o mejor conocido como "puente" entre el cliente/usuario y el navegador. Cuando se utiliza un servidor proxy, lo que hace el navegador es conectarse al servidor proxy y esté redirige el tráfico al sitio web, luego el proxy recibe la respuesta del sitio web y la reenvía al cliente. En resumen, se podría decir que un proxy es una "tercera máquina" controlada bajo nuestras ordenes que ingresa al sitio web, extrae la información y nos la devuelve. Un ejemplo de la vida cotidiana, imagenese que se dirige a un restaurante y espera que el mozo le entregué el menú, después de unos minutos de elección decide optar por una ensalada con pollo, entonces el mozo se encarga de hacerle saber al chef lo que quiere, esté lo prepara y le entrega el platillo al mozo para que usted lo recibe. El mismo ejemplo puede ser usado para una API (Interfaz de programación de aplicaciones).

<a href="#" align="center"><img src="https://github.com/R3LI4NT/articulos/blob/main/Seguridad/Anonimato/GNU-Linux/img/servidor_proxy.png"></a>

</br>

<h3 align="center">¿Qué es la red TOR?</h3>

La red tor es un navegador de código abierto desarrollado en el año 2003 cuyo objetivo es proporcionar seguridad y privacidad al usuario en internet. Contiene una red de servidores proxy muy potentes, evitando todo tipo de control, bloqueos internacionales y seguimientos. Tor utiliza distintos nodos de enrutamiento para llevar la petición a su destino.

**Nodo de entrada:** Se comunica con el cliente de Tor y conecta a los clientes con el resto de la red Tor.

**Nodo intermediario:** Se comunica solamente con otros nodos sin que el tráfico salga de la red Tor, se puede configurar para aumentar su seguridad.

**Nodo de salida:** Es la salida del tráfico de Tor, el cliente recibe su respuesta del destinario y las envía de vuelta a la red del originario. Es el punto más crítico, pués, el tráfico puede ser analizado antes de salir a Internet.

<a href="#" align="center"><img src="https://github.com/R3LI4NT/articulos/blob/main/Seguridad/Anonimato/GNU-Linux/img/proceso_tor.png"></a>

<h1 align="center"></h1>


### PROXYCHAINS

**Instalar herramienta en Debian:**
```
sudo apt-get install proxychains
```

Lo primero que se debe hacer es ingresar a la configuración de proxychains4 y editar el archivo:
```
sudo nano /etc/proxychains4.conf
```

Desmarcan (**#**) la línea de `dynamic_chain`, es la más dinámica ya que su función es saltar de servidor en servidor. Y marcan (**#**) la línea de `strict_chain`, es estricta y poco recomendable.

![1](https://user-images.githubusercontent.com/75953873/182004430-fbc2b6cb-c15c-4a31-8598-9633685efb03.png)

Al final del archivo se encuentrá la lista de los servidores proxys. Los servidores `SOCKS` son comúnmente los que utiliza Tor, socks4 solo utiliza TCP, mientras que socks5 TCP y UDP, por la cual la recomiendo. Guardar el archivo **CTRL + O + ENTER**.

![2](https://user-images.githubusercontent.com/75953873/182004552-68d77571-4664-4174-bc29-504291c2bebf.png)

</br>

### TOR

**Instalar en Debian:**
```
sudo apt-get install tor
```

Iniciar y comprobar servicio de tor:
```
sudo service tor start 
sudo service tor status
```
![3](https://user-images.githubusercontent.com/75953873/182004654-2d06883a-ad62-4795-ab39-dae0fabec20e.png)

Para comprobar que nuestra dirección IP ha sido cambiada ingresamos al navegador pero antes ejecutamos la herramienta:
```
proxychains firefox
```
![4](https://user-images.githubusercontent.com/75953873/182004806-b7b65eea-1820-4c6f-b95d-b7246b5894b4.png)

Otra forma para reconocer nuestra dirección IP pero desde la terminal:
```
proxychains curl ifconfig.me
proxychains curl checkip.dyndns.org
```
![5](https://user-images.githubusercontent.com/75953873/182004912-44806eea-e52b-4769-9f2c-2a800f41b700.png)

</br>

**¿Cómo cambiar de país?**

Restaurar el servicio tor:
```
sudo service tor restart
```
![6](https://user-images.githubusercontent.com/75953873/182004956-177e8082-5890-4aa8-a37f-8dd4b85d676e.png)

**¿Cómo parar el servicio Tor?**
```
sudo service tor stop
```

</br>

Realizar escaneo con Nmap de forma anónima:
```
sudo proxychains nmap -p- --open -sS -sV -n -Pn <URL/IP>
```
![7](https://user-images.githubusercontent.com/75953873/182005136-cd22b0a9-5608-47e6-8b6c-2195c600fd6a.png)

<h1 align="center"></h1>

Para utilizar el proxy de por medio es preciso ejecutar antes proxychains seguido de la herramienta, así como tener el servicio Tor encendido. Un tip que les doy frente a un ataque cibernético es utilizar una IP del país enemigo que estén atacando; por ejemplo, supongamos que ataco una empresa de EE.UU, el FBI tiene la IP de donde provino el ataque pero por fortuna la geolocalizacion de esa IP esta en Irán (un país conflictivo con Estados Unidos), por lo tanto, las autoridades iraníes no revelarán ningúna información de la dirección IP que pueda revelar mi verdadera identidad, después de todo a ellos les favorece que un país enemigo este bajo ataque. ¿Se entiende lo que quiero decir?, países como Estonía, Afganistán, Siria, Yemen, etc donde la policía no puede entrar por sus conflictos políticos.



#### ~R3LI4NT~
