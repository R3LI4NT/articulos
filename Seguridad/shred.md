<p align="center">
  <a href="https://github.com/DenverCoder1/readme-typing-svg"><img src="https://readme-typing-svg.herokuapp.com?color=F70000&width=430&lines=Borrado+de+datos+seguro+con+SHRED"></a>
</p>

<h1 align="center"></h1>

Shred es uno de los comandos de Linux mayormente utilizado para borrar datos de forma permanente y no ser recuperados fácilmente por medio de informática forense. La información o archivo que eliga para eliminar es sobrescrita por 1s y 0s varias veces lo que borra permanentemente los datos y no pueden ser recuperable. Normalmente, cuando elimina un archivo, esa parte del disco se marca como lista para que se escriba otro archivo, pero los datos aún están almacenados allí. Si un tercero (por ejemplo, la policía) obtuviera acceso físico a su disco, podría, utilizando técnicas avanzadas, acceder a los datos que pensó que había eliminado.

El más común y repetitivo es el comando "`rm`" para eliminar directorios y archivos, pero... ¿se eliminan del TODO en realidad? la respuesta es un retundo NO, lo que se destruye es el tamaño del fiechero para liberar espacio en el disco duro (conocido como número inodo), y como ya sabrán, existen software gratis y de pago que se encargan de recuperar datos.

<h1 align="center"></h1>

**Instalar herramienta en Debian:**
```
sudo apt-get install coreutils 
```
Coreutils es un paquete de tipo Unix que contiene varias herramientas y utilidades como ls, cd, rm, `shred`, entre otras.

![1](https://user-images.githubusercontent.com/75953873/179375886-b7d55261-515a-44b1-84ea-9fe51f596b23.png)

Utilizaré como ejemplo un archivo de texto donde escribiré tres líneas y posteriormente ejecutare el comando `shred` **+** nombre del archivo a sobreescribir:

![2](https://user-images.githubusercontent.com/75953873/179375954-d4ae3128-3c96-45de-ba0f-45de20086496.png)

Como observarán, el documento es totalmente ilegible ya que es ofuscado con una serie de caracteres aleatorios. En el ejemplo anterior no he utilizado ningún parámetro a especificar, ya de por sí la herramienta se encarga de añadir una variedad de caracteres por defecto (25). Si quisiéramos eliminar el fichero deberíamos a especificar con el parámetro "`-u`":

![3](https://user-images.githubusercontent.com/75953873/179379315-f7a81860-38fa-4eca-8739-b9a14fc4ffcf.png)

El parámetro "`-n`" se utiliza para sobreescribir el archivo cuantas veces quieramos, en este caso lo que hago es borrar todo el contenido del disco (**cuidado con esto**, es a modo de ejemplo):

![4](https://user-images.githubusercontent.com/75953873/179379527-d16a4963-629e-47ff-abd0-5712931654f3.png)

Con el parámetro "`-v`" (verbose) indicamos que nos muestre los detalles que sobreescribe y poder tener noción de que pasar por detrás...

![5](https://user-images.githubusercontent.com/75953873/179379659-50a2e7a8-5953-4f04-9d26-278899828bb5.png)

Por último, contiene el parámetro "`-z`" el cual agrega una sobrescritura al final con ceros para ocultar la evidencia con caracteres encriptados.

![6](https://user-images.githubusercontent.com/75953873/179379711-a2069c48-fc2a-4f59-ad00-1602edfbc1a0.png)



#### ~R3LI4NT~
