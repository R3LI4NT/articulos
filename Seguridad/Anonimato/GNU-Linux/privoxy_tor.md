<p align="center">
  <a href="https://github.com/DenverCoder1/readme-typing-svg"><img src="https://readme-typing-svg.herokuapp.com?size=19&color=13F700&lines=https://readme-typing-svg.herokuapp.com?font=Fira+Code&pause=1000&color=13F700&width=400&lines=Configuraci%C3%B3n+de+Privoxy+%26+Tor"></a>
</p>

<h1 align="center"></h1>

<h3 align="center">PRIVOXY</h3>

Privoxy es un proxy web de código abierto sin almacenamiento de cache con capas de seguridad avanzadas para mejorar la seguridad de navegación, modificar los datos de la página web y los encabezados HTTP, eliminar anuncios y restricción geográfica. Al igual que proxychains, privoxy se puede utilizar mediante socks5 para enrutar todo el tráfico de la red bajo los nodos Tor, lo que lo vuelve aún más anónimo.

El proxy SOCKS5 enruta la conexión a través de un proxy remoto utilizando una IP arbitraria antes de que llegues a la página destino. Para ello utiliza el protocolo TCP o UDP.

Protocolo **TCP:** El protocolo TCP es utilizado para la transmisión de datos entre un dispositivo y otro, siempre y cuando la verificación de la recepción sea correcta y sin errores.

Portocolo **UDP:** El protocolo UDP es similar al anterior, con la única diferencia que no es orientado a transporte de conexiones, es decir, no verifica si la repeción de la información es enviada correctamente y sin presentar errores. Al no contar con una capa de verificación de la recepción lo hace inferior, pero, su velocidad es mayor al TCP al evadir el sistema de verificación de ida y vuelta.
  
- <a href="https://github.com/R3LI4NT/articulos/blob/main/Seguridad/Anonimato/GNU-Linux/proxychains_tor.md">Funcionamiento de un Proxy y nodos Tor (con esquema)</a>
 
<h1 align="center"></h1>

### PRIVOXY

**Instalar herramienta en Debian:**
```
sudo apt-get install privoxy
```

Lo primero que se debe hacer es ingresar a la configuración de privoxy y editar el archivo:
```
sudo nano /etc/proxychains4.conf
```

Al final del archivo agregan la línea `forward-socks5 / localhost:9050` y guardan los cambios con **CTRL + O + ENTER**:

![3](https://user-images.githubusercontent.com/75953873/184516393-b5351c4f-029d-4c37-9c75-d5bdf06dd244.png)

Luego editan los proxy del navegador (Ej. Firefox) como se muestra en la siguiente captura:

| Proxy |  IP | Puerto |
| ------------- | ------------- | ------------- |
| HTTP Proxy | localhost  | 8118 |
| HTTPS Proxy | localhost  | 8118 |
| SOCKS5 Host | localhost  | 9050 |

![4](https://user-images.githubusercontent.com/75953873/184516484-079081bc-2d83-444f-9421-97404719568f.png)
