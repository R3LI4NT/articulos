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
