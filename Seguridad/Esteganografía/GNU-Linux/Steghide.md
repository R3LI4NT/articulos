<p align="center">
  <a href="https://github.com/DenverCoder1/readme-typing-svg"><img src="https://readme-typing-svg.herokuapp.com?size=19&color=13F700&width=680&lines=Ocultar+archivos+secretos+en+una+pista+de+audio+o+imagen"></a>
</p>

<h1 align="center"></h1>

La esteganografía es la ténica de ocultamiento de información, archivos multimedia o mensajes en otra pieza de información (imagen o audio) para pasar de desapercibida. A diferencia de la criptografía, está intenta que la información no sea visible de su existencia, mientras que la primera codifica la información sin importar que el intruso conozca la existencia de la misma. Los contenedores preferidos de los estenógrafos son los archivos multimedia (imágenes, audios, videos, documentos, etc) ya que, para empezar, suelen ser bastante grandes, lo que permite pasar desapercibido el tamaño del mismo. La información también se puede escribir mediante metadatos del archivo. Por ejemplo, una imagen esta compuesta por miles de píxeles y cada uno contiene información descriptiva, es decir, su color RGB. El formato RGB ocupa 24 bits de memoria en imágenes a color, lo que significa que dado el gran número de píxeles en imágenes, se pueden escribir muchos datos en ellos y extraerlos con herramientas especiales.

<p align="center">
  <img src="https://github.com/R3LI4NT/articulos/blob/main/Seguridad/Esteganograf%C3%ADa/GNU-Linux/img/esteganografia.png">
</p>

<h1 align="center"></h1>

### STEGHIDE

Existen una variedad de herramientas de esteganografía disponibles, tanto para <a href="https://github.com/R3LI4NT/articulos/blob/main/Seguridad/Esteganograf%C3%ADa/Windows/DeepSound.md">Windows</a> como para GNU/Linux, pero su diferencia reside en los algoritmos que utiliza cada una para cifrar los datos. Steghide permite ocultar los datos en cualquier formato de imagen (jpg, png, gif, bmp) y también en audio (mp3, wav). Por defecto, utiliza el algoritmo Rijndael (AES), nombrado en otras oportunidades por su popularidad y su nivel fuerte de cifrado que hasta incluso la NSA lo aplica en documentos clasificados.
  
La principal ventaja de esta herramienta es que utiliza un proceso de cálculo propulsado para envolver el documento en cualquier registro de imagen o sonido sin cambiar la apariencia del documento, lo que implica que sin utilizar steghide es casi imposible extraer los documentos ocultos de la imagen.
  
**Instalar herramienta en Debian:**
```
sudo apt-get install steghide
```

#### Incrustar datos en una IMAGEN

Ocultaremos datos en una imagen con Steghide para que solo la persona pueda leerlo. Entonces, creamos el archivo o documento en el que escribiremos nuestro mensaje confidencial, y seleccionamos una imagen (puede ser cualquiera de internet, siempre y cuando la extensión sea compatible). Para lograr esto, ejecutamos el siguiente comando:
```
steghide embed -ef <archivoSECRETO> -cf <IMAGEN>
```
**ef =** embedded file - archivo incrustado.

**cf =** cover file - archivo de cubierta.

![1](https://user-images.githubusercontent.com/75953873/200152264-92b3bb28-a0b9-4f30-b5e9-bf9b2640b299.png)


