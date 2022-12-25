<p align="center">
  <a href="https://github.com/DenverCoder1/readme-typing-svg"><img src="https://readme-typing-svg.herokuapp.com?color=13F700FF&width=350&lines=Cifrar+archivos+con+CCRYPT"></a>
</p>

<h1 align="center"></h1>

Cuando se trata de cifrado y descifrado de datos no se puede olvidar de Ccrypt, una herramienta super útil para proteger nuestra información sensible. Si bien es cierto que hay herramientas con GUI que hacen el cifrado de archivos como lo es Cloaker, pero también lo hay para la línea de comandos; como lo haremos en este caso.

Esta herramienta esta basada en el cifrado belga Rijndael, mismo que es utilizado en el estándar AES por el gobierno de los EE.UU. AES utiliza un tamaño de bloque de 128 bits, pero Ccrypt utiliza un tamaño de bloque de 256 bits haciendo que sea más díficil de recuperar los archivos. Cabe recalcar que usualmente usa la extensión de archivo .cpt y permite cifrar cualquier archivo (multimedia sobre todo).

<h1 align="center"></h1>

### CCRYPT

**Instalar herramienta en Debian:**
```
sudo apt-get install ccrypt
```

Para cifrar un archivo simplemente debemos de proporcionarle el párametro "`-e`" + el nombre del archivo. Les pedirá una contraseña de cifrado.
```
ccrypt -e <archivo>
```
![1](https://user-images.githubusercontent.com/75953873/179381300-04537638-5bd2-4f7f-a04d-14d342778214.png)

Como observan, el contenido del fichero es ilegible. Ahora, si quisieramos descifrarlo utilizamos el párametro "`-d`" **+** la `contraseña`.
```
ccrypt -d <archivo>
```
![2](https://user-images.githubusercontent.com/75953873/179381328-f1ad68ed-5ccc-4c73-b615-7169de6c4d44.png)

Supongamos que tenemos un directorio con muchos archivos y queremos cifrar todos los archivos dentro de él y de subdirectorios. Entonces utilizamos el parámetro "`-R`" -**+** "`-e`".
```
ccrypt -R -e <Directorio>
```
![3](https://user-images.githubusercontent.com/75953873/179381353-72c34cea-e0e1-48d0-978a-cc9ad963282c.png)

Y para descifrarlo sería lo inverso:
```
ccrypt -R -d <Directorio>
```

¿Cómo cambiamos la contraseña de cifrado? para ello utilizamos el parámetro "`-x`". Recuerden que si cifraron todos los archivos de un directorio, entonces deben de acompañar el "`-x`" **+** "`-R`". Escriben la contraseña anterior y luego la nueva.
```
ccrypt -R -x <Directorio>
```
![4](https://user-images.githubusercontent.com/75953873/179381394-86096ec9-ad9a-4fc9-b6bc-f144dd2c16b5.png)

Ahora, si solo quisiéramos que muestre el contenido del archivo pero sin que la extensión sea modificada, es decir, se muestre en la terminal el contenido. Entonces utilizamos el parámetro "`-c`", esto solo funciona con ficheros .TXT, en un audio o video no sería el caso.
```
ccrypt -c <archivo>
```
![5](https://user-images.githubusercontent.com/75953873/179381414-186f8f29-4144-4d4e-96b5-5dfee6b1c8f4.png)

Ccrypt también incluye un menú de ayuda **-->** ccrypt --help

</br>

<h1 align="center"></h1>

<h3 align="center"><ins>ADVERTENCIA<ins></h3>

<h4 align="center">Esto es con fines de aprendizaje, no nos hacemos responsables ni el fundador, ni el creador del tema del mal uso de esta herramienta u información.</h4>

</br>

<h1 align="center"></h1>

<h3 align="center"><ins>ADVERTENCIA<ins></h3>

<h4 align="center">Esto es con fines de aprendizaje, no nos hacemos responsables ni el fundador, ni el creador del tema del mal uso de esta herramienta u información.</h4>



#### ~R3LI4NT~
