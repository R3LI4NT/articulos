<p align="center">
  <a href="https://github.com/DenverCoder1/readme-typing-svg"><img src="https://readme-typing-svg.herokuapp.com?size=19&color=13F700&lines=Configuraci%C3%B3n+de+Proxychains+y+Tor"></a>
</p>

<h1 align="center"></h1>

<h3 align="center">¿Qué es un Proxy y cómo funciona?</h3>

Un proxy es un intermediario, o mejor conocido como "puente" entre el cliente/usuario y el navegador. Cuando se utiliza un servidor proxy, lo que hace el navegador es conectarse al servidor proxy y esté redirige el tráfico al sitio web, luego el proxy recibe la respuesta del sitio web y la reenvía al cliente. En resumen, se podría decir que un proxy es una "tercera máquina" controlada bajo nuestras ordenes que ingresa al sitio web, extrae la información y nos la devuelve. Un ejemplo de la vida cotidiana, imagenese que se dirige a un restaurante y espera que el mozo le entregué el menú, después de unos minutos de elección decide optar por una ensalada con pollo, entonces el mozo se encargá de hacercele saber al chef lo que quiere, esté lo prepará y le entrega el platillo al mozo para que usted lo recibe. El mismo ejemplo puede ser usado para una API (Interfaz de programación de aplicaciones).

<a href="#" align="center"><img src="https://github.com/R3LI4NT/articulos/blob/main/Seguridad/Anonimato/GNU-Linux/img/servidor_proxy.png"></a>

</br>

<h3 align="center">¿Qué es la red TOR?</h3>

La red tor es un navegador de código abierto desarrollado en el año 2003 cuyo objetivo es proporcionar seguridad y privacidad al usuario en internet. Contiene una red de servidores proxy muy potentes, evitando todo tipo de control, bloqueos internacionales y seguimientos. Tor utiliza distintos nodos de enruamiento para llevar la petición a su destino.

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
