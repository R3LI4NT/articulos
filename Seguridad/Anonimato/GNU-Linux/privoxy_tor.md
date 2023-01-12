<p align="center">
  <a href="https://github.com/DenverCoder1/readme-typing-svg"><img src="https://readme-typing-svg.herokuapp.com?size=19&color=13F700&lines=https://readme-typing-svg.herokuapp.com?font=Fira+Code&pause=1000&color=13F700&width=400&lines=Configurar+Privoxy+%26+Tor"></a>
</p>

<h1 align="center"></h1>

<h3 align="center"><ins>PRIVOXY</ins></h3>

Privoxy es un proxy web de código abierto sin almacenamiento de cache con capas de seguridad avanzadas para mejorar la seguridad de navegación, modificar los datos de la página web y los encabezados HTTP, eliminar anuncios y restricción geográfica. Al igual que proxychains, privoxy se puede utilizar mediante socks5 para enrutar todo el tráfico de la red bajo los nodos Tor, lo que lo vuelve aún más anónimo.

El proxy SOCKS5 enruta la conexión a través de un proxy remoto utilizando una IP arbitraria antes de que llegué a la página destino. Para ello utiliza el protocolo TCP o UDP.

Protocolo **TCP:** El protocolo TCP es utilizado para la transmisión de datos entre un dispositivo y otro, siempre y cuando la verificación de la recepción sea correcta y sin errores.

Protocolo **UDP:** El protocolo UDP es similar al anterior, con la única diferencia que no es orientado a transporte de conexiones, es decir, no verifica si la recepción de la información es enviada correctamente y sin presentar errores. Al no contar con una capa de verificación de la recepción lo hace inferior, pero, su velocidad es mayor al TCP al evadir el sistema de verificación de ida y vuelta.
  
- <a href="https://github.com/R3LI4NT/articulos/blob/main/Seguridad/Anonimato/GNU-Linux/proxychains_tor.md">Funcionamiento de un Proxy y nodos Tor (con esquema)</a>
 
<h1 align="center"></h1>

### PRIVOXY

**Instalar herramienta en Debian:**
```
sudo apt-get install privoxy
```

Lo primero que se debe hacer es ingresar a la configuración de privoxy y editar el archivo:
```
nano /etc/privoxy/config
```

Al final del archivo agregan la línea `forward-socks5 / localhost:9050` y guardan los cambios con **CTRL + O + ENTER**:

![3](https://user-images.githubusercontent.com/75953873/184516393-b5351c4f-029d-4c37-9c75-d5bdf06dd244.png)

Luego editan los proxy del navegador (Ej. Firefox) como se muestra en la siguiente captura:

| Proxy |  IP | Puerto |
| ------------- | ------------- | ------------- |
| HTTP Proxy | localhost  | 8118 |
| HTTPS Proxy | localhost  | 8118 |
| SOCKS Host | localhost  | 9050 |

![4](https://user-images.githubusercontent.com/75953873/184516484-079081bc-2d83-444f-9421-97404719568f.png)

Inician los servicios de `tor` y `privoxy`, y comprueban su estado (activo).
```
sudo service tor start && sudo service privoxy start
service tor status
service privoxy status
```
![5](https://user-images.githubusercontent.com/75953873/184516562-a94bdb10-ee9f-4591-acdc-0cd48af311db.png)

Para comprobar que nuestra dirección IP ha sido cambiada ingresamos a una web de geolocalización basada en IP:

![6](https://user-images.githubusercontent.com/75953873/184516708-8384ce3b-359a-47b8-ae26-9878875f9973.png)

**¿Cómo cambiar de país?**

Restaurar el servicio tor:
```
sudo service tor restart
```
![7](https://user-images.githubusercontent.com/75953873/184516780-11f9750d-3d65-42df-909c-3a6ccc3149f3.png)

<h1 align="center"></h1>

Ahora, si deseamos elegir un proxy manual, entonces podemos hacer uso de la lista **->** https://free-proxy-list.net/

![10](https://user-images.githubusercontent.com/75953873/184517400-25ef6ab7-ea5e-464c-bf1b-a2d159093990.png)

Copian la dirección **IP** y el **Puerto**, entran nuevamente a la configuración de privoxy y marcan (#) la línea de `socks5`, agregan `forward-socks4 / IP:Puerto` y `forward-socks4a / IP:Puerto` junto con los datos copiados.

![11](https://user-images.githubusercontent.com/75953873/184517491-17ab35d4-b60f-4340-b6af-d87712022d0f.png)

En la configuración del navegador deben de cambiar los valores por la IP y puerto seleccionado, es importante marcar `SOCKSS v4` como proxy a utilizar:

![12](https://user-images.githubusercontent.com/75953873/184517505-79fa83d0-0c37-4254-bb8f-e0e2ad6f63da.png)

Ya no se estará haciendo uso de Tor, lo conveniente es detener el servicio y reiniciar el de privoxy:
```
sudo service tor stop
sudo service privoxy restart
```
![9](https://user-images.githubusercontent.com/75953873/184517550-0a9c1b9e-d784-4139-8e7a-431088ab5f6d.png)


<h1 align="center"></h1>

En caso de que estén utilizando el entorno de escritorio de Gnome, pueden configurar el proxy desde las Preferencias del menú.

![8](https://user-images.githubusercontent.com/75953873/184516873-25be5cbf-6d45-4766-8379-1b64b4c039b0.png)

</br>

<h1 align="center"></h1>

<h3 align="center"><ins>ADVERTENCIA<ins></h3>

<h4 align="center">Esto es con fines de aprendizaje, no nos hacemos responsables ni el fundador, ni el creador del tema del mal uso de esta herramienta u información.</h4>



#### ~R3LI4NT~
