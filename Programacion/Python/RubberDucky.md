<p align="center">
  <a href="https://github.com/DenverCoder1/readme-typing-svg"><img src="https://readme-typing-svg.herokuapp.com?font=Fira+Code&pause=1000&color=000BF7&width=435&lines=Crear+Rubber+Ducky+casero+con+Python"></a>
</p>

<h1 align="center"></h1>

<h3 align="center"><ins>¿Qué es un USB Rubber Ducky?</ins></h3>

Existen una variedad de métodos por los cuales pueden atacar nuestro ordenador. Estamos acostumbrados toparnos con malware a través de descargas, con enlaces maliciosos (phishing), software malintencionados, entre otros. Pero también a través de dispositivos físicos, como lo es Rubber Ducky.

Un Rubber Ducky es un pendrive (USB) programado que funciona como un teclado conectado, nada más conectarse comienza a escribir en el equipo de forma automatizada con los payloads ya configurados para lanzar programas y herramientas cargados en el equipo de la víctima o en el propia memoria Micro SD que lleva incluida. Lo que lo hace peligroso es que es indetectable, los sistemas operativos permiten la comunicación con el usuario a través de los teclados USB lo que implica que un Rubebr Ducky sea acepatado como uno más y tenga la posibilidad de desactivar antivirus, entre otros programas de seguridad de suma importancia.

#### Tipos de ataques con un Rubber Ducky

Este ataque se aprovecha de la confianza del usuario para ser llevado a cabo (ingeniería social) o de equipos expuestos. Solo imagina por un momento las miles de posibilidades que puede hacer con este dispositivo, pedirle a un amigo/a que te imprima un documento, acceso a puertos USB de una oficina o cibercafe, arrojar pendrives en zonas públicas y esperar que alguien lo enchufe a su dispositivo y que la información que extraiga la suba a un servidor FTP. Por mencionar algunos ataques:

- Robar contraseñas del Wi-Fi.

- Recolección información sensible del sistema operativo.

- Robar cookies del navegador.

- Subir información a través de un servidor FTP.

- Borrar datos del sistema.

- Modificar el DNS para engañar a la víctima (Pharming de DNS).

- Bloquear programas del sistema (antivirus, firewall).

- Borrar usuarios y agregar permisos administrativos.

- Infectar el sistema por medio de una descargar vía internet.

- Crear puerta trasera (backdoor) para acceder de forma remota.

<p align="center">
  <img src="https://github.com/R3LI4NT/articulos/blob/main/Programacion/Python/img/rubberDucky.png">
</p>

</br>

Las especificaciones técnicas que incorporá el Rubber Ducky son:

- Ranura para tarjeta Micro SD.

- Luz LED que indica el estado del dispositivo.

- Botón qeu permite re-ejecutar el código.

- Conector USB Tipo A.

- Procesador de 60 MHz de 32 bits.

- Lector USB de memorias micro SD.

- Case USB.

En seguida que se conecta este USB, es reconocido como un driver Atmel de Windows, engañando al sistema haciéndose pasar por un teclado (para no levantar sospechas y evitar ser bloqueado por antivirus y/o firewall) y ejecutar las tecladas indicadas en el código programado (payload).

<p align="center">
  <img src="https://blogger.googleusercontent.com/img/a/AVvXsEhKkGfB_D2uI1vyV5SgBe-6aIN3G6gCksHVXCw_qFgnlGKcbw3ZeLhx2NmPh8jgtV84Yt4xpQZ9_S7PKKD_gIUNMmppio90PfTyyLQW08-bllBLOdJcuSmOvw8VIs2vTTwZ06zVUTRMhTT9hP4D4sfXAe9EG0nLNkFop3aJhn11XF8GcSJ96Mx_VAll=w640-h269">
</p>

</br>

#### ¿Cómo funciona?

Luego de haber visto los componentes de hardware que incorpora el Rubber Ducky, es preciso saber cómo funciona por dentro. Utiliza un lenguaje de programación llamado <a href="https://github.com/hak5darren/USB-Rubber-Ducky/wiki/Duckyscript">"**_Ducky Script_**"</a>, compuesto por una sintaxis sencilla de escribir y soportada por cualquier edit de código (Notepad, vi, emacs, nano, gedit, kedit, TextEdit, etc). Cada comando reside en una nueva línea y puede tener opciones a continuación. Los comandos están escritos todo en mayúsculas, algunas instrucciones:

## Uso:
| SINTAXIS | DESCRIPCIÓN |
| ------------- | ------------- |
| REM | Comentarios, código que no será ejecutado.  |
| DELAY  | crea una pausa momentánea en el guión de Ducky. El tiempo DELAY se especifica en milisegundos de 1 a 10000. Se pueden usar varios comandos DELAY para crear retrasos más largos.  |
| DEFAULT_DELAY / DEFAULTDELAY | Se debe definir un valor entre 0 y 10000 (milisegundos), el cual establecerá un delay a todas las secuencias de comandos.  |
| STRING | Permite inyectar cadenas de caracteres: a-z A-Z 0-9 !-) `~+=_-"';:<,>.?[{]}/|!@#$%^&*()`.  |
| WINDOWS / GUI | Equivale a la tecla windows o la tecla cmd en macos.  |
| SHIFT | Simula la tecla SHIFT, y esta se puede combinar con: DELETE, HOME, INSERT, PAGEUP, PAGEDOWN, WINDOWS, GUI, UPARROW, DOWNARROW, LEFTARROW, RIGHTARROW, TAB.  |
| DELETE | Simula la tecla suprimir. |
| RIGHTARROW / RIGHT | Simulan las teclas de dirección.  |
| UPARROW / UP | Simulan las teclas de dirección.  |
| DELETE | Simula la tecla suprimir.  |

Quién está detrás de este proyecto es el grupo de hackers <a href="https://shop.hak5.org/products/usb-rubber-ducky">Hak5</a>, se desempeñan en crear kits de herramientas de pentesting para todo público; enfocados especialmente en la recopilación de información, reconocimiento avanzado, la recopilación de inteligencia de código abierto y más. 