<p align="center">
  <a href="https://github.com/DenverCoder1/readme-typing-svg"><img src="https://readme-typing-svg.herokuapp.com?color=F70000&width=390&lines=Ataque+de+autenticaci%C3%B3n+Wi-Fi"></a>
</p>

<h1 align="center"></h1>

Un ataque de Autenticación es lo inverso al de un Desautenticación, aquí lo que se hace es envíar clientes falsos a la red; esto satura el ancho de banda y puede provocar lentitud e incluso DoS. Es útil si se quiere capturar el handshake pero no hay ningún cliente "real" conectado a la red, entonces se aprovecha este ataque.

<h1 align="center"></h1>

### AIRCRACK-NG

Este ataque es funcional si el punto de acceso tiene la seguridad WEP activada, de lo contrario, mostrará un mensaje de: `Denegado (código 12), ESSID o WPA incorrecto`.
```
aireplay-ng --fakeauth 5000 -a <AP-MAC> -h <MAC> <INTERFAZ>
```

**--fakeauth / -1:** Modo de ataque Autenticación.

**5000:** Segundos que transcurré para volver a autenticar.

**-a:** Dirección MAC del punto de acceso.

**-h:** Dirección MAC falsa a autenticar.

![2](https://user-images.githubusercontent.com/75953873/181665516-835bfdd9-d080-4091-92e1-86f72cb22987.png)

Al específicar el tiempo en `0` la autenticación del cliente falso será ilimitado.

</br>

<h1 align="center"></h1>

### MDK4

La herramienta MDK4 también contiene parámetros para dicho ataque:

**a:** Modo de ataque Autenticaicón.

**-a:** Dirección MAC del punto de acceso.

**-m:** Direcciones MAC's aleatorias.

```
mdk4 <INTERFAZ> a -a <AP-MAC> -m 
```
![1](https://user-images.githubusercontent.com/75953873/181666285-473396ff-e871-4196-9245-3b0956e5e229.png)

</br>

<h1 align="center"></h1>

<h3 align="center"><ins>ADVERTENCIA<ins></h3>

<h4 align="center">Esto es con fines de aprendizaje, no nos hacemos responsables ni el fundador, ni el creador del tema del mal uso de esta herramienta u información.</h4>



#### ~R3LI4NT~
