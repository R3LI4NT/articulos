<p align="center">
  <a href="https://github.com/DenverCoder1/readme-typing-svg"><img src="https://readme-typing-svg.herokuapp.com?font=Fira+Code&pause=1000&color=008FFF&width=550&lines=Generar+reportes+de+Nmap+con+nmap-bootstrap"></a>
</p>

<h1 align="center"></h1>

<h3 align="center"><ins>¿QUÉ ES Y PARA QUÉ SIRVE UN REPORTE TÉCNICO DE UN PENTEST?</ins></h3>

Un reporte de pentesting es un informe detallado donde se define un listado de acciones que se le recomienda al cliente de realizar. La elaboración del informe es de suma importancia luego de hacer una auditoría ya que en ella se refleja de forma clara los descubrimientos de vulnerabilidades y sus respectivos pasos de explotación. En el apartado del reporte se debe incluir varios aspectos: 

- Vulnerabilidades encontradas.

- Metodología de explotación (exploits utilizados, scripts, pasos, etc).

- Máquinas o recursos vulnerados.

- Criticidad (riesgo).

- Usuarios afectados.

- Conclusiones y recomendaciones.


Las vulnerabilidades se pueden clasificar por dos tipos:

- **Vulnerabilidad por tipo**: Enfocado a empresas mediana-grande que cuente con una cantidad considerable de activos (usuarios = equipos) en donde las vulnerabilidades se repitan y que permiten recolectar información confidencial para comprometer otros recursos. Para cada vulnerabilidad encontrada y explotada, se define su: _Nombre_, _Descripción detallada_, _Criticidad en la empresa_, _Clasificación_, _Número de ID en caso de que corresponda_. Además, de forma detallada se debe incluir una breve descripción de los objetivos afectados, ya sea aplicación web, IP, puerto, URL, etc. Por último, para cada vulnerabilidad se debe proporcionar una prueba que valide la explotación, ya sea capturas de pantallas o el código del payload/exploit, así como también recomendaciones para mantener a la empresa prevenida de ataques similares.

- **Vulnerabilidad por objetivo**: Se enfocada nada más en empresas pequeñas que cuentan con un número considerable de activos o recursos a explotar. El pentester deberá presentar la siguiente información: _El objetivo alcanzado_, _Descripción de la vulnerabilidad_, _Criticidad_, _Resolución_.

</br>

La importancia de un reporte o informe es fundamental para aquellos trabajadores independientes que se dedican a este rubro, ya que con él, el cliente sacará una conclusión de nuestro trabajo. Por lo tanto, si el trabajo está bien hecho, entonces el reporte estará igual, muchas veces esto implica que nos vuelvan a contratar en dicha empresa o nos recomienden con otra. Dentro de un reporte de pentest, es importante definir los pasos a seguir para corregir los problemas identificados. Se debe considerar lo siguiente:

- **Criticidad**: Es el impacto que puede generar las vulnerabilidad encontradas en dichos activos, se tendrá que tomar medidas necesarias para minimizar el riesgo al que se encuentra expuesta la organización/empresa.

- **Medidas a tomar**: En esta parte del informe se define un listado de acciones que se recomienda al cliente realizar, por ejemplo la aplicación de parches de seguridad, actualizaciones y uso de software antimalware en los equipos.

- **Registros / Logs**: Por último, todo reporte debe contener el registro detallado de las acciones realizas durante la prueba de pentest, que serían: _Fecha del test_, _Objetivo atacado_, _Tipo de caja/prueba_, _IP de origen_, _Herramientas utilizadas_, _Pentester a cargo_.

Gracias a la empresa <a href="https://www.offensive-security.com/">Offensive Security</a>, creadores de BackTrack-Kali Linux, han liberado un libro electrónico de reporte que utilizan en sus test de penetración, se encuentra bien estructurado y contiene una base de los elementos que se debe mostrar en un reporte de este tipo.

- https://www.offensive-security.com/reports/sample-penetration-testing-report.pdf

<h1 align="center"></h1>

</br>

### NMAP-Bootstrap

Generalmente cuando escaneamos rangos de redes con muchos hosts, es recomendable hacerlo mediante un informe HTML. Es por eso que gracias al usuario <a href="https://github.com/honze-net">Andreas Hontzia</a> y su gran aportación a la herramienta <a href="https://nmap.org/">Nmap</a>, ha publicado una implementación de una plantilla XSL de nmap con Boostrap para obtener resultados bien estructurados.

Primero que nada, agregamos el XSL de su repositorio con el siguiente comando:

```
nmap -sS -T4 -A -sC -oA scanme --stylesheet https://raw.githubusercontent.com/honze-net/nmap-bootstrap-xsl/master/nmap-bootstrap.xsl scanme.nmap.org scanme2.nmap.org
```

![1](https://user-images.githubusercontent.com/75953873/211124811-d34a8c86-d2a3-4ae9-b6b3-182bf96b4942.png)

Podremos abrir el fichero scanme.xml con nuestro navegador o transformar el xml a html con xsltproc:

```
xsltproc scanme.xml -o scanme.html
```

Como verán a continuación, la información del escaneo se muestra detallada.

![2](https://user-images.githubusercontent.com/75953873/211176445-17c807e5-c18d-4c14-bad4-c638410d45c6.png)

![3](https://user-images.githubusercontent.com/75953873/211176263-f7e319ba-d7ad-41b4-b655-73fbf838b5fe.png)

![4](https://user-images.githubusercontent.com/75953873/211176326-b4a07acf-5420-43fc-82de-7ba9ac1730cd.png)

Es una herramienta muy útil que nos ayuda en la enumeración de hosts, puertos y servicios corriendo.

</br>

<h1 align="center"></h1>

<h3 align="center"><ins>ADVERTENCIA<ins></h3>

<h4 align="center">Esto es con fines de aprendizaje, no nos hacemos responsables ni el fundador, ni el creador del tema del mal uso de esta herramienta o información.</h4>



#### ~R3LI4NT~
