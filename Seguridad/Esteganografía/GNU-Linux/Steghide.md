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

#### ➤ Incrustar datos en una IMAGEN

Ocultaremos datos en una imagen con Steghide para que solo la persona pueda leerlo. Entonces, creamos el archivo o documento en el que escribiremos nuestro mensaje confidencial, y seleccionamos una imagen (puede ser cualquiera de internet, siempre y cuando la extensión sea compatible). Para lograr esto, ejecutamos el siguiente comando:
```
steghide embed -ef <archivoSECRETO> -cf <IMAGEN>
```
**ef =** embedded file - archivo incrustado.

**cf =** cover file - archivo de cubierta.

![1](https://user-images.githubusercontent.com/75953873/200152264-92b3bb28-a0b9-4f30-b5e9-bf9b2640b299.png)


#### ➤ Extraer datos de la IMAGEN

En el ejemplo anterior, Steghide agrega una capa de seguridad adicional al permitirnos usar contraseña para ello. Ahora bien, para extraer los datos ocultos, ejecutamos lo siguiente:
```
steghide extract -sf <IMAGEN>
```
**sf =** secret file - archivo secreto.

![2](https://user-images.githubusercontent.com/75953873/200152447-fb81f6ff-e6fb-4f6c-9598-8e46514eab64.png)


#### ➤ Recuperar información del archivo incrustado

En caso de que sospechemos de que una imagen tiene datos ocultos y, de ser así, entonces utilizamos el siguiente comando:
```
steghide info <IMAGEN>
```
![3](https://user-images.githubusercontent.com/75953873/200152653-081126fb-ae17-452e-9279-043ec2d2e469.png)


**Archivo:** test.txt

**Tipo de encriptación:** Rijndael (AES) con longitud de bloque de 128 bits.


#### ➤ Algoritmo de Cifrado

Podemos escoger el tipo de algoritmo de cifrado para ocultar nuestros datos. Steghide contiene una lista de los algoritmo que soporta.
```
steghide --encinfo
```
![4](https://user-images.githubusercontent.com/75953873/200152838-6b03e0c5-018c-44f6-8e1a-dc4ce56ac91a.png)

Para escogerlo, se puede lograr fácilmente con solo usar el siguiente comando:
```
steghide embed -ef <ARCHIVO> -cf <IMAGEN> -e <ALGORITMO>
```
![5](https://user-images.githubusercontent.com/75953873/200152934-59d7919f-6489-4c4b-8db8-b96a531c002d.png)

#### ➤ Sobrescribir los archivos existentes

Al extraer el archivo, aún nos queda el mismo archivo en el directorio con el mismo nombre. Entonces lo mejor sería utilizar el siguiente comando para sobrescribir el archivo existente:
```
steghide extract -sf <IMAGEN> -f 
```
![6](https://user-images.githubusercontent.com/75953873/200153075-957e5503-1fff-4285-a0ee-ba3fc8eb074c.png)

#### ➤ Modo de Comprensión

Si lo deseas, puedes comprimir el archivo antes de ocultarlo. El nivel de compresión varia `1` y `9`, el primer nivel brinda velocidad de comprensión mientras que, en el noveno nivel, te proporciona mejores técnicas de comprensión.
```
steghide embed  -ef <ARCHIVO> -cf <IMAGEN> -z 5
```
![7](https://user-images.githubusercontent.com/75953873/200153226-d3c1fb7e-15d6-4d35-9ea2-acc0327ddde4.png)


#### ➤ Modo de Anti-Comprensión

Ahora, si no queremos comprimir un archivo antes de ocultarlo, utilizamos el siguiente comando:
```
steghide embed  -ef <ARCHIVO> -cf <IMAGEN> -Z
```

#### ➤ Modo Detallado

Mostrar información muy detallada sobre  el  estado del proceso de adjuntado o del de extracción.
```
steghide embed  -ef <ARCHIVO> -cf <IMAGEN> -N
```
![9](https://user-images.githubusercontent.com/75953873/200153436-8edcd9e4-388a-48dc-ade8-779181c35ad5.png)


#### ➤ Incrustar archivo sin nombre

A su vez, también podemos ocultar el archivo sin necesidad de nombrarlo. Si  se usa  esta opinión, el extractor necesitará declarar un nombre de archivo para  decirle  a  steghide  en donde escribiremos los datos adjuntos.

```
steghide embed  -ef <ARCHIVO> -cf <IMAGEN> -N
```
![8](https://user-images.githubusercontent.com/75953873/200153377-de0eca83-3263-4051-ba9d-641dda4c6c93.png)
