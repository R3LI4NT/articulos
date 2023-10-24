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

Antes de comenzar deben de tener su sitio ya programado, en mi caso voy a utilizar un blog personal que aún no termino. Aún así, les dejo un código básico de HTML para que utilicen de ejemplo:

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
