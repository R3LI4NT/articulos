<p align="center">
  <a href="https://github.com/DenverCoder1/readme-typing-svg"><img src="https://readme-typing-svg.herokuapp.com?color=13F700FF&width=350&lines=Cifrar+archivos+con+CCRYPT"></a>
</p>

<h1 align="center"></h1>

Cuando se trata de cifrado y descifrado de datos no se puede olvidar de Ccrypt, una herramienta super útil para proteger nuestra información sensible. Si bien es cierto que hay herramientas con GUI que hacen el cifrado de archivos como lo es Cloaker, pero también lo hay para la línea de comandos; como lo haremos en este caso.

Esta herramienta esta basada en el cifrado belga Rijndael, mismo que es utilizado en el estándar AES por el gobierno de los EE.UU. AES utiliza un tamaño de bloque de 128 bits, pero Ccrypt utiliza un tamaño de bloque de 256 bits haciendo que sea más díficil de recuperar los archivos. Cabe recalcar que usualmente usa la extensión de archivo .cpt y permite cifrar cualquier archivo (multimedia sobre todo).

<h1 align="center"></h1>

**Instalar herramienta en Debian:**
```
sudo apt-get install ccrypt
```

Para cifrar un archivo simplemente debemos de proporcionarle el párametro "-e" + el nombre del archivo. Les pedirá una contraseña de cifrado.
```
ccrypt -e <archivo>
```
![1](https://user-images.githubusercontent.com/75953873/179381300-04537638-5bd2-4f7f-a04d-14d342778214.png)
