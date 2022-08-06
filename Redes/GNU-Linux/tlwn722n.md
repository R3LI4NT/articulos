<p align="center">
  <a href="https://github.com/DenverCoder1/readme-typing-svg"><img src="https://readme-typing-svg.herokuapp.com?color=F70000&width=447&lines=TL-WN722N+en+modo+monitor+Kali+Linux"></a>
</p>

<h1 align="center"></h1>

<p align="center">
  <img src="https://github.com/R3LI4NT/articulos/blob/main/Redes/GNU-Linux/img/TL_WN722N.png">
</p>

<h1 align="center"></h1>

<h3 align="center">ADAPTADOR TP-LINK TL-WN722N</h3>
El adaptador USB inalámbrico TL-WN722N fue desarrollado y es mantenido por la empresa <a href="https://www.tp-link.com/us/">TP-Link Technologies CO. LTD</a>. Permite conectar una computadora de escritorio o portátil a una red inalámbrica y acceder a una conexión a Internet de alta velocidad. Proporciona una velocidad inalámbrica de hasta 150 Mbps, lo que es beneficioso para los juegos en línea o incluso la transmisión de video.

#### Problema con Kali Linux
Luego de que Offensive Security lanzará la nueva versión de Kali Linux, el kernel de esté también se actualizó lo que hizo que afectará los controladores del adaptador en versiones 5.0.0 del kernel en adelante. El adaptador es reconocido perfectamente y deja navegar en internet, pero al momento de ponerlo en modo monitor devuelve el siguiente error:

<p align="center">
  <img src="https://user-images.githubusercontent.com/75953873/183257849-f1876da4-cbbc-44ab-acf3-f9cbfbfc4f6e.png">
</p>

<h1 align="center"></h1>

### Solución para versiones 4.X.X | 5.X.X
El primer paso es actualizar la lista de paquetes disponibles y sus versiones.
```diff
- sudo apt-get update && sudo apt-get dist-upgrade
```

Luego, instalan el paquete `bc`. Es una calculadora que se puede utilizar en la línea de comandos, su principal utilidad en los scripts bash es realizar operaciones matemáticas  y que nos devuelva un valor.
```diff
! sudo apt-get install bc
```

Los `linux-headers` son los encabezados de paquetes que contiene el kernel para definir los componentes del núcleo y sus interfaces, como también para compilar drivers y meterlos en el código del núcleo. Para instalar los encabezados más recientes debemos de ejecutar el siguiente comando:
```diff
+ sudo apt-get install -y bc linux-headers-$(uname -r)
```
No es necesario especificar una versión, al incluir "`uname -r`" esté automáticamente reconocerá las versiones compatibles con tu sistema e intentará instalar la más adecuada.

Después de instalar los headers hay que eliminar el módulo `r8188eu.ko` con `rmmod`:
```diff
! sudo rmmod r8188eu.ko
```

Aircrack lanzó un controlador oficial para RTL8188eus en su repositorio, por lo que debemos clonarlo:
```diff
+ git clone https://github.com/aircrack-ng/rtl8188eus
+ cd rtl8188eus
```

Dentro del directorio, hay que incluir en la lista negra los controladores antiguos:
```diff
! sudo -i
! echo "blacklist r8188eu" > "/etc/modprobe.d/realtek.conf"
! exit
```

Luego necesitamos compilar este controlador e instalarlo con el comando "`make`":
```diff
- make
- sudo make install
```

Posteriormente utilizamos el comando `modprobe` para configurar los drivers:
```diff
+ sudo modprobe 8188eu
```

Y por último reiniciar el sistema:
```diff
! reboot
```

Luego del reinicio, solo quedaría probar el modo monitor:
```diff
+ ifconfig <INTERFAZ> down
+ airmon-ng check kill
+ iwconfig <INTERFAZ> mode monitor
+ ifconfig <INTERFAZ> up
+ iwconfig
```

<h1 align="center"></h1>

### Solución para versiones 5.18.0 en adelante
Para este caso los controladores oficiales de aircrack quedarón inutilizable para la nueva versión del kernel de Kali Linux, es por ello que el usuario <a href="https://github.com/KanuX-14">@KanuX-14</a> modifico los controladores pero con pasos extras.

```
> sudo apt update
> sudo apt upgrade
> sudo reboot
> sudo apt install bc
> sudo apt-get install build-essential 
> sudo apt-get install libelf-dev 
> sudo apt-get install linux-headers-$('uname -r')
> cd Desktop
> git clone https://github.com/KanuX-14/rtl8188eus.git
> cd rtl8188eus
> sudo -i
> echo "blacklist r8188eu" > "/etc/modprobe.d/realtek.conf"
> exit
> sudo reboot
> cd Desktop
> cd rtl8188eus
> sh -c "$(curl -fsSL https://raw.githubusercontent.com/KanuX-14/rtl8188eus/v5.3.9/build.sh)"
```

</br>

<p align="center">
  <img src="https://camo.githubusercontent.com/f4bf5c8ac52adfcb3caa0978d1dc22d471840c63560511f3415ae403cd7c24d4/68747470733a2f2f692e6962622e636f2f4868436847576b2f312e706e67">

</br>  
  
<img src="https://user-images.githubusercontent.com/75953873/183260481-5c55a9b9-e365-4dcb-8449-bb8c15ef54fd.png">
</p>

<h1 align="center"></h1>



#### ~R3LI4NT~
