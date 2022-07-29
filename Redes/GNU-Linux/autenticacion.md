<p align="center">
  <a href="https://github.com/DenverCoder1/readme-typing-svg"><img src="https://readme-typing-svg.herokuapp.com?color=F70000&width=390&lines=Ataque+de+autenticaci%C3%B3n+Wi-Fi"></a>
</p>

<h1 align="center"></h1>

Un ataque de Autenticación es lo inverso al de un Desautenticación, aquí lo que se hace es envíar clientes falsos a la red; esto satura el ancho de banda y puede provocar lentitud e incluso DoS. Es útil si se quiere capturar el handshake pero no hay ningún cliente "real" conectado a la red, entonces se aprovecha este ataque.

<h1 align="center"></h1>

### AIRCRACK-NG

Este ataque es funcional si el punto de acceso tiene la seguridad WEP activada, de lo contrario, mostrará un mensaje de: `Denegado (código 12), ESSID o WPA incorrecto`.
```
aireplay-ng -1 5000 -a <AP-MAC> -h <MAC> <INTERFAZ>
```

**-1:** Modo de ataque Autentciación.

**5000:** Segundos que transcurré para volver a autenticar.

**-a:** Dirección MAC del punto de acceso.

**-h:** Dirección MAC falsa a autenticar.

![2](https://user-images.githubusercontent.com/75953873/181665374-039da28b-5da3-4631-bff3-9411cbc4af81.png)
