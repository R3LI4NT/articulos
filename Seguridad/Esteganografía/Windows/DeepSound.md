<p align="center">
  <a href="https://github.com/DenverCoder1/readme-typing-svg"><img src="https://readme-typing-svg.herokuapp.com?size=19&color=13F700&width=540&lines=Ocultar+archivos+secretos+en+una+pista+de+audio"></a>
</p>

<h1 align="center"></h1>

La esteganografía es la ténica de ocultamiento de información, archivos multimedia o mensajes en otra pieza de información (imagen o audio) para pasar de desapercibida. A diferencia de la criptografía, está intenta que la información no sea visible de su existencia, mientras que la primera codifica la información sin importar que el intruso conozca la existencia de la misma.

En la serie Mr. Robot, Elliot utiliza una herramienta llamada `DeepSound` para ocultar la información que extraía de su trabajo, investigaba y hackeaba a las personas de su entorno cercano para posteriormente guardar la información en un CD.

<p align="center">
  <img src="https://user-images.githubusercontent.com/75953873/179873094-df240f71-097f-4402-a459-2887437234d6.jpg" width="580" height="300">
</p>

<h1 align="center"></h1>

## DeepSound

- Descargar: https://deepsound.uptodown.com/windows

Una vez instalada nos aparecerá de la siguiente manera:

![2](https://user-images.githubusercontent.com/75953873/179873487-11f50848-a4af-4331-a1c1-02eb3da2496a.png)

Como primer paso hay que descargar una canción o pista de audio, luego le damos clic en `Open carrier files` y añadimos dicha pista. Después pasaremos a seleccionar nuestros archivos que queramos ocultar `Add secret files`.

![3](https://user-images.githubusercontent.com/75953873/179873554-b99bdb60-d0db-40b9-9da7-3219bffb6bfe.png)

Y le damos a `Encode secret files` **>** Encrypt secret files (AES 256):

![4](https://user-images.githubusercontent.com/75953873/179873606-33916ace-bc1e-44f7-b3c9-b95333107a30.png)

Con esto ya tenemos nuestros archivos ocultos en la pista de audio... ¿cómo podemos extraerlos? Eliminamos la pista que hemos importado el principio (click derecho y `remove from list`), repetimos el paso principal `Open carrier files` y esta vez importamos el archivo de salida que nos dejo (en mi caso en documentos).

![5](https://user-images.githubusercontent.com/75953873/179873793-f224de40-01d3-4bbf-a10c-16efaec0d5dc.png)

Ingresan la contraseña y le dan a `Extract secret files`.

<p align="center">
  <img src="https://user-images.githubusercontent.com/75953873/179873871-59804325-6512-4451-9996-c5f7327ecf2f.png">
</p>

<p align="center">
  <img src="https://user-images.githubusercontent.com/75953873/179873909-5a15b8fc-16d5-4539-b379-8518b1af692e.gif">
</p>

