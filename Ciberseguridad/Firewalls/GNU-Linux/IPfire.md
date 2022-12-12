<p align="center">
  <a href="https://github.com/DenverCoder1/readme-typing-svg"><img src="https://readme-typing-svg.herokuapp.com?font=Fira+Code&pause=1000&color=F77800FF&width=475&lines=Instalar+y+Configurar+firewall+IPFIRE"></a>
</p>

<h1 align="center"></h1>

<h3 align="center"><ins>¿QUÉ ES UN FIREWALL Y CÓMO FUNCIONA?</ins></h3>

Un firewall es un sistema de defensa diseñado en proteger redes privadas de accesos no autorizados y no verificado en una conexión de Internet. Además de limitar los intentos de acceso a determinadas redes, también te protegen contra el malware de sitios web malintencionados o de puertos de red vulnerables, así como también una medida de protección contra ataques Dos/DDoS debido a que regula el tráfico que genera. Los firewall de red se pueden encontrar en redes privadas de empresas, hogares, escuelas, cibercafés; y estos pueden ser de tipo hardware o software, o una combinación de ambos.

- Firewall de tipo **HARDWARE**: Los firewalls por hardware son dispositivos electrónicos externos que se colocan en la computadora o red y el modem/router que da acceso a Internet, de manera que le permita controlar las comunicaciones y conexión del lado exterior (entradas y salientes). Se configura generalmente mediante una interfaz de web, el propio usuario del equipo es quien indica que elementos autoriza a ingresar y cuáles no. Su principal ventaja es que no se ejecuta dentro del sistema que protege, por lo que no es fácil de ser manipulado. Por otra parte, un ataque al cortafuegos por hardware produce una caída automática en el dispositivo, lo que bloquea de manera automática el tráfico entrante y saliente hasta que sea reiniciado.

- Firewall de tipo **SOFTWARE**: Los firewalls por software son programas que se ejecutan en el sistema o dispositivo y examinan acerca del tráfico de la red para interceptar y prevenir infecciones de programas maliciosos antes de que lleguen a éste. Normalmente suelen ir acompañados de un antivirus u otra arquitectura de firewall más fuerte, a diferencia del hardware, estos ya vienen preconfigurados con lo más básico para proteger las conexiones. No obstante, un cortafuego de tipo software va a recibir mas actualizaciones que de tipo físico debido que es un programa que instalamos y eso le aporta un plus. Además de que si nos traladamos a otro lugar el firewall va a seguir ahí, mientras que al ser físico se encuentra conectado al sistema o router, y por lo tanto, es menos flexible para trasladarlo de un lugar a otro.

Un firewall actúa bloqueando el tráfico no autorizado y cada diseño de implentación se enfocara a las necesidades de cada individuo o empresa en particular. Existen una variedad de métodos que se utilizan para filtrar el tráfico de datos, que pueden ser utilizados individualmente o combinados en un equipo de firewall:

- **Filtrado de contenido**: Esta funciona examina los paquetes de comunicación que intentan pasar a través del firewall, comparándolos con las reglas. Las reglas determinan cómo se maneja la comunicación de entrada y salida. Las reglas de **ENTRADA** controla el tráfico que se permite o deniega de fuentes externas, es decir, conexiones que se generan en Internet y llegan a nuestro equipo. Las reglasde **SALIDA** controla las conexiones que se genera en nuestro equipo y que tienen como objetivo salir al exterior (Internet). El filtrado de contenido permite a los administradores de redes bloquear fácilmente algunos tipos de contenido web sin tener que proporcionar la URL individualmente, como pueden ser sitios inapropiados o redes sociales, entre otros.

- **Servicio de Anti-Virus a nivel red**: Este servicio es una defensa imlementada en algunos firewalls para proteger la red interna contra ataques que provengan de Internet o enlace WAN (ordenadores interconectados).

- **Servicio Anti-Spam**: Este servicio proteger contra spam, correos phishing y cargados de virus. Utiliza la tecnología de reconocimiento de patrones recurrente (RDP) para analizar y bloquear todos los mensajes infectados en tiempo real. Además, el antispam se aplica a la IP remitente para eliminar y evitar mensajes no deseados.

- **Servicio IDP**: El servicio de Prevención de Detección de Intrusos (IDP) permite al administrador controlar aplicaciones específicas como troyanos y backdoors que pueden infiltrarse en la red interna. Utiliza la tecnología de inspección profunda de paquetes DPI (Deep Packet Inspection), añade una capa de seguridad extra y proporciona al administrador la flexibilidad necesaria para bloquear programas específicos no autorizados en la red como el intercambio de archivos P2P o la mensajería instantánea, evitando así el abuso del ancho de banda.

- **Servicio de cliente VPN SSL**: Con esta función se logra crear un túnel de comunicación de datos encriptado entre el firewall y el usuario de forma rápida y segura sin tener que implementar un software adicional. La función del software VPN se realiza a través de un programa instalado en el equipo del cliente, con autenticación fuerte, soporta hash SHA-2 512 bits con conexión rápida al ejecutarlo. 

- **Gestor de puntos de acceso (AP)**: Actualmente los firewall tienen implementado un servicio para controlar los dispositivos AP y lograr una mejor conectividad para usuarios autorizados y servicios definidos. La gran demanda de conexiones inalámbricas wifi hicieron que las empresas se enfocarán inmediatamente esta función.

<p align="center">
   <img src="https://github.com/R3LI4NT/articulos/blob/main/Ciberseguridad/Firewalls/GNU-Linux/img/Firewall.png">
</p>

<h1 align="center"></h1>

</br>

### CONFIGURAR FIREWALL IPFIRE | VMware

IPFire es una distribución de Linux basada en Debian cuya función principal es actuar como un firewall (cortafuegos) y también de router dentro de una red local, hace uso de IPtables para permitir o denegar el tráfico. IPFire se gestiona muy fácilmente con su interfaz web intuitiva sin necesidad entrar vía SSH , sino que desde el propio nevageador web. No requiere de altos requisitos y prácticamente se puede instalar en cualqueir ordenador actual, el rendimiento dependerá del hardware utilizado y de las reglas del firewall dependiendo de las necesidades.

Proporciona seguridad en entornos domésticos y pequeñas empresas, su facilidad de configurar previene de posibles intrusos en la red gracias a su sistema de IDS (Sistema de detección de intrusos). IPFire emplea un cortafuegos SPI (Stateful Packet Inspection) basado en IPtables, proporciona anchos de banda superiores a los 10Gbps. Con IPFire podemos configurar el firewall para mitigar y bloquear posibles ataques de denegación de servicio gracias a su interfaz gráfica de usuario, podremos crear host y redes para aplicarle reglas ordenadas. El firewall incorpora redes privadas virtuales para interconectar ubicaciones remotas a través de Internet de forma segura, entre las que se incluyen IPsec y OpenVPN; permitiendo que los usuarios puedan conectarse a ella de forma remota y segura gracias a que las comunicaciones permanecen cifradas de extremo a extremo. Además, otra de las características adicionales es la posibilidad de configurar un servidor Proxy e instalar extensiones populares. Esta basada en web, algunos de sus complementos y funciones adicionales son:

- _DNS Dinámico._

- _Sistemas de detección de intrusiones (IDS)._

- _Redes virtuales privadas con IPsec y OpenVPN._

- _Funciones de portal cautivo._

- _Protocolo de configuración dinámica de host (DHCP)._

- _Monitorización de sistemas y registro de análisis._

- _Filtrado GeoIP._

##### Descargar imagen ISO

La descarga y uso de IPfire es completamente gratuita, es tan sencillo como entrar a su web oficial e irnos a la pestaña de **Download**. En este apartado tendremos que elegir la arquitectura de nuestro equipo, luego procedemos en descargar la imagen ISO para cargarla desde un CD o pendrive.

![1](https://user-images.githubusercontent.com/75953873/206926972-49bfa642-9348-4faa-84ba-30e230f740c3.png)

- https://www.ipfire.org/download/

Luego de crear la máquina e importar la ISO en VMware, hay que añadirle dos adaptadores de red como se observa en la imagen. El primero sirve para la conexión hacia el Internet y el segundo hacia la conexión de la red local.

![2](https://user-images.githubusercontent.com/75953873/206936073-7f7e3bfd-b711-4272-bba6-fb230dcb3b11.png)

Iniciamos la máquina y procedemos con la instalación.

![3](https://user-images.githubusercontent.com/75953873/206936368-f499e096-0ce0-4fe1-88f2-654f7af6f19a.png)

Seleccionar el idioma de preferencia.

![4](https://user-images.githubusercontent.com/75953873/206943644-ed83d0c3-6a22-4e48-bc22-156a9035df25.png)

Aceptamos la licencia de GNU (tecla espacio) y damos enter. Luego borraremos los datos del disco SDA, en caso de que contenga información útil, realizar un respaldo.

![5](https://user-images.githubusercontent.com/75953873/206936640-30f59528-9e1e-47f8-bc6d-f6ed001e6421.png)

El formato del sistema de archivo por defecto es ext4 pero podemos elegir otros, personalmente voy a seleccionar XFS ya que es uno de los mejores para trabajar en el cortafuego en el servidor proxy para ofrecer un mejor rendimiento al disco de almacenamiento de caché.

![6](https://user-images.githubusercontent.com/75953873/206937477-14c99685-eeed-497c-9b21-a64f8847ffda.png)

El sistema comenzará a instalarse.

![7](https://user-images.githubusercontent.com/75953873/206938711-b7e0787e-f5be-45bf-8d1a-f8607e691721.png)

Nos devuelve un mensaje de que la instalación ha sido finalizada de manera exitosa, también nos muestra el enlace (junto con el puerto **444**) para acceder a la configuración pero que podremos cambiarlo más adelante. Reiniciamos el sistema.

![8](https://user-images.githubusercontent.com/75953873/206938883-f4242e59-b5b7-4e48-9ee4-2c44d2433383.png)

Al reiniciar el sistema, entramos a la segunda fase de instalación. Seleccionamos el lenguaje de nuestro teclado.

![9](https://user-images.githubusercontent.com/75953873/206939209-b2da480e-09ae-48fc-9f98-2b779f56f9a9.png)

Especificar el tiempo de zona para el servidor, esto depende de donde este ubicado geográficamente.

![10](https://user-images.githubusercontent.com/75953873/206939314-47cb1ce8-1b47-4f32-bca3-8da9c8e280a5.png)

Luego le asignamos el nombre de la máquina (hostname), por defecto es **ipfire** y lo dejaré tal cual está.

![11](https://user-images.githubusercontent.com/75953873/206939501-9acd85e4-e973-4256-bdff-e3a5fb251f4e.png)

Después tenemos que indicarle el nombre del dominio (por defecto es **localdomain**). El nombre del dominio es para el resto de la red local, es decir, va hacer el sufijo DNS de búsqueda.

![12](https://user-images.githubusercontent.com/75953873/206939708-a0440622-78eb-4ddf-834e-9f3572e44e12.png)

Por defecto tendremos dos usuarios: **root** es el usuario para iniciar sesión en la máquina, y **admin** es el usuario para administrar el sistema vía web. El siguiente paso será asignar una contraseña para cada uno de ellos, se recomienda siempre utilizar una contraseña compleja.

![13](https://user-images.githubusercontent.com/75953873/206940019-15a714fd-919b-4f50-ad74-6bb2ffdc54f4.png)

![14](https://user-images.githubusercontent.com/75953873/206940025-7651461d-276a-4937-839f-2c115cbc9ab5.png)

A continuación debemos de configurar las tarjetas de red. IPfire utiliza colores para identificar diferentes interfaces de red:

| COLOR | RED | DESCRIPCIÓN |
| ------------- | ------------- | ------------- |
| RED | WAN | Conexión hacia el proveedor de Internet (ISP). |
| GREEN | LAN | Conexión hacia la red local. |
| ORANGE | DMZ | Zona desmilitarizada que permite que sus servidores respondan a direcciones IP públicas. |
| BLUE | WLAN | Red inalámbrica, una red separada para clientes inalámbricos. |

![15](https://user-images.githubusercontent.com/75953873/206940643-da96005d-731b-4bce-ae52-64dd3863bb22.png)

En mi caso voy a seleccionar verde y rojo. Luego tenemos que asignar a cada adaptador de red (virtuales en este caso) las dos interfaces.

![16](https://user-images.githubusercontent.com/75953873/206941296-c4f1104f-e7f7-408f-ba55-c823b227a640.png)

A continuación configuramos el adaptador RED, que recordemos que es la conexión hacia el Internet.

![17](https://user-images.githubusercontent.com/75953873/206941433-d23e7d81-708e-480d-8049-5df81ba19a71.png)

Y el adaptador GREEN, que corresponde a la red interna, actuando así como puerta de enlace de nuestro entorno.

![18](https://user-images.githubusercontent.com/75953873/206941591-c2df2dd2-87b5-4e2d-98df-4d0ad2a5a067.png)

Ya al haber identificado la dirección MAC de cada adaptador, podemos darle en finalizar.

![19](https://user-images.githubusercontent.com/75953873/206941659-9a65cfcd-ffdd-4b73-869e-2dee2b87a47d.png)

Por último, configuramos la dirreción IP para cada interfaz. En la interfaz roja observarán que tenemos tres opciones a elegir, el modo estático es el más recomendado pero para ello nuestro proveedor de Internet nos tiene que entregar los parámetros de la red (dirección IP pública, máscara de red, enlace de salida y los DNS), el modo DHCP asigna de manera automática direcciones de protocolo de Internet (IP) a los equipo de la red, el modo PPP Dial-UP para una conexión a un modem o a una línea ADSL. Como hemos configurado el adaptador VMWare (ya sea por NAT también), será está la opción a escoger.

![20](https://user-images.githubusercontent.com/75953873/206942415-7bbee8ba-9873-4264-bbf4-cee38cbd7d31.png)

Para la interfaz verde nos pedirá que asignemos una dirección IP local. Yo utilizaré la IP _**192.25.130.254**_ con una máscara de red de 24 bits (255.255.255.0) para que disponga un tamaño de 254 ordenadores (una IP para cada equipo), en este caso va hacer para el gateway y el DNS (va a disponer de 253 direcciones IP) para el modo de DHCP. Le damos a finalizar para guardar los cambios.

![21](https://user-images.githubusercontent.com/75953873/206942975-f3f71467-f561-4d17-a2d7-ad865e8a3a41.png)

Habilitamos el DHCP y configuramos el rango de inicio (**192.25.130.50**) y final (**192.25.130.200**), para el DNS secundario podemos utilizar uno de google (8.8.8.8 o 1.1.1.1), el tiempo de liberación por defecto son 60 minutos pero yo lo voy a cambiar a 5000 minutosy el tiempo máximo de liberación lo voy a cambiar a 10000 minutos. Finalizamos la instalación.

![22](https://user-images.githubusercontent.com/75953873/206943449-1b127e15-a5f7-42a2-929c-90042a9a09bd.png)

Se comenzará a incializar todos los servicios.

![23](https://user-images.githubusercontent.com/75953873/206943905-512a514a-0c03-4ba5-80b5-9367b69f3dd2.png)

Se requiere de otro equipo que se encuentre interconectado en la red local para administrar el firewall vía web, para ello voy a levantar una máquina virtual con Kali Linux que ya había creado, de igual manera funciona con Windows. Hay que asegurarse que el adaptador de la segunda máquina sea el mismo que hemos establecido en el firewall (VMnet6 en este caso). 

![24](https://user-images.githubusercontent.com/75953873/207092281-4c65aa69-4d27-40f9-ad84-814bf9a6bd89.png)

Abrimos una terminal y chequeamos la dirección IP que nos entregó para comprobar diagnósticos de conectividad.

![25](https://user-images.githubusercontent.com/75953873/207094606-3fb25c91-8579-4c79-a539-e3f76553e029.png)

![26](https://user-images.githubusercontent.com/75953873/207094627-a643803b-56e7-4a85-8f59-4865bd11832a.png)
