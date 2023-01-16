<p align="center">
  <a href="https://github.com/DenverCoder1/readme-typing-svg"><img src="https://readme-typing-svg.herokuapp.com?size=19&color=13F700&lines=https://readme-typing-svg.herokuapp.com?font=Fira+Code&pause=1000&color=13F700&width=400&lines=Configurar+FoxyProxy+para+Burp+Suite"></a>
</p>

<h1 align="center"></h1>

<h3 align="center"><ins>FOXYPROXY</ins></h3>

FoxyProxy es uno de los proxys más completos y seguros que existen en complementos del navegador Firefox. Es una extensión destinada a usuarios experimentados con conocimientos avanzados ya que dispone de reglas determinadas (listas blancas y listas negras) para especificar que páginas se abran con un proxy y cuales no. Con una configuración decente del proxy, el navegador se conecta a Internet a través de un servidor intermediario, que se conoce como proxy. Al cambiar la configuración del proxy, es posible acceder al contenido del sitio web desde otra posición geográfica, esto con el único propósito de acceder a contenido bloqueado/restringido o para no revelar nuestra dirección IP pública. FoxyProxy es especialmente útil para los usuarios que necesitan acceder a contenido en línea de diferentes regiones o que quieren ocultar su dirección IP para proteger su privacidad en línea.

- <a href="https://github.com/R3LI4NT/articulos/blob/main/Seguridad/Anonimato/GNU-Linux/proxychains_tor.md">Funcionamiento de un proxy y nodos Tor (con esquema)</a>

- <a href="https://github.com/R3LI4NT/articulos/blob/main/Pentesting/WEB/fileUpload.md">Funcionamiento de proxy con Burp Suite</a>
 
<h1 align="center"></h1>

### FOXYPROXY

Su instalación es sencilla, basta con dirigirse a las extensiones de Firefox e instalarlo.

- https://addons.mozilla.org/es/firefox/addon/foxyproxy-standard/

![1](https://user-images.githubusercontent.com/75953873/212214528-62b6add9-fa9b-4cb3-8fa0-2fe3159308f1.png)

Es recomendable permitir que la extensión se ejecute en ventanas privadas (_Opciones_ **->** _Extensiones_ **->** _FoxyProxy_).

![2](https://user-images.githubusercontent.com/75953873/212215729-c57b191f-50d2-4ba6-9a65-7abcd43b6131.png)

Dentro de los ajustes de FoxyProxy tendremos varias opciones, desde importar un nuevo proxy, configurar listas, ver registros, entre otras.

![3](https://user-images.githubusercontent.com/75953873/212216304-33bd5865-6adb-4a7e-99a2-973a468aca29.png)

Añadiremos un nuevo proxy y lo configuramos como se ve en la imagen. El tipo de color hexadecimal es para identificar un proxy sobre otros que hayamos creado.

![3](https://user-images.githubusercontent.com/75953873/212576414-3a011bfa-f22a-4bb5-bcdf-37442e2befab.png)

![4](https://user-images.githubusercontent.com/75953873/212576576-1c1b61a2-67f0-4934-afa8-7c6f0ad85108.png)

Burp Suite escucha por defecto el puerto `8080`, para configurarlo debemos acceder «**Proxy**» **->** «**Options**».

![5](https://user-images.githubusercontent.com/75953873/212576929-0c32f9eb-f5a4-4102-8c1f-3d265394e81a.png)