<p align="center">
  <a href="https://github.com/DenverCoder1/readme-typing-svg"><img src="https://readme-typing-svg.herokuapp.com?color=13F700&width=550&lines=Crear+servidor+bajo+la+red+tor+DARK+WEB"></a>
</p>

<h1 align="center"></h1>

<h3 align="center">¿Qué es la DARK WEB?</h3>


El dark web es una parte de internet que está intencionalmente oculta y no es accesible para navegadores web y motores de búsqueda estándar. Constituye una pequeña parte de la "deep web" (web profunda), que consiste en páginas web que no son indexadas por los motores de búsqueda. El dark web se mantiene intencionalmente oculto y solo se puede acceder a través de software especializado, como Tor (The Onion Router), I2P (Proyecto de Internet Invisible) o Freenet.

Para comprender qué es la web oscura, es necesario comprender cuatro conceptos diferentes: Clearnet, Deep Web, Dark Web y Darknet. La más fácil de entender es Clearnet, que es Internet tal y como lo conoces, las páginas que encuentras en Google y otros buscadores y a las que puedes acceder directamente desde ellos. Cerca del 90% del contenido en línea no se encuentra disponible a través de los motores de búsqueda. Esto representa una fracción de la Deep Web, que abarca todo el contenido al que no se puede acceder de manera pública. Esta categoría puede incluir sitios web convencionales protegidos por una barrera de pago, así como archivos almacenados en servicios como Dropbox, correos electrónicos guardados en los servidores de tu proveedor de correo, y todas las páginas temporales que se generan, por ejemplo, cuando personalizas una búsqueda de viajes y obtienes resultados específicos.

Si consideramos que la Deep Web representa aproximadamente el 90% de todo lo que abarca Internet, la Dark Web constituiría tan solo alrededor del 0,1% de este vasto espacio digital. Este rincón en línea se caracteriza por ser deliberadamente esquivo para los motores de búsqueda, empleando direcciones IP enmascaradas y siendo accesible únicamente a través de navegadores web especializados. Es relevante destacar que la Dark Web forma parte integral de la Deep Web, aunque ambas son entidades distintas. Para dar una analogía, podríamos pensar en la Deep Web como una ciudad y la Dark Web como varios barrios dentro de esa ciudad. Aunque los barrios son una parte esencial de la ciudad, no representan la ciudad en su totalidad.

Las características clave de la red oscura incluyen:

- **Anonimato:** Los usuarios y operadores de sitios web en la web oscura a menudo permanecen en el anonimato.

- **Comunicación cifrada:** La Dark Web se basa en protocolos de comunicación cifrados que proporcionan un alto nivel de privacidad y seguridad a los usuarios.

- **Servicios ocultos:** Los sitios web alojados en la web oscura a menudo se denominan "servicios ocultos". Estos sitios web tienen direcciones que terminan en ".onion" para Tor y utilizan métodos de cifrado especiales para permanecer ocultos.

- **Mercados para actividades ilegales:** La red oscura es conocida por albergar varios mercados donde se compran y venden bienes y servicios ilegales.

- **Foros y comunidades:** La web oscura también tiene foros, chats y comunidades donde las personas discuten una amplia gama de temas, incluida la privacidad, la seguridad, la piratería y más.

Algunos usuarios lo utilizan por razones legítimas de privacidad y seguridad, especialmente en países con severa censura o vigilancia en línea. Es imperativo priorizar la seguridad en línea y mantener estándares éticos al utilizar estos servicios ocultos.

<p align="center">
  <img src="https://raw.githubusercontent.com/R3LI4NT/articulos/main/Seguridad/Anonimato/GNU-Linux/img/icebergWeb.png">
</p>

Si desean saber más acerca de la Deep Web, les recomiendo leer mi revista llamada "<a href="https://github.com/R3LI4NT/Deep-Web">**Deep Web: El otro lado de Internet**</a>". No solamente cuento anécdotas, al final de la revista enseño como entrar de forma anónima y segura.

<h1 align="center"></h1>

### Crear servidor web bajo la red Tor

El objetivo de este artículo es enseñarles a montar una página web en la red tor de manera pública. Existen servicios en la dark web que ofrecen alojamiento web (hosting) donde los usuarios pueden almacenar los archivos y datos necesarios para que funcione una web 24/7. Para este caso voy a utilizar mi propio ordenador físico como "hosting", esto quiere decir que yo como dueño puedo decidir cuando arrancar y/o detener mi sitio web.

Antes de comenzar deben de tener su sitio ya programado, en mi caso voy a utilizar un proyecto personal. De todas formas, si no tienen conocimiento de diseño web, les dejo un código básico de HTML para que utilicen de ejemplo:

```html
<!DOCTYPE html>
<html>
<head>
    <title>Ejemplo de imagen de Google</title>
</head>
<body>
    <h1>Imagen de Google</h1>
    <img src="https://blog.felinus.cl/wp-content/uploads/2023/04/118.png" alt="Imagen de Google">
</body>
</html>
```

Este código lo deben guardar como `index.html` en un directorio llamado "server". 

![1](https://github.com/R3LI4NT/articulos/assets/75953873/08b4944e-4740-4046-aaad-2162c62d28b1)

A continuación, descargamos tor.

```
sudo apt-get install tor
```

![2](https://github.com/R3LI4NT/articulos/assets/75953873/726b5a05-b91e-4365-86e3-6cda615eb7c4)

Después debemos iniciar un servidor web local en el puerto 80; podemos utilizar nodeJS, python o apache:

```
> python3 -m http.server 80

> sudo service apache2 start
```

Si abrimos el navegador y entramos al localhost, podemos ver nuestro sitio web accesible solo para usuarios dentro de la misma red local y en la clearnet.

![3](https://github.com/R3LI4NT/articulos/assets/75953873/73292d7a-b146-469f-baa9-d9e6348fe821)

Luego tenemos que iniciar el servicio tor:

```
> sudo service tor start
```

Para saber si el servicio se encuentra activo ejecutamos el siguiente comando:

```
> sudo service tor status
```

![4](https://github.com/R3LI4NT/articulos/assets/75953873/25806063-81d2-4bdc-9f78-7cef0301ec69)

Ahora bien, antes de ejecutar tor nos faltaría el útlimo paso. Debemos de entrar al directorio `/etc/tor` y modificar el archivo `torrc`. Debemos desmarcar las líneas `HiddenServiceDir` y `HiddenServicePort` para redirigir el tráfico de localhost a través de la red Tor en el puerto 80. Guardar con CTRL + O.

```
> sudo nano /etc/tor/torrc
```

![5](https://github.com/R3LI4NT/articulos/assets/75953873/157a2670-7fd7-4567-a406-8e94c2d80415)

Iniciamos tor.

![6](https://github.com/R3LI4NT/articulos/assets/75953873/18aa62b7-2362-4de0-9c85-40055ef3d925)

Ya con esto tendríamos nuestra página web bajo la red tor, para encontrar la URL del sitio hay que acceder al archivo de configuración `/var/lib/tor/hidden_service/hostname`.

```
> sudo cat /var/lib/tor/hidden_service/hostname
```

![7](https://github.com/R3LI4NT/articulos/assets/75953873/9cf563c1-ee2e-495e-9911-a34c4ca95c50)

Si copiamos esa URL y la pegamos en el navegador Tor nos mostrará el contenido de nuestro sitio web.

![8](https://github.com/R3LI4NT/articulos/assets/75953873/56eefee5-7292-4500-bc2e-22cdc36f774f)

Ahora voy hacer la misma prueba pero desde mi teléfono y con otra red Wi-Fi distinta.

![9](https://github.com/R3LI4NT/articulos/assets/75953873/edc5d579-78f2-487a-8e39-4262a5407d8e)

Cada vez que quieran modificar el servicio web (los archivos) es necesario restaurar el servicio de localhost y tor. Lo pueden hacer con el siguiente comando:

```
> sudo service apache2 restart

> sudo service tor restart
```

Para detener el servicio:

```
> sudo service apache2 stop

> sudo service tor stop
```

De está manera conseguimos abrir nuestra página web en la darkweb, recuerden que nuestra máquina funciona como "hosting" por lo cual cuando apaguemos nuestro ordenador también lo hará el servicio; esto último puede ser una ventaja para no dejar rastro y que solo sea accesible en ciertos momentos que lo requieran.

</br>

<h1 align="center"></h1>

<h3 align="center"><ins>ADVERTENCIA<ins></h3>

<h4 align="center">Esto es con fines de aprendizaje, no nos hacemos responsables ni el fundador, ni el creador del tema del mal uso de esta herramienta u información.</h4>



#### ~R3LI4NT~
