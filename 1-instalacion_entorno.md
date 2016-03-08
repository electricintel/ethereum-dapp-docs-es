## Instalación de Geth, Solidity y Meteor en Ubuntu
                                                                                                                                                                                                                                                                                                                                                                                                                                                                 
`Para este tutorial, es necesario tener un mínimo de experiencia con la terminal` 

### Instalar Geth y Solidity
El primer paso sería instalar la versión estable de Geth, el cliente Go de Ethereum. También debemos instalar SolC, el compilador de Solidity.
```
sudo apt-get install software-properties-common
sudo add-apt-repository -y ppa:ethereum/ethereum
sudo apt-get update
sudo apt-get install ethereum solc
```

Si tienes otra distribución GNU/Linux, puedes mirar en [esta wiki](https://github.com/ethereum/go-ethereum/wiki/Building-Ethereum "Building Ethereum") para ver otras instalaciones.

### Antes de ejecutar Geth

Para que funcione correctamente, debemos crear nuestra primera dirección de Ethereum, ejecutando el siguiente comando:
  
``geth account new``
  
Además hay que indicarle a Geth la ruta donde se instaló SolC, por lo que ejecutamos este comando, y copiamos el resultado para usarlo más tarde:  
  
``which solc``

### Ejecutando geth por primera vez 

Abrimos dos terminales diferentes (o dos pestañas), en el primer terminal ejecutamos el cliente de Ethereum.
  
``geth``
  
Veremos como empieza a cargar la cadena de bloques, esto puede tardar varias horas hasta que se sincronize. Puedes ver el número de bloques actuales en algún explorador de bloques, como [EtherCamp](https://live.ether.camp/ "Explorador de bloques EtherCamp). 

En la segunda terminal, ejecutamos el siguiente comando para entrar en la consola de Geth:
  
``geth attach``
  
Una vez dentro de la consola de Geth, establecemos la ruta del compilador de Solidity, que nos dio el comando "which solc", reemplazando */ruta/del/solc*, manteniendo las comillas.
  
``admin.setSolc("/ruta/del/solc")``
  
Ahora comprobamos dentro de la consola de Geth si detecta el compilador de Solidity:
  
``eth.getCompilers()``
  
Si la salida del comando es ["Solidity"], has instalado correctamente el compilador en el cliente geth. Puedes salir de la consola pulsando la combinación de teclas Ctrl+D.
  
### Instalar Meteor 

### Desarrollar contratos en una cadena de bloques de testeo

#### To be continued!

### Fuentes
* [ go-ethereum wiki - Installation Instructions for Ubuntu](https://github.com/ethereum/go-ethereum/wiki/Installation-Instructions-for-Ubuntu) 
* [go-ethereum wiki - Contract Tutorial](https://github.com/ethereum/go-ethereum/wiki/Contract-Tutorial) 
* [ ethereum wiki - Dapp using Meteor ](https://github.com/ethereum/wiki/wiki/Dapp-using-Meteor) 