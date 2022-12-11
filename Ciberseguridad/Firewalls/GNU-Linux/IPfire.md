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

![4](https://user-images.githubusercontent.com/75953873/206936416-5652ce91-67e4-4192-97ad-fb79c1b97b43.png)

Aceptamos la licencia de GNU (tecla espacio) y damos enter. Luego borraremos los datos del disco SDA, en caso de que contenga información útil, realizar un respaldo.

![5](https://user-images.githubusercontent.com/75953873/206936640-30f59528-9e1e-47f8-bc6d-f6ed001e6421.png)

